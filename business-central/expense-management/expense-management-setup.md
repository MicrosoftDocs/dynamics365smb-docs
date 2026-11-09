---
title: Set Up Expense Management in Business Central
description: Learn how to configure Expense Agent, policies, payment methods, posting groups, VAT reclaim, and approval workflows for expenses in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 11/04/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6976, 6996, 7127
ai-usage: ai-assisted
---

# Set up expense management

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Before employees can record expenses and submit reports, an administrator must configure expense management features in [!INCLUDE[prod_short](../includes/prod_short.md)]. This article explains the key setup tasks.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Choose your setup path

Use these pages for different parts of setup:

- **Assisted setup (recommended)**: Use **Configure Expense Agent** for guided setup and validation checks. Activate or deactivate the agent and configure receipt submission, AI-assisted policy evaluation, communication, and project tracking. Learn more in [Use Expense Agent (recommended)](#use-expense-agent-recommended).
- **Manual setup (advanced)**: Use **Expense Management Setup** to configure accounting defaults, expense rules, numbering, and other expense management settings. This page doesn't replace assisted setup for agent-specific settings. Learn more in [Access expense management setup](#access-expense-management-setup).

For most organizations, start with assisted setup, and then use this article for detailed settings and ongoing management.

Learn more in [With and without Expense Agent](expense-management-overview.md#with-and-without-expense-agent).

## Configure AI-assisted policy evaluation

Use **Configure Expense Agent** assisted setup to control AI-assisted policy evaluation. The corresponding fields on the **Expense Agent Setup** page are hidden and obsolete.

1. [!INCLUDE [open-search](../includes/open-search.md)], enter **Configure Expense Agent**, and then select the related link.
1. Go to **Policy compliance**.
1. Turn on **Evaluate compliance with AI** to let Expense Agent evaluate applicable natural-language policies. Policy evaluations use additional AI credits.
1. Under **Enable pre-submission evaluation**, record whether your organization allows submitters to evaluate draft expense reports before submission.
1. Select **Update**.

The pre-submission preference doesn't change how Business Central applies deterministic expense rules. To create policies and control which expenses they apply to, go to [Create and manage expense policies](expense-management-categories-rules.md#create-and-manage-expense-policies).

## Use the provided default settings (recommended)

It's optional, but we recommend that you start with the default configuration that we provide, and then adjust the settings to match your organization's needs. The default settings create a baseline setup with default categories, rules, and other master data.

To apply the default configuration, on the **Expense Management Setup** page, choose **More options**, and then **Apply default settings**.

## Use Expense Agent (recommended)

Expense Agent is an AI‑powered capability that automates the most time‑intensive parts of expense management. For example, receipt intake, data extraction, categorization, and expense line creation. It accepts receipts from multiple channels, including uploaded images and email submissions, while maintaining a human‑in‑the‑loop review process to ensure accuracy, compliance, and full user oversight. Learn more in [Expense Agent overview](expense-agent.md).

If you haven't configured Expense Agent yet, we recommend that you use assisted setup first. Learn more in [Set up the Expense Agent](expense-agent-configuration-page.md).

### Configure activation and receipt submission

Use **Configure Expense Agent** for the following settings. The corresponding controls on **Expense Management Setup** are hidden.

| Setting | Description |
| --- | --- |
| **Active** | Activates Expense Agent to process expense submissions. Turn off to deactivate the agent. |
| **Enable sending email with receipts** | Specifies whether the agent reads its mailbox and processes incoming emails containing expense receipts. This option is under **Access and submission**. |
| **Account** under **Enable sending email with receipts** | Specifies the mailbox that the agent monitors. You need permission to the mailbox to activate email-based receipt submission. |

Configure incoming receipt processing and outgoing email separately. To send notifications, also [configure notification settings](#configure-notification-settings).

## Access expense management setup

The **Expense Management Setup** page organizes expense management settings on FastTabs. Use this page for accounting and expense controls. Configure agent activation, receipt submission, communication, and project tracking through **Configure Expense Agent**.

To get started, [!INCLUDE [open-search-lowercase](../includes/open-search-lowercase.md)], enter **Expense Management Setup**, and then choose the related link.

### Configure general settings

The following table describes the settings on the **General** FastTab.

| Field | Description |
| --- | --- |
| **Exchange Rate for Expenses** | Controls whether foreign currency expenses use the rate from the expense date or the posting date. |
| **Allow prepayment-cash advance** | Specifies whether prepayments and cash advances are allowed. |
| **Allow Grouping of Transactions in Report** | Determines whether similar transactions are grouped together in expense reports automatically by the agent. |
| **Expense Report Rounding Precision** | Sets rounding precision for report amounts. |
| **Expense Report Rounding Type** | Rounding behavior: **Nearest**, **Up**, or **Down**. |
| **Default Payment Methods Applied** | Indicates whether default payment methods have been applied (read-only). |
| **Default Posting Groups Applied** | Indicates whether default posting groups have been applied (read-only). |
| **Default No. Series Applied** | Indicates whether default number series have been applied (read-only). |
| **Default Exp. Categories Applied** | Indicates whether default expense categories have been applied (read-only). |
| **Default Exp. Locations Applied** | Indicates whether default expense locations have been applied (read-only). |
| **Default Management Rules Applied** | Indicates whether default management rules have been applied (read-only). |
| **Create Employees for Expense Users** | Specifies whether Employees should be automatically created from Expense Users when no matching Employee exists. Employees and their connection with Expense Users are critical for correct processing and posting in Expense Agent, but this setting may impact your HR data.|
| **Allow VAT Reclaim** | Specifies whether VAT reclaim is allowed on expenses. |
| **Default VAT Bus. Posting Group** | Specifies the default VAT business posting group for expenses. |
| **Default VAT Rates Applied** | Indicates whether the default VAT rates for the company's country or region have been applied (read-only). |

### Configure rules and controls

The following table describes the settings on the **Rule & Controls** FastTab. These settings control expense rules and required expense details. Configure AI-assisted policy evaluation through **Configure Expense Agent**, as described in [Configure AI-assisted policy evaluation](#configure-ai-assisted-policy-evaluation).

| Field | Description |
| --- | --- |
| **Receipt No. Mandatory** | Requires entry of a receipt number for every expense. |
| **Merchant Name Mandatory** | Requires entry of a merchant name for every expense. |
| **Apply Rules** | Turn on to enforce expense management rules during submission. |
| **Do Not Allow Expenses Older Than** | Restricts how far back expenses can be dated (for example, `-90D` for 90 days). |
| **If Expense Is Older Than Allowed** | Choose what happens when an expense falls outside the allowed range: **Warn**, **Require Justification**, or **Block Submission**. This field is hidden by default.|
| **Check Category/Subcategory Usage** | Turn on to require that expenses use valid category and subcategory combinations during entry. |
| **Display Anti-Corruption Attestation** | Turn on if your organization requires an attestation message that users must confirm before submitting expenses. |

To learn how to create rules and policies, go to [Set up expense categories, rules, and policies](expense-management-categories-rules.md). To learn how Business Central applies rules and Expense Agent evaluates policies, go to [How expense policy and rules compliance work](expense-agent-policy-compliance.md).

### Configure approval settings

The following settings are on the **Approval** FastTab.

| Field | Description |
| --- | --- |
| **Use traditional approval workflow** | Turn on to require manager approval before expense reports can be posted when Expense Agent isn't enabled. Expense Agent provides its own approval process. |
| **Default Approver** | Specifies the expense user assigned as approver by default. |

### Assign number series

Number series automatically generate unique identification codes for things such as new general ledger accounts, customer and vendor accounts, invoices, and so on. Learn more in [Create number series](../ui-create-number-series.md).

On the **Number Series** FastTab, assign number series in the fields described in the following table.

| Field | Description |
| --- | --- |
| **Expense User Nos.** | Automatic numbering for expense users. |
| **Expense Reports Nos.** | Automatic numbering for expense reports. |
| **Posted Expense Reports Nos.** | Automatic numbering for posted reports. |
| **Expense Nos.** | Automatic numbering for individual expenses. |

Travel requests use the underlying spend request numbering. The **Spend Request No. Series** field on the **General Ledger Setup** page is optional. Configure it to use a defined numbering scheme. If you leave it blank, [!INCLUDE [prod_short](../includes/prod_short.md)] derives the next sequential number.

### Configure notification settings

On **Configure Expense Agent**, go to **Communication** to configure outgoing email and reminders about open expense reports. These controls aren't available on **Expense Management Setup**.

Turn on outgoing email and select an **Account** under **Send mail**. This account is required for outgoing messages. The agent doesn't fall back to the mailbox used to receive receipts.

| Field | Description |
| --- | --- |
| **Communication** | Controls whether the agent sends outgoing emails to users. Turning off outgoing email stops welcome emails, reimbursement notifications, approval updates, and open-report reminders. It also turns off the reminder and approval notification options. Incoming receipt processing is controlled separately. |
| **Account** | Specifies the email account for all outgoing Expense Agent messages: welcome emails, pending-approval requests sent to approvers, approved or rejected notifications sent to submitters, reimbursement notifications, and optional open-report reminders. Outgoing email must be enabled and this account must be configured before messages can be sent. |
| **Notify users about unsubmitted reports** | Enables reminders to expense users about open expense reports that might need attention. Outgoing email must also be enabled and an account configured. |
| **Frequency** | Specify whether to send reminders on a weekly, monthly, or custom basis. For weekly reminders, choose **Day of week**. For monthly reminders, specify **Day of month**. For custom schedules, enter a date formula in **Custom formula**. Learn more in [Use date formulas](../ui-enter-date-ranges.md#use-date-formulas). |
| **Day of week** | Specifies the day of the week for weekly open-report reminders. |
| **Day of month** | Specifies the day of the month for monthly open-report reminders. |
| **Custom formula** | Specifies a date formula for the next reminder date based on the last reminder run. For example, use `1D` for one day, `1W` for one week, or `1M` for one month. |
| **Notify users about approval updates** | Specifies whether the agent sends email notifications when expense reports are submitted, approved, or rejected. Outgoing email must also be enabled and an account configured. |

### Configure projects

On **Configure Expense Agent**, go to **Project tracking** to configure the following settings. These controls aren't available on **Expense Management Setup**.

| Field | Description |
| --- | --- |
| **Project tracking** | Specifies whether project and project task fields are visible in the expense web app for submitters. |
| **Project visibility** | Specifies which projects are visible to submitters: only projects assigned to the user, or all active projects. |

### Manage agent access control

The **Agent Access Control** FastTab lets you specify which users can configure the agent and which users the agent can work on behalf of. When you enable the agent, the current user is automatically added to the access control list.

## Set up expense payment methods

Payment methods define how you pay expenses, such as cash, credit card, or company bank account, and determine how to reimburse expenses.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Payment Methods**, and then select the related link.
1. Select **New** and create entries for each payment method your organization uses.

> [!NOTE]
> When you create an expense payment method, you must assign a **Reimbursement Type** (**Employee Paid**, **Credit Card**, or **Company Paid**). Each reimbursement type can be used by only one payment method.

Refundable expenses with the **Employee Paid** reimbursement type are reimbursable because employees pay them out of pocket. Expenses with the **Credit Card** or **Company Paid** reimbursement type aren't reimbursed because the company pays them directly. Nonrefundable company-paid amounts create accounting entries to recover money from the employee and appear as a negative **Reimbursable Amount**.

## Set up posting groups

Posting groups map entities to general ledger accounts. Examples of entities are customers, vendors, items, resources, and sales and purchase documents. Posting groups save time and help avoid mistakes when you post transactions. The transaction values go to the accounts specified in the posting group for that particular entity. Learn more in [Set up posting groups](../finance-posting-groups.md).

Expense management uses two types of posting groups to control how to post entries for expenses to the general ledger.

### Employee posting groups

Employee posting groups control how amounts related to the expense report header (reimbursements, prepayments) are posted. 

In addition to the standard fields, on the **Employee Posting Group** page, fill in fields described in the following table.

| Field | Description |
| --- | --- |
| **Expense Payable Cash Account** | The G/L account for expenses paid personally by the employee and due for reimbursement. |
| **Expense Payable Bank Paid Account** | The G/L account for expenses paid directly by the company through its bank accounts. |
| **Expense Payable Card Paid Account** | The G/L account for company credit card transactions that aren't reimbursed to the employee. |
| **Expense Prepayment Account** | The G/L account for cash advances or prepayments issued to the employee. |

The next step is to assign the group to employees who submit expenses. On the **Employees** page, fill in the **Employee Posting Group** field.

### Expense posting groups

Expense posting groups control how to post individual expense lines. In addition to standard fields, on the **Expense Posting Group** page, fill in the fields described in the following table.

| Field | Description |
| --- | --- |
| **Refundable Debit Account** | The G/L account for posting refundable expense amounts. |
| **Non-Refundable Debit Account** | The G/L account for posting nonrefundable company-paid amounts to recover from the employee. |
| **Prepayment Credit Account** | The G/L account for crediting prepayments when applied to expenses. |
| **Expense Debit Rounding Account** | The G/L account for debit rounding adjustments. |
| **Expense Credit Rounding Account** | The G/L account for credit rounding adjustments. |

The next step is to assign the group to expense categories. On the **Expense Categories** page, fill in the **Posting group** field.

## Set up VAT reclaim

Enable VAT reclaim to let Expense Agent capture VAT from receipts and suggest the amount that your organization can reclaim. The feature uses VAT posting setup together with defaults on expense categories and subcategories. An accountant must approve or reject every pending reclaim suggestion before the related expense report can be posted.

1. On the **Expense Management Setup** page, fill in the **Default VAT Bus. Posting Group** field.
1. Turn on **Allow VAT Reclaim**.
1. Choose **Expense VAT Posting Setup**.
1. Review the combinations of VAT business and product posting groups. Verify their VAT percentages and purchase VAT accounts.

During initial setup, you can choose **Apply default settings** to create VAT rates for the country or region in **Company Information**, when defaults are available. This action sets **DOMESTIC** as the default VAT business posting group if the field is empty. It also creates VAT posting setup and assigns VAT product posting groups, VAT percentages, and a 100 percent reclaim percentage to supported expense categories and subcategories. Review the generated setup and rates before you process expenses.

To control the VAT treatment for specific types of expenses, review the VAT defaults on expense categories and configure exceptions on expense subcategories. Learn more in [Set up expense categories and rules](expense-management-categories-rules.md#configure-vat-defaults-for-categories).

## Set up approval workflows

> [!NOTE]
> You only need to set up a workflow if you aren't using Expense Agent. The agent automatically uses a newer way to handle workflows, so you can skip this step.

Administrators configure approval workflows on the **Expense Management Setup** page.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Management Setup**, and then choose the related link.
1. On the **Approval** FastTab, turn on **Use traditional approval workflow**.
1. To configure approver assignments, [!INCLUDE [open-search-lowercase](../includes/open-search-lowercase.md)], enter **Expense Approvals Setup**, and then choose the related line.
1. On the **Expense Approval Setup** page, fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](../includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> When the approval workflow is enabled, managers can only view reports where they're assigned as the approver, unless they have **Unlimited Expense Approval** permission.

## Next steps

- [Set up expense users and teams](expense-management-users-teams.md)
- [Set up expense categories, rules, and policies](expense-management-categories-rules.md)
- [Set up per diem allowances](expense-management-per-diem-mileage.md)
- [Set up mileage rates for expense management](expense-management-mileage-rate-setup.md)
- [Manage travel requests](expense-management-travel-requisitions.md)

## Related information

[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
