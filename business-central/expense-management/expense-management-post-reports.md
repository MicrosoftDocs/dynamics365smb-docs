---
title: Post Expense Reports in Business Central
description: Learn how to preview and post approved expense reports to the general ledger and view posted reports and expense ledger entries.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6903, 6910, 6953, 6987, 6998
ai-usage: ai-generated
---

# Post expense reports

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After an expense report is approved, you post it to the general ledger. Posting creates ledger entries for each expense line and processes reimbursement. This article explains how to post expense reports and review the results in [!INCLUDE[prod_short](../includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Preview posting

Before you post, you can review what entries [!INCLUDE [prod_short](../includes/prod_short.md)] creates.

1. Open the **Expense Report** card for the approved report.
1. Choose **Preview Posting**, or press <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>F9</kbd>.

The preview shows the general ledger entries, employee ledger entries, and other entries in the report. If expenses link to projects, the preview also shows project ledger entries. Close the preview when you're done reviewing.

## Post an expense report

1. Open the **Expense Report** card for an approved report.
2. Choose **Post**, or press <kbd>F9</kbd>.
3. Confirm the posting.

After you post a report, it moves to the **Posted Expense Reports** list and is no longer editable. To learn more about the entries and documents that posting creates, go to [What posting creates](#what-posting-creates).

> [!TIP]
> To post and immediately open a new blank expense report, choose **Post and New** instead, or press <kbd>Alt</kbd>+<kbd>F9</kbd>.

## View posted expense reports

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Posted Expense Reports**, and then choose the related link.
1. Select a posted report to view its details.

The posted report shows all the expense lines, amounts, and dimensions that were recorded at the time of posting. You can also access attached documents and statistics.

## View expense ledger entries

Posted expense reports create expense ledger entries that you can use for analysis and reconciliation.

- [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Ledger Entries**, and then choose the related link.

The list shows all posted expense entries with details like the expense user, category, amount, posting date, and document number.

## What posting creates

When you post an expense report, [!INCLUDE [prod_short](../includes/prod_short.md)] creates the following entries:

| Entry | Description |
|---|---|
| **Expense ledger entries** | One entry per expense line, recording the category, amount, and expense user. |
| **Employee ledger entries** | Records the reimbursable amounts owed to employees who paid out of pocket. |
| **Detailed employee ledger entries** | Records the reimbursable amounts underlying breakdown. |
| **G/L entries** | Posts expense amounts to the appropriate general ledger accounts based on the posting groups. |
| **Project ledger entries** | Created only for expense lines that have a **Project No.** and **Project Task No.** assigned. |
| **Sales invoices** | Created automatically for expense lines marked as **Billable** to a customer. |

## Next steps

[Manage employee expenses](expense-management-overview.md)

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Approve expense reports](expense-management-approve-reports.md)  
[Record and reimburse employees' expenses](../finance-how-record-reimburse-employee-expenses.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
