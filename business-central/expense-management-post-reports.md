---
title: Post Expense Reports in Business Central
description: Learn how to preview and post approved expense reports to the general ledger and view posted reports and expense ledger entries.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6903, 6910, 6953, 6987, 6998
---

# Post expense reports

After an expense report is approved, you post it to the general ledger. Posting creates ledger entries for each expense line and processes reimbursement. This article explains how to post expense reports and review the results in [!INCLUDE[prod_short](includes/prod_short.md)].

## To preview posting

Before you post, you can review what entries the system will create.

1. Open the **Expense Report** card for the approved report.
2. Choose **Preview Posting**, or press <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>F9</kbd>.

The preview shows the general ledger entries, employee ledger entries, and other entries that will be created. Close the preview when you're done reviewing.

## To post an expense report

1. Open the **Expense Report** card for the approved report.
2. Choose **Post**, or press <kbd>F9</kbd>.
3. Confirm the posting.

After posting, the report moves to the **Posted Expense Reports** list and is no longer editable.

> [!TIP]
> To post and immediately open a new blank expense report, choose **Post and New** instead, or press <kbd>Alt</kbd>+<kbd>F9</kbd>.

## To view posted expense reports

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Expense Reports**, and then choose the related link.
2. Select a posted report to view its details.

The posted report shows all the expense lines, amounts, and dimensions that were recorded at the time of posting. You can also view attached documents and statistics.

## To view expense ledger entries

Posted expense reports create expense ledger entries that you can use for analysis and reconciliation.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Ledger Entries**, and then choose the related link.

The list shows all posted expense entries with details like the expense user, category, amount, posting date, and document number.

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Approve expense reports](expense-management-approve-reports.md)  
[Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
