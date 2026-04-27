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

This article explains how to set up the Expense Agent by using the **Configure Expense Agent** page.

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

  The capability is enabled if the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon appears in the upper-right corner of the role center.  
  Learn more in [Configure Copilot and agent capabilities](../enable-ai.md).

## Configure Expense Agent

Use the **Configure Expense Agent** page to configure and activate the agent.
The page guides you through agent setup. You configure submission channels, access controls, defaults, and policies, then activate the agent to handle registration.

1. In the upper-right corner of the role center, select the select the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon-small.png) **Expense Agent** icon, and then select **Activate**.
1. Follow the instructions onscreen to configure how the agent should behave.
1. The configuaration options are spread across multiple pages. Use the **Go to next card** and **Go to previous card** arrows to move between pages.
1. When you finish configuring the options, turn on the **Active** toggle to activate the agent.  
   If you don't want to activate the agent yet, leave the toggle off. You can retrun to the page to active the agent later.
1. Select **Save**.

After configuration, the Expense Agent icon indicates the agent’s status:

- ![Shows the Expense Agent icon](../media/expense-agent-icon-small.png) indicates the agent ready to process expense submissions.
- ![Shows the Expense Agent icon](../media/expense-agent-configured-icon-small.png) indicates agent is configured but not currently active.

## What the configuration page does

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
- Managers and approvers can review and approve expense reports in Business Central and the Expense Agent web app.

You can return to the **Configure Expense Agent** page at any time to update settings, apply other defaults, or deactivate and reactivate the agent.

For detailed descriptions of individual setup options, validation rules, and operational limits, see 

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
    > The configuration hides age-related controls, but setup contains these fields and logic references:
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
[Configure Copilot and agent capabilities](../enable-ai.md)

