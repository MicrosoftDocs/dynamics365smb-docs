---
title: Expense Management Overview
description: Learn about expense management in Business Central, including how to capture expenses, create reports, get approvals, and post to the general ledger.
author: brentholtorf
ms.topic: overview
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6903, 6933, 6987, 6989, 6997
---

# Manage employee expenses

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

[!INCLUDE[prod_short](../includes/prod_short.md)] includes expense management features that help organizations track, review, approve, and reimburse business expenses. Whether employees travel, entertain clients, or pay for supplies, expense management gives everyone a clear, auditable process from receipt to ledger entry.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## With and without Expense Agent

You can use expense management in two ways:

- With Expense Agent enabled. Expense users submit receipts through a web app, email, or Microsoft 365 Copilot chat. Expense Agent automatically extracts data, categorizes expenses, creates expense records, and groups them into expense reports. You view and edit agent-created expenses inside [!INCLUDE [prod_short](../includes/prod_short.md)]. Learn more at [Expense Agent overview](expense-agent.md).
- Without Expense Agent. Expense users create expense reports in [!INCLUDE [prod_short](../includes/prod_short.md)] and add expense lines manually. Individual expenses aren't available without the agent, and there's no AI-powered receipt scanning, extraction, or automatic categorization. This option is useful in regions where the agent isn't enabled or when you prefer to work entirely in [!INCLUDE [prod_short](../includes/prod_short.md)].

Without the agent, you still have access to:

- Expense report creation, release, and posting
- Itemization, participants, per diem, and mileage on report lines
- Rule validation and approval workflows
- All setup features (categories, rules, posting groups, locations)

> [!TIP]
> We recommend enabling Expense Agent for the full experience. With the agent, expenses are created automatically from receipts, categorized, and grouped into reports. Without the agent, all data entry is manual.

## Who is expense management for?

Expense management involves three roles:

- Expense users who incur expenses and submit expense reports for reimbursement.
- Managers who review and approve or reject expense reports submitted by their team.
- Administrators who set up expense categories, rules, approval workflows, and posting groups.

## Key concepts

The following concepts are central to how expense management works.

### Expenses

An expense is a work-related cost, such as a hotel stay, a meal, or a taxi ride. Each expense has a category, date, amount, and optionally a receipt attachment. You can also add participants, itemizations, and mileage or per diem details depending on the category.

### Expense reports

An expense report groups one or more expenses into a single document for submission. After you add expenses to a report, submit it for approval (if approval workflows are enabled). After the report is approved, you can post it to the general ledger.

### Expense report statuses

Expense reports move through these statuses.

| Status | Description |
| --- | --- |
| Open | The report is being prepared. You can add or remove expenses. |
| Pending Approval | The report was submitted and is waiting for a manager's decision. |
| Released | The report was released for processing. |
| Approved | A manager approved the report. It's ready to post. |
| Rejected | A manager rejected the report. The submitter can make changes and resubmit. |
| Processed for Payment | The report was posted and payment processing started. |
| Completed | Reimbursement is complete. |

### Expense categories and rules

Expense categories classify expenses by type, such as meals, travel, or office supplies. Administrators can configure categories with default payment methods, posting groups, and detail requirements like itemization or per diem.

Expense rules enforce company policy automatically. A rule defines conditions based on category and location — for example, requiring justification for meals above a certain amount, or restricting which merchants are allowed.

Learn more at [Set up expense categories and rules](expense-management-categories-rules.md).

### Refundable versus reimbursable

Understanding the difference between *refundable* and *reimbursable* is important:

- **Refundable** means the expense complies with company policy and is eligible for processing. Non-refundable expenses (such as personal charges on a hotel bill) aren't posted to the general ledger.
- **Reimbursable** means the employee paid personally and is owed money. An expense paid by company credit card is refundable but not reimbursable, because the company already covered the cost.

A single receipt can be partially refundable. For example, a hotel bill with three refundable line items and one non-refundable minibar charge results in a partial reimbursement. Administrators set the default refundable status on expense categories and subcategories.

### Per diem and mileage

For travel expenses, expense management supports *per diem* allowances and *mileage* reimbursement. Administrators configure rates, calculation methods, and partial-day rules in the setup. Learn more at [Set up per diem and mileage allowances](expense-management-per-diem-mileage.md).

## Expense Management role center

The **Expense Management** role center is the main navigation hub. From here, you can access:

- **Expenses** — View and manage individual expenses.
- **Expense Reports** — Create and submit expense reports.
- **Posted Expense Reports** — View reports that were posted to the general ledger.
- **Expense Ledger Entries** — Review posted expense entries.
- **Setup** — Configure categories, rules, users, teams, and posting groups.

## Licensing requirements

The license you need depends on how you interact with expense management:

| How you use expense management | License required |
| --- | --- |
| Submit expenses through the web app, email, or Microsoft 365 Copilot chat only (no [!INCLUDE [prod_short](../includes/prod_short.md)] access) | No [!INCLUDE [prod_short](../includes/prod_short.md)] license. You're charged based on Copilot credits. |
| Manage expenses and submit expense reports inside [!INCLUDE [prod_short](../includes/prod_short.md)] | Team Member license (minimum) |
| Approve expense reports inside [!INCLUDE [prod_short](../includes/prod_short.md)] | Team Member license (minimum) |
| Post expense reports and process payments in [!INCLUDE [prod_short](../includes/prod_short.md)] | Essentials or Premium license |

> [!NOTE]
> Expense users who work exclusively through the Expense Agent web app or email don't need a [!INCLUDE [prod_short](../includes/prod_short.md)] license. They can also approve reports through the web app without a [!INCLUDE [prod_short](../includes/prod_short.md)] license. However, if a user signs in to [!INCLUDE [prod_short](../includes/prod_short.md)] to perform any expense task, they must have at least a Team Member license.

## Related information

[Manage expenses with Expense Agent web app](expense-agent-overview.md)  
[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
