---
title: Set Up Expense Management in Business Central
description: Learn how to configure expense management settings, including Expense Agent, mailbox, number series, posting groups, and approval workflows.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6976, 6996
---

# Set up expense management

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Before employees can record expenses and submit reports, an administrator must configure expense management features in [!INCLUDE[prod_short](../includes/prod_short.md)]. This article explains the key setup tasks.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Choose your setup path

You can configure Expense Agent in two ways:

- **Assisted setup (recommended)**: Use **Configure Expense Agent** to get started quickly with guided steps and validation checks. Learn more in [Use Expense Agent (recommended)](#use-expense-agent-recommended).
- **Manual setup (advanced)**: Use the **Expense Agent Setup** page to configure each setting directly and fine-tune behavior after initial setup. Learn more in [Access expense management setup](#access-expense-management-setup).

For most organizations, start with assisted setup, and then use this article for detailed settings and ongoing management.

To learn more about the differences of using the agent or not, go to [With and without Expense Agent](expense-management-overview.md#with-and-without-expense-agent).

## Use the provided default settings (recommended)

It's optional, but we recommend that you start with the default configuration that we provide, and then adjust the settings to match your organization's needs. The default settings create a baseline setup with default categories, rules, and other master data.

To apply the default configuration, on the **Expense Agent Setup** page, choose **More options**, and then **Apply default settings**.

## Use Expense Agent (recommended)

Expense Agent is an AI‑powered capability that automates the most time‑intensive parts of expense management. For example, receipt intake, data extraction, categorization, and expense line creation. It accepts receipts from multiple channels, including uploaded images and email submissions, while maintaining a human‑in‑the‑loop review process to ensure accuracy, compliance, and full user oversight. Learn more at [Expense Agent overview](expense-agent.md).

If you haven't configured Expense Agent yet, we recommend that you use assisted setup first. Learn more in [Set up the Expense Agent](expense-agent-configuration-page.md).

## Access expense management setup

The **Expense Agent Setup** page organizes all configuration settings on FastTabs. Except for the settings that are related to Expense Agent, the settings apply to expense management. The following sections describe the settings that are available on each FastTab.

To get started, [!INCLUDE [open-search-lowercase](../includes/open-search-lowercase.md)], enter **Expense Agent Setup**, and then choose the related link.

### Configure general settings

The following table describes the settings on the **General** FastTab.

| Field | Description |
| --- | --- |
|**Enable agent**|Specifies whether Expense Agent can process expense submissions from email and the Expense Agent web app.|
|**Mail Account**|Specifies the shared mailbox that the agent monitors. You need permission to the mailbox to activate the agent.|
| **Exchange Rate for Expenses** | Controls whether foreign currency expenses use the rate from the expense date or the posting date. |
| **Allow Grouping of Transactions in Report** | Determines whether similar transactions are grouped together in expense reports automatically by the agent. |
| **Expense Report Grouping** | Defines how reports are grouped, for example by period. |
| **Expense Report Rounding Precision** | Sets rounding precision for report amounts. |
| **Expense Report Rounding Type** | Rounding behavior: **Nearest**, **Up**, or **Down**. |
| **Receipt No. Mandatory** | Requires entry of a receipt number for every expense. |
| **Merchant Name Mandatory** | Requires entry of a merchant name for every expense. |

### Configure rules and controls

The following table describes the settings on the **Rule & Controls** FastTab. These settings define expense policies.

| Field | Description |
| --- | --- |
| **Apply Rules** | Turn on to enforce expense management rules during submission. |
| **Do Not Allow Expenses Older Than** | Restricts how far back expenses can be dated (for example, `-90D` for 90 days). |
| **If Expense Is Older Than Allowed** | Choose what happens when an expense falls outside the allowed range: **Warn**, **Require Justification**, or **Block Submission**. |
| **Check Category/Subcategory Usage** | Turn on to require that expenses use valid category and subcategory combinations during entry. |
| **Display Anti-Corruption Attestation** | Turn on if your organization requires an attestation message that users must confirm before submitting expenses. |
| **Enable Approval Workflow** | Turn on to require manager approval before reports can be posted (recommended). |

To learn more about categories and rules, go to [Set up expense categories and rules](expense-management-categories-rules.md).

### Assign number series

Number series automatically generate unique identification codes for things such as new general ledger accounts, customer and vendor accounts, invoices, and so on. To learn more about number series, go to [Create number series](../ui-create-number-series.md).

On the **Number Series** FastTab, assign number series in the fields described in the following table.

| Field | Description |
| --- | --- |
| **Expense User Nos.** | Automatic numbering for expense users. |
| **Expense Reports Nos.** | Automatic numbering for expense reports. |
| **Posted Expense Reports Nos.** | Automatic numbering for posted reports. |
| **Expense Nos.** | Automatic numbering for individual expenses. |

## Configure notification settings

When the agent is enabled, you can configure reminders about open expense reports on the **Communication** FastTab.

| Field | Description |
| --- | --- |
| **Enable Open Report Notification** | Let [!INCLUDE [prod_short](../includes/prod_short.md)] notify you about open expense reports that might need attention. |
| **Open Report Notification Frequency** | Specify whether to be notified on a weekly, monthly, or custom basis:<br><br>For weekly notifications, choose the day of the week in the **Notification Day of Week** field.<br>For monthly notifications, specify the number of the month in the **Notification Day in a Month** field.<br>For custom schedules, enter a date formula in the **Custom Notification Formula** field. To learn more about date formulas, go to [Use date formulas](../ui-enter-date-ranges.md#use-date-formulas).|

## Manage agent access control

The **Agent Access Control** FastTab lets you specify which users can configure the agent and which users the agent can work on behalf of. When you enable the agent, the current user is automatically added to the access control list.

### Set up posting groups

Posting groups map entities to general ledger accounts. Examples of entities are customers, vendors, items, resources, and sales and purchase documents. Posting groups save time and help avoid mistakes when you post transactions. The transaction values go to the accounts specified in the posting group for that particular entity. To learn more about posting groups in general, go to [Set up posting groups](../finance-posting-groups.md).

Expense management uses two types of posting groups to control how to post entries for expenses to the general ledger.

#### Employee posting groups

Employee posting groups control how amounts related to the expense report header (reimbursements, prepayments) are posted. 

In addition to the standard fields, on the **Employee Posting Group** page, fill in fields described in the following table.

| Field | Description |
| --- | --- |
| **Expense Payable Cash Account** | The G/L account for expenses paid personally by the employee and due for reimbursement. |
| **Expense Payable Bank Paid Account** | The G/L account for expenses paid directly by the company through its bank accounts. |
| **Expense Payable Card Paid Account** | The G/L account for company credit card transactions that aren't reimbursed to the employee. |
| **Expense Prepayment Account** | The G/L account for cash advances or prepayments issued to the employee. |

The next step is to assign the group to employees who submit expenses. On the **Employees** page, fill in the **Employee Posting Group** field.

#### Expense posting groups

Expense posting groups control how to post individual expense lines. In addition to standard fields, on the **Expense Posting Group** page, fill in the fields described in the following table.

| Field | Description |
| --- | --- |
| **Refundable Debit Account** | The G/L account for posting refundable expense amounts. |
| **Prepayment Credit Account** | The G/L account for crediting prepayments when applied to expenses. |
| **Expense Debit Rounding Account** | The G/L account for debit rounding adjustments. |
| **Expense Credit Rounding Account** | The G/L account for credit rounding adjustments. |

The next step is to assign the group to expense categories. On the **Expense Categories** page, fill in the **Posting group** field.

## Set up approval workflows

> [!NOTE]
> You only need to set up a workflow if you aren't using Expense Agent. The agent automatically uses a newer way to handle workflows, so you can skip this step.

Administrators configure approval workflows on the **Expense Agent Setup** page.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Agent Setup**, and then choose the related link.
1. Turn on **Enable Approval Workflow**.
1. To configure approver assignments, [!INCLUDE [open-search-lowercase](../includes/open-search-lowercase.md)], enter **Expense Approvals Setup**, and then choose the related line.
1. On the **Expense Approval Setup** page, fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](../includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> When the approval workflow is enabled, managers can only view reports where they're assigned as the approver, unless they have **Unlimited Expense Approval** permission.

## Related information

[Set up expense categories and rules](expense-management-categories-rules.md)  
[Set up expense users and teams](expense-management-users-teams.md)  
[Set up per diem and mileage allowances](expense-management-per-diem-mileage.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
