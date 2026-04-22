---
title: Expense Management Overview in Business Central
description: Learn about expense management in Business Central, including how to capture expenses, create reports, get approvals, and post to the general ledger.
author: brentholtorf
ms.topic: overview
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6903, 6933, 6987, 6989, 6997
---

# Manage employee expenses

[!INCLUDE[prod_short](includes/prod_short.md)] includes an *expense management* module that helps organizations track, review, approve, and reimburse business expenses. Whether employees travel, entertain clients, or pay for supplies, the module gives everyone a clear, auditable process from receipt to ledger entry.

## Who is expense management for?

Expense management involves three roles:

- **Expense users** — Employees who incur expenses and submit expense reports for reimbursement.
- **Managers** — People who review and approve or reject expense reports submitted by their team.
- **Administrators** — People who set up expense categories, rules, approval workflows, and posting groups.

## Key concepts

The following concepts are central to how expense management works.

### Expenses

An *expense* is a single business cost, such as a hotel stay, a meal, or a taxi ride. Each expense has a category, date, amount, and optionally a receipt attachment. You can also add participants, itemizations, and mileage or per diem details depending on the category.

### Expense reports

An *expense report* groups one or more expenses into a single document for submission. After you add expenses to a report, you release it and submit it for approval (if approval workflows are enabled). Once approved, the report can be posted to the general ledger.

### Expense report statuses

Expense reports move through these statuses:

- **Open** — The report is being prepared. You can add or remove expenses.
- **Pending Approval** — The report was submitted and is waiting for a manager's decision.
- **Released** — The report was released for processing.
- **Approved** — A manager approved the report. It's ready to post.
- **Rejected** — A manager rejected the report. The submitter can make changes and resubmit.
- **Processed for Payment** — The report was posted and payment processing started.
- **Completed** — Reimbursement is complete.

### Expense categories and rules

*Expense categories* classify expenses by type, such as meals, travel, or office supplies. Administrators can configure categories with default payment methods, posting groups, and detail requirements like itemization or per diem.

*Expense rules* enforce company policy automatically. A rule defines conditions based on category and location — for example, requiring justification for meals above a certain amount, or restricting which merchants are allowed.

### Per diem and mileage

For travel expenses, the module supports *per diem* allowances and *mileage* reimbursement. Administrators configure rates, calculation methods, and partial-day rules in the setup.

## Expense management role center

The **Expense Management** role center is the main navigation hub. From here, you can access:

- **Expenses** — View and manage individual expenses.
- **Expense Reports** — Create and submit expense reports.
- **Posted Expense Reports** — View reports that were posted to the general ledger.
- **Expense Ledger Entries** — Review posted expense entries.
- **Setup** — Configure categories, rules, users, teams, and posting groups.

## Get started

To start using expense management, an administrator must first set up the module. The following articles walk you through each step:

| To do this | See |
|---|---|
| Configure expense management settings, number series, and posting groups | [Set up expense management](expense-management-setup.md) |
| Create expense categories and define policy rules | [Set up expense categories and rules](expense-management-categories-rules.md) |
| Add expense users and organize them into teams | [Set up expense users and teams](expense-management-users-teams.md) |
| Configure per diem rates and mileage reimbursement | [Set up per diem and mileage allowances](expense-management-per-diem-mileage.md) |
| Record a new expense with receipt and details | [Create and manage expenses](expense-management-create-expenses.md) |
| Group expenses into a report and submit for approval | [Create and submit expense reports](expense-management-submit-report.md) |
| Review and approve or reject submitted reports | [Approve expense reports](expense-management-approve-reports.md) |
| Post approved reports to the general ledger | [Post expense reports](expense-management-post-reports.md) |
| Learn how the expense agent processes emails | [How the expense agent processes emails](expense-management-agent.md) |

## Related information

[Manage expenses with Expense Agent web app](expense-agent-overview.md)  
[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
