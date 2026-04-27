---
title: Set up the Expense Agent
description: Learn how to set up and configure the Expense Agent to automate expense tracking, processing, and approval workflows in Business Central.
author: jswymer
ms.topic: how-to
ms.date: 01/30/2026
ms.author: jswymer
ms.reviewer: jswymer
---

# Set up the Expense Agent

The Expense Agent automates expense tracking, processing, and approval workflows. The agent can monitor email accounts for expense submissions, automatically create expense reports, and enforce compliance rules. This article explains how to set up and configure the Expense Agent.

## Prerequisites

Before you set up the Expense Agent, make sure the following prerequisites are met:

- The Anthropic model is enabled as a subprocessor in the Microsoft 365 admin center.

  Learn more in [Anthropic as a subprocessor for Microsoft Online Services](/microsoft-365/copilot/connect-to-ai-subprocessor).

- Your Business Central account has the **EXPENSE MGMT. ADMIN** permission set or equivalent permissions.

- The **Expense Agent** capability is active on the **Copilot & Agent Capabilities** page.

  If the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon appears in the upper-right of the role center, the capability is already enabled.

  Learn more in [Configure Copilot and agent capabilities](../enable-ai.md).

- A shared mailbox is available for receiving expenses from employees.

  The Expense Agent monitors incoming emails to this mailbox. The email account must be a **Microsoft 365** type (user mailbox or shared mailbox) in your organization. Learn more in [Set up email](../admin-how-setup-email.md).

  > [!IMPORTANT]
  > You need **Read and manage (Full Access)** permission on the shared mailbox. As an Exchange admin, delegate these permissions to all users who need to activate and configure the agent. Learn more in [Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation).

- Number series, payment methods, and posting groups for expenses are configured (optional).

  You can choose to use the default settings during setup, which creates these entities for you.

### Prerequisites

Before you set up the Expense Agent, make sure the following prerequisites are met:

- The Anthropic model is enabled as a subprocessor in the Microsoft 365 admin center.

  Learn more in [Anthropic as a subprocessor for Microsoft Online Services](/microsoft-365/copilot/connect-to-ai-subprocessor).

- Your Business Central account has the **EXPENSE MGMT. ADMIN** permission set, or equivalent permissions.

- A shared mailbox is available for receiving expense submissions from employees.
  
  The mailbox must be a Microsoft 365 user or shared mailbox in your organization. Learn more in [Set up email](../admin-how-setup-email.md).

  > [!IMPORTANT]
  > You need **Read and manage (Full Access)** permission on the shared mailbox. Learn more in [Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation).

- Number series, payment methods, and posting groups for expenses are configured (optional).

  You can let the setup wizard create default values for you during configuration.

- The **Expense Agent** capability is enabled on the **Copilot & Agent Capabilities** page.
  
  The capability is enabled if the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon appears in the upper-right corner of the role center. 
 
  Learn more in [Configure Copilot and agent capabilities](../enable-ai.md).


## Set up the Expense Agent

The following sections explain how to use **Configure Expense Agent** page to set up the Expense Agent.

### Configure the Expense Agent

1. In the navigation bar at the upper right of the role center, select ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon > **Activate**.
1. Follow the instructions on the page to configure the options you want.
1. On the right side of the page, select the **Go to next card** arrow to configure more options that determine how the agent behaves.

   The options are spread across multiple pages. Use the **Go to next card** and **Go to previous card** arrows to go back and forth between the pages to set the various options.
1. When done configuring the options, turn on the **Active** toggle to activate the agent.

   If you don't want to enable it now, skip this step. You can enable it later.
1. Select **Save** to save your changes.

If you activated the agent, the icon changes to ![Shows the Expense Agent icon](../media/expense-agent-icon-small.png) indicating it's ready to handle incoming expenses from the Expense Agent web app or email.

The ![Shows the Expense Agent icon](../media/expense-agent-configured-icon-small.png) icon indicates that the agent is configured but not active.

## What the setup wizard does

The **Configure Expense Agent** wizard is the primary interface for setting up the Expense Agent. Behind the scenes, it orchestrates setup persistence, agent registration with your ERP environment, and scheduled task creation. This section explains what happens when you configure options and enable or disable the agent—the validation gates, state transitions, and integration calls. If you're looking for step-by-step setup instructions, see [Set up the Expense Agent](#set-up-the-expense-agent) earlier in this article.

For admins, the wizard workflow orchestrates these stages in sequence:

1. Loads current **Expense Agent Setup** into a temporary working record.
1. Lets you configure access, defaults, policy settings, communication, mileage, and per diem.
1. On **Update**, validates and saves data, applies selected default data packs, and updates agent state.
1. If agent state changes to active, runs enablement checks and registration.
1. If agent state changes to inactive, unregisters ERP configuration and removes scheduled tasks.

When the agent is activated, the wizard performs these guardrails:

- Enforces early-access environment constraints (sandbox checks in SaaS production URLs).
- Requires privacy notice approval.
- Verifies Copilot capability activation for **Expense Agent**.
- Ensures the current user has agent access control (adds one if missing).
- Enables the Expense Agent AAD app and ensures the **Expense Agent** permission set is assigned.
- Registers ERP configuration through the integration endpoint.

## Wizard fields and options by group (admin details)

The sections below describe each wizard field, organized by the logical groups that match the wizard interface. Each field includes details about dependencies, validation rules, operational limits, and how it affects runtime behavior and integration with backend codeunits. Some fields become locked after defaults are applied; see the related default sections for details. To configure fields that aren't visible in the wizard (for example, age handling formulas, per diem location rates, and advanced scheduling), use the full **Expense Agent Setup** page.

### Access and submission

#### Submission channels

- **Enable sending email with receipts**
  - Enables mailbox selection and notification controls in the wizard UI.
  - Admin note: backend dispatch is primarily gated by **Enable Agent** and a valid mailbox account; keep this option aligned with your operational intent.

- **Mailbox account**
  - Stores **Email Account ID**, **Email Connector**, and **Email Address** used by retrieval and outbound mail.
  - Wizard filters mailbox selection to **Email Connector v4** accounts.
  - If the selected mailbox is no longer valid, setup clears mailbox fields and disables the agent.
  - If the mailbox changes while agent is enabled, scheduler is recreated on save.

#### Who can access

- **Users** (Agent Access Control part)
  - Controls who can configure and who can work on behalf.
  - On activation, current user is auto-added with both permissions if missing.

### Use accounting defaults

- **Number series**
  - Creates and assigns default series for expenses, expense users, expense reports, and posted expense reports.
  - Sets **No. Series Applied**; once set, wizard control is locked.

- **Payment methods**
  - Creates seed methods (Card, Cash, Bank) when not already represented.
  - Sets **Payment Methods Applied** and locks this option afterward.

- **Expense posting groups**
  - Creates default posting setup and employee posting setup dependencies.
  - Sets **Posting Groups Applied** and locks afterward.
  - In UI mode, posting-group defaults can optionally copy existing employees into Expense Users.

- **Apply default expense categories and subcategories**
  - Requires posting groups.
  - If selected while posting groups aren't yet applied, wizard autoselects posting groups.
  - Sets **Exp. Categories Applied** and locks afterward.

### Use management defaults

- **Expense locations**
  - Creates location master data defaults.
  - Sets **Exp. Locations Applied** and locks afterward.

- **Apply default management rules**
  - Creates default rule headers and conditions.
  - Depends on locations.
  - If selected while locations aren't selected/applied, wizard autoselects locations.
  - Sets **Management Rules Applied** and locks afterward.

### Rules and controls

- **Enforce management rules** (**Use Rules**)
  - Enables category/location rule enforcement during expense and expense report line validation.
  - Important: per-diem flows still run rule application logic even when this switch is off.

- **Require receipt number**
  - Adds validation violations when receipt number is blank on expenses and report lines.

- **Require merchant name**
  - Adds validation violations when merchant name is blank on expenses and report lines.

- **Display anti-corruption attestation**
  - Controls visibility of attestation section on expense report pages and manager approval views.
  - Admin note: this setting controls display/collection; it isn't implemented as a hard post/submit block by setup validation itself.

> [!NOTE]
> The wizard hides age-related controls, but setup contains these fields and logic references:
> - **Do Not Allow Exp. Older Than** (date formula, default `<3M>` in default setup)
> - **If Exp. Is Older Than Allowed** (warning/justification/error enum)
>
> In current code paths, age formula is used in duplicate-detection range behavior for posted report lines; the handling enum is present but not wired as a direct submit-block path in the wizard flow.

### Communication

- **Notify users about unsubmitted reports**
  - Enables reminder processing for users with open expense reports.
  - Wizard allows it only when email with receipts is enabled and mailbox exists.

- **Notification frequency**
  - Options: **Daily**, **Weekly**, **Monthly**, **Custom**.
  - Changing frequency resets dependent schedule fields in setup (day-of-week, day-in-month, custom formula) to keep valid combinations.
  - Wizard exposes frequency; full scheduling fields are available on the full **Expense Agent Setup** page.

- Runtime scheduling behavior
  - First run initializes last-notification timestamp and doesn't send immediately.
  - Next runs calculate next due time from frequency settings and send one reminder per expense user with open reports.

### Mileage expenses

- **Rate per unit** (**Standard Rate of Mileage**)
  - Drives mileage amount autocalculation in expense and report lines.
  - Validation checks calculated amount consistency against entered amount.

- **Default unit of distance** (**Default Mileage UOM**)
  - Autopopulates mileage unit when missing.
  - Rule validation enforces UOM alignment for mileage-required entries.
  - Assist lookup is constrained to standard mileage UOM candidates.

### Per diem expenses

- **Per diem calculation** (**Full Per-Diem Calculation**)
  - Options: **None**, **Full Calendar Day**, **24-hour Rolling Period**, **Overnight Stay**.
  - Changing option autoadjusts related settings:
    - **None** resets partial-day settings and minimum hours.
    - Full-day/rolling/overnight enforce compatible partial-day rule patterns.

- **Rounding precision**
  - Used in per-diem hour calculations and amount rounding behavior.

- **Minimum hours**
  - Only valid for **24-hour Rolling Period** and **Overnight Stay**.
  - Invalid combinations are blocked by setup validation.

#### Partial day

- **Rule** (**Partial Day Rules**)
  - **Flat Percentage of Full Rate** or **Based on Eligible Hours**.
  - Must match the selected full per-diem method (validated in setup).

- **Partial day minimum hours**
  - Minimum hours before partial-day amount applies.

- **Partial day percentage**
  - Percentage multiplier used for partial-day payout.

- **Breakfast/Lunch/Dinner reduction (%)**
  - Copied into generated per-diem detail lines and used as meal deductions.

- Runtime detail
  - Per-diem calculation uses date spans, selected method, and a 1% hour tolerance in threshold comparisons.

### Active toggle and save behavior

- The **Active** toggle comes from the embedded agent setup part and maps to enabled/disabled agent state.
- On **Update**, wizard save sequence applies changes, defaults, activation/deactivation integration calls, and scheduler updates.
- If enabling without mailbox, wizard shows warning and requires confirmation to continue.
- Activation prerequisites include applied defaults for posting groups/categories and required number series values.

### Operational limits to plan for

- Scheduler creates one agent task and one recovery task; each run reschedules itself.
- Email retrieval is capped at **100 processed emails per 24 hours**.
- Retrieval requests load up to **50 emails per pull**.
- Outbound outbox processing sends up to **25 emails per dispatcher run**.
- Outbound retries stop at **5 attempts**, then message status changes to **Failed**.

<!--Test the setup

After you configure the Expense Agent, test the setup to make sure everything works correctly.

### Create a test expense

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Expenses**, and then choose the related link.
2. Create a new expense.
3. Select a category, payment method, and amount.
4. Verify that all fields populate correctly.
5. Check that validation rules work as expected.

### Test expense report creation

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Expense Reports**, and then choose the related link.
2. Use the **Add Expenses** action to add expenses to a report.
3. Verify grouping and calculation logic.
4. Submit for approval (if approval workflow is enabled).

### Validate agent functionality (if enabled)

1. Send a test expense email to the configured mailbox.
2. Wait for the scheduled task to run (check after 20 seconds).
3. Verify that the expense is created in the system.
4. Check the **EA Scheduler Task** table for processing logs.

### Test per diem calculation (if configured)

1. Create an expense with a per diem category.
2. Enter start and end dates.
3. Verify that the per diem amount is calculated correctly.
4. Test partial day and meal deduction scenarios.

### Verify posting

1. Create and approve an expense report.
2. Post the expense report.
3. Check **Expense Ledger Entries** for posted transactions.
4. Verify that G/L entries are created correctly.

## Best practices

Consider the following best practices when setting up and using the Expense Agent:

- **Start simple** - Begin with basic setup and a few categories. Enable advanced features (rules, automation) after users are comfortable.
- **Define clear policies** - Document what expenses are allowed. Set appropriate age limits for expense submission. Communicate policies to all employees.
- **Regular reviews** - Review expense categories quarterly. Update mileage and per diem rates annually. Archive or inactivate unused categories.
- **Security considerations** - Limit who can approve expenses. Use teams for delegated approval. Enable anti-corruption attestation for compliance.
- **Email agent monitoring** - Monitor scheduled task logs regularly. Set up error notifications. Test email integration thoroughly before going live.
- **Approval workflows** - Define clear approval hierarchies. Set appropriate approval limits. Configure reminder notifications.
-->

## Troubleshooting

### You can't turn off the agent

**Problem:** When you turn off the **Active** toggle, you get the message: Failed to unregister environment from Expense Agent service. Please try again or contact support.

### Agent not processing emails

**Problem:** Scheduled task isn't running or finding emails.

**Solutions:**

1. Verify that **Enable Agent** is turned on.
2. Check that the mailbox account is configured correctly.
3. Confirm that Email Connector v4 is installed and configured.
4. Review the **EA Scheduler Task** table for errors.
5. Verify that the user has **Can Create Task** permission.

### Expenses failing validation

**Problem:** Can't save or submit expenses.

**Solutions:**

1. Check the age of the expense against the **Do Not Allow Expenses Older Than** setting.
2. Verify that the category and subcategory are valid and active.
3. Confirm that the payment method is marked as **Expense Report Type**.
4. Check that a posting group is assigned to the category.
5. Verify that the employee is configured as an expense employee.

### Per diem not calculating

**Problem:** Per diem amounts aren't populating.

**Solutions:**

1. Verify that **Full Per-Diem Calculation** isn't set to **None**.
2. Check that per diem rates are configured for the location/category.
3. Confirm that travel dates span the required minimum hours.
4. Review partial day rule settings.
5. Check that **Per Diem Rounding Precision** is set.

### Posting errors

**Problem:** Can't post expense reports.

**Solutions:**

1. Verify that the posting group has all required G/L accounts configured.
2. Check that G/L accounts allow direct posting.
3. Confirm that the number series for posted expense reports is set.
4. Verify the approval status (if approval workflow is enabled).
5. Check that the source code **EXPENSE** exists in Source Code Setup.

## Related information

[Set up email](../admin-how-setup-email.md)  
[Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation)


---
title: Set up the Expense Agent
description: Learn how to set up the Expense Agent to automate expense tracking, processing, and approval workflows in Business Central.
author: jswymer
ms.topic: how-to
ms.date: 01/30/2026
ms.author: jswymer
ms.reviewer: jswymer
---

# Set up the Expense Agent

The Expense Agent helps automate expense tracking, processing, and approval workflows in Dynamics 365 Business Central. After you set it up, employees can submit expenses through email or the Expense Agent web app, and the agent creates expense reports and applies configured rules automatically.

This article explains how to set up the Expense Agent by using the **Configure Expense Agent** setup wizard.

## Prerequisites

Before you set up the Expense Agent, make sure the following prerequisites are met:

- The Anthropic model is enabled as a subprocessor in the Microsoft 365 admin center for Microsoft Online Services.  
  Learn more in [Anthropic as a subprocessor for Microsoft Online Services](/microsoft-365/copilot/connect-to-ai-subprocessor).

- Your Business Central account has the **EXPENSE MGMT. ADMIN** permission set or equivalent permissions.

- A shared mailbox is available for receiving expense submissions from employees.  
  
  The mailbox must be a Microsoft 365 **user mailbox** or **shared mailbox** in your organization. Learn more in [Set up email](../admin-how-setup-email.md).

  > [!IMPORTANT]  
  > You need **Read and manage (Full Access)** permission on the shared mailbox. Learn more in [Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation).

- Number series, payment methods, and posting groups for expenses are configured (optional).  

  You can choose to use default values during setup, and the wizard creates these entities for you. 

- Billing for agent capabilities is setup up in Business Central admin center.

  Expense Agent uses Microsoft Copilot Studio messages when activated, which your company is charged for. Learn more in [Manage consumption-based billing](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-consumption-billing).

- The **Expense Agent** capability is enabled on the **Copilot & Agent Capabilities** page.  

  The capability is enabled if the **Expense Agent** icon appears in the upper-right corner of the role center.  
  Learn more in [Configure Copilot and agent capabilities](../enable-ai.md).

## Configure Expensee 

Use the **Configure Expense Agent** setup wizard to configure and activate the agent.
The wizard guides you through agent setup in a controlled sequence. You'll configure submission channels, access controls, defaults, and policies, then activate the agent with scheduled task creation and ERP registration. For detailed information on what happens at each stage, see [What the setup wizard does](#what-the-setup-wizard-does) later in this article.

1. In the upper-right corner of the role center, select the **Expense Agent** icon, and then choose **Activate**.d
1. Follow the instructions onscreem to configure how the agent should behave.
1. Use the **Go to next card** and **Go to previous card** arrows to move between pages.
1. When you finish configuring the options, turn on the **Active** toggle to activate the agent.  
   If you don't want to activate the agent yet, leave the toggle off. You can retrun to the page to active the agent later.
1. Select **Save**.

When the agent is active, the icon indicates that it’s ready to process expense submissions. If the agent is configured but not active, the icon reflects that state.

## What the setup wizard does

The **Configure Expense Agent** page guides you through the choices required to prepare the Expense Agent for use in your Business Central environment.

The guide helps you:

- Configure how expenses can be submitted and who can access or manage the agent.
- Apply optional default data, such as number series, posting groups, categories, and management rules.
- Define validation, notification, mileage, and per diem behavior.
- Save configuration changes without activating the agent.
- Activate or deactivate the agent when you’re ready.

When you activate the agent, Business Central verifies that all required conditions are met, such as enabled capabilities, correct permissions, and a valid mailbox for email-based expense submission. If any required conditions aren’t met, the wizard prompts you to address them before activation completes.

If you deactivate the agent later, Business Central stops processing incoming expenses and disables background processing. Your configuration settings are retained so that you can reactivate the agent without reconfiguring it.

## After you finish setup

After the Expense Agent is active:

- The agent starts monitoring the configured mailbox for incoming expense submissions.
- Expenses submitted by email or through the Expense Agent web app are processed based on your configuration.
- Expense reports are created automatically and routed according to your rules.
- Reminder notifications are sent based on your notification settings, if enabled.
- 
- Managers and approvers can review and approve expense reports in Business Central.

You can return to the **Configure Expense Agent** page at any time to update settings, apply other defaults, or deactivate and reactivate the agent.

For detailed descriptions of individual setup options, validation rules, and operational limits, see the companion reference article.

## Troubleshooting

### Agent not processing emails

**Problem:** The agent doesn’t process incoming emails.

**Resolution:**
- Verify that the agent is active.
- Confirm that the mailbox account is configured correctly.
- Ensure that Email Connector v4 is installed and configured.
- Check scheduler task entries for errors.
- Verify that the user has permission to create background tasks.

### Expenses failing validation

**Problem:** Expenses can’t be saved or submitted.

**Resolution:**
- Check the age of the expense against configured limits.
- Verify that categories, posting groups, and payment methods are configured and active.
- Confirm that the employee is set up as an expense user.

### Per diem not calculating

**Problem:** Per diem amounts aren’t generated.

**Resolution:**
- Verify that per diem calculation isn’t set to **None**.
- Confirm that per diem rates are configured.
- Check minimum hours and rounding settings.

## Related information

- [Set up email](../admin-how-setup-email.md)
- [Configure Copilot and agent capabilities](../enable-ai.md)