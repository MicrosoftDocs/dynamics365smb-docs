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

- Anthropic model is enabled as subprocessor in the Microsoft 365 admin center.

  Learn more in [Anthropic as a subprocessor for Microsoft Online Services](/microsoft-365/copilot/connect-to-ai-subprocessor).

- Your Business Central account has the **EXPENSE MGMT. ADMIN** permission set or equivalent permissions.

- The **Expense Agent** capability is active on the **Copilot & Agent Capabilities** page. 

  The agent is already activated if the ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon.svg) **Expense Agent** icon appears in upper-right of the role center.

  Learn more in [Configure Copilot and agent capabilities](../enable-ai.md).

- A shared mailbox is available for receiving expenses from employees. 

  The Expense Agent monitors incoming emails to this mailbox. The email account must be a **Microsoft 365** type (user mailbox or shared mailbox) in your organization. Learn more in [Set up email](../admin-how-setup-email.md).

  > [!IMPORTANT]
  > You need **Read and manage (Full Access)** permission on the shared mailbox. As an Exchange admin, delegate these permissions to all users who need to activate and configure the agent. Learn more in [Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation).

- Number series, payment methods, and posting groups for expenses are configured (optional)

  You can choose to use the default setting during setup, which creates these entities for you.

## Set up the Expense Agent

The following sections explain how to set up the Expense Agent.

### Configure Expense Agent

1. In the navigation bar at the upper right of the role center, select ![Shows the Expense Agent icon](../media/expense-agent-unconfigured-icon.svg) **Expense Agent** icon > **Activate**.
1. Follow the instructions on the page to configure the option you want.
1. On the right side of the page, select the **Go to next card** arrow to configure more options that determine how the agent behaves.

   The options are spread across multiple pages. Use the **Go to next card** and **Go to previous card** arrows to go back and forth between the pages to set the various options.
1. When done configuring the options, turn on the **Active** toggle to activate the agent.

  If you don't want to enable it now, skip this step. You can enable it later.
1. Select **Save** to save your changes.

If you activated the agent, the icon changes to ![Shows the Expense Agent icon](../media/expense-agent-icon.svg) indicating it's ready to handle incoming expenses from the Expense Agent web app or email.

The ![Shows the Expense Agent icon](../media/expense-agent-configured-icon.svg) icon indicates that agent is configured but not active.

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

### Agent not processing emails

**Problem:** Scheduled task is not running or finding emails.

**Solutions:**

1. Verify that **Enable Agent** is turned on.
2. Check that the mailbox account is configured correctly.
3. Confirm that Email Connector v4 is installed and configured.
4. Review the **EA Scheduler Task** table for errors.
5. Verify that the user has **Can Create Task** permission.

### Expenses failing validation

**Problem:** Cannot save or submit expenses.

**Solutions:**

1. Check the age of the expense against the **Do Not Allow Expenses Older Than** setting.
2. Verify that the category and subcategory are valid and active.
3. Confirm that the payment method is marked as **Expense Report Type**.
4. Check that a posting group is assigned to the category.
5. Verify that the employee is configured as an expense employee.

### Per diem not calculating

**Problem:** Per diem amounts are not populating.

**Solutions:**

1. Verify that **Full Per-Diem Calculation** is not set to **None**.
2. Check that per diem rates are configured for the location/category.
3. Confirm that travel dates span the required minimum hours.
4. Review partial day rule settings.
5. Check that **Per Diem Rounding Precision** is set.

### Posting errors

**Problem:** Cannot post expense reports.

**Solutions:**

1. Verify that the posting group has all required G/L accounts configured.
2. Check that G/L accounts allow direct posting.
3. Confirm that the number series for posted expense reports is set.
4. Verify the approval status (if approval workflow is enabled).
5. Check that the source code **EXPENSE** exists in Source Code Setup.

## Related information

[Set up email](admin-how-setup-email.md)  
[Use the Exchange admin center to edit shared mailbox delegation](/microsoft-365/admin/email/create-a-shared-mailbox#use-the-eac-to-edit-shared-mailbox-delegation)
