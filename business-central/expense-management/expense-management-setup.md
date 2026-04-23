---
title: Set Up Expense Management in Business Central
description: Learn how to configure expense management settings including the expense agent, mailbox, number series, posting groups, and approval workflows.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6976, 6996
---

# Set up expense management

Before employees can record expenses and submit reports, an administrator must configure the expense management module in [!INCLUDE[prod_short](../includes/prod_short.md)]. This article walks you through the key setup tasks.

## To set up a shared mailbox

To let the expense agent receive receipts by email, create a dedicated shared mailbox for your organization, for example *expenses\@contoso.com*. Expense users can then forward receipts, scans, and PDFs to that address, and the agent processes them automatically.

Setting up the shared mailbox for the expense agent works the same way as for other Business Central agents. For detailed instructions, see [Set up the Sales Order Agent](https://learn.microsoft.com/dynamics365/business-central/sales-order-agent-setup).

## To open expense agent setup

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Agent Setup**, and then choose the related link.

The **Expense Agent Setup** page contains all configuration settings organized into the following groups.

## To apply default settings

We recommend starting with the provided default configuration, then adjusting it to match your organization's needs.

1. On the **Expense Agent Setup** page, choose **More options** > **Apply default settings**.

This creates a baseline setup with default categories, rules, and other master data.

## To enable the expense agent

The expense agent monitors an email mailbox and can automatically create expenses from incoming emails, such as receipt confirmations and credit card statements.

1. On the **Expense Agent Setup** page, turn on the **Enable Agent** toggle.
2. In the **Mailbox Account** field, choose the email account that the agent should monitor. You need permission to the mailbox to activate the agent.
3. In the **Agent Access Control** FastTab, select which users are permitted to use agent capabilities.

> [!NOTE]
> Before you can enable the agent, you must accept the privacy notice and make sure the **Expense Agent** capability is active on the **Copilot & Agent Capabilities** page.

## To configure general settings

The **General** FastTab on the **Expense Agent Setup** page includes additional fields:

- **Exchange Rate for Expenses** — Controls whether foreign currency expenses use the rate from the expense date or the posting date.
- **Allow Grouping of Transactions in Report** — Determines whether similar transactions are grouped together in expense reports automatically by the agent.
- **Expense Report Grouping** — Defines how reports are grouped, for example by period.
- **Expense Report Rounding Precision** — Sets rounding precision for report amounts.
- **Expense Report Rounding Type** — Rounding behavior: **Nearest**, **Up**, or **Down**.
- **Receipt No. Mandatory** — Requires entry of a receipt number for every expense.
- **Merchant Name Mandatory** — Requires entry of a merchant name for every expense.

## To configure rules and controls

Use the **Rule & Controls** FastTab to define expense policies.

1. Turn on **Apply Rules** to enforce expense management rules during submission.
2. Set **Do Not Allow Expenses Older Than** to restrict how far back expenses can be dated (for example, `-90D` for 90 days).
3. In **If Expense Is Older Than Allowed**, choose what happens when an expense falls outside that range: **Warn**, **Require Justification**, or **Block Submission**.
4. Turn on **Check Category/Subcategory Usage** to require that expenses use valid category and subcategory combinations during entry.
5. Turn on **Display Anti-Corruption Attestation** if your organization requires an attestation message that users must confirm before submitting expenses.
6. Turn on **Enable Approval Workflow** to require manager approval before reports can be posted (recommended).

## To set up number series

In the **Number Series** section, assign number series for the following:

- **Expense User Nos.** — Automatic numbering for expense users.
- **Expense Reports Nos.** — Automatic numbering for expense reports.
- **Posted Expense Reports Nos.** — Automatic numbering for posted reports.
- **Expense Nos.** — Automatic numbering for individual expenses.

## To set up posting groups

Expense management uses two types of posting groups to control how entries are posted to the general ledger.

### Employee posting groups

Assign employee posting groups to employees. They control how amounts related to the expense report header (reimbursements, prepayments) are posted. In addition to the standard fields, configure the following:

- **Expense Payable Cash Account** — The G/L account for expenses paid personally by the employee and due for reimbursement.
- **Expense Payable Bank Paid Account** — The G/L account for expenses paid directly by the company through its bank accounts.
- **Expense Payable Card Paid Account** — The G/L account for company credit card transactions that aren't reimbursed to the employee.
- **Expense Prepayment Account** — The G/L account for cash advances or prepayments issued to the employee.

### Expense posting groups

Assign expense posting groups to expense categories. They control how individual expense lines are posted. Configure the following:

- **Refundable Debit Account** — The G/L account for posting refundable expense amounts.
- **Prepayment Credit Account** — The G/L account for crediting prepayments when applied to expenses.
- **Expense Debit Rounding Account** — The G/L account for debit rounding adjustments.
- **Expense Credit Rounding Account** — The G/L account for credit rounding adjustments.

## To configure notification settings

When the agent is enabled, you can configure reminders about open expense reports.

1. In the **Communication** section, turn on **Enable Open Report Notification**.
2. Choose a notification frequency: **Weekly**, **Monthly**, or **Custom**.
3. For weekly notifications, choose the day of the week in the **Notification Day of Week** field.
4. For monthly notifications, specify the day in **Notification Day in a Month**.
5. For custom schedules, enter a date formula in the **Custom Notification Formula** field.

## To manage agent access control

The **Agent Access Control** FastTab on the setup page lets you specify which users can configure the agent and which users the agent can work on behalf of. When you enable the agent, the current user is automatically added to the access control list.

## Related information

[Set up expense categories and rules](expense-management-categories-rules.md)  
[Set up expense users and teams](expense-management-users-teams.md)  
[Set up per diem and mileage allowances](expense-management-per-diem-mileage.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
