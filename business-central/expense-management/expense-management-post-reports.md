---
title: Post Expense Reports in Business Central
description: Learn how to verify VAT reclaim decisions, preview and post approved expense reports, and review the entries and documents created by posting.
author: brentholtorf
ms.topic: how-to
ms.date: 09/26/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6903, 6910, 6953, 6987, 6998
ai-usage: ai-assisted
---

# Post expense reports

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After an expense report is approved, you post it to the general ledger. Posting creates ledger entries for each expense line and processes reimbursement. This article explains how to post expense reports and review the results in [!INCLUDE[prod_short](../includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Verify VAT reclaim decisions

If VAT reclaim is enabled, confirm that an accountant reviewed every VAT specification line before you post the report. Each line must have a reclaim status of **Approved** or **Rejected**.

1. Open the expense report.
1. Select an expense report line, and then choose **VAT Specification**.
1. Confirm that no VAT specification line has the **Pending** reclaim status.

If a line is pending, [!INCLUDE [prod_short](../includes/prod_short.md)] blocks posting and provides an action that opens the VAT specification. An accountant can then approve or reject the reclaim. Learn more in [Review VAT reclaim](expense-management-approve-reports.md#review-vat-reclaim).

## Preview posting

Before you post, you can review what entries [!INCLUDE [prod_short](../includes/prod_short.md)] creates.

1. Open the **Expense Report** card for the approved report.
1. Choose **Preview Posting**, or press <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>F9</kbd>.

The preview shows the general ledger entries, employee ledger entries, and other entries in the report. If expenses link to projects, the preview also shows project ledger entries. For expense lines linked to travel requests, **Posted to G/L Preview** shows the relationship to the expected costs. Close the preview when you're done reviewing.

## Post an expense report

1. Open the **Expense Report** card for an approved report.
1. Select **Post**, or press <kbd>F9</kbd>.
1. Confirm the posting.

After you post a report, it moves to the **Posted Expense Reports** list and is no longer editable. Learn more in [What posting creates](#what-posting-creates).

> [!TIP]
> To post and immediately open a new blank expense report, choose **Post and New** instead, or press <kbd>Alt</kbd>+<kbd>F9</kbd>.

If expense report lines are linked to travel requests, posting records the actual spending against each request. If a line is marked to close the related request, posting closes the approved request and stores the closing document number.

## View posted expense reports

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Posted Expense Reports**, and then choose the related link.
1. Select a posted report to view its details.

The posted report shows all the expense lines, amounts, and dimensions that were recorded at the time of posting. You can also access attached documents and statistics.

## Review posted VAT totals

If the report contains VAT specifications, use its statistics to review the VAT amounts retained for reporting and audit.

1. Open the posted expense report.
1. Choose **Statistics**.
1. Review **Amount without VAT (LCY)**, **VAT Amount (LCY)**, and **Approved Reclaim VAT (LCY)**.
1. In the **VAT Specification** section, review the category or subcategory, VAT rate, VAT base, VAT amount, reclaim percentage, reclaim amount, and reclaim status for each VAT specification.

The statistics show totals in local currency. When the report uses a reimbursement currency, the VAT specification also shows the total, VAT base, VAT amount, and reclaim amount in that currency.

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
| **VAT entries** | Records the VAT base and amount for approved reclaims according to the reclaim percentage and VAT posting setup. A rejected reclaim doesn't create a VAT entry. |
| **Project ledger entries** | Created only for expense lines that have a **Project No.** and **Project Task No.** assigned. |
| **Posted to G/L links** | Created only for expense lines that are linked to travel requests. These entries help track actual posted spending against the total expected amount. |
| **Sales invoices** | Created automatically for expense lines marked as **Billable** to a customer. |
| **Posted policy evaluations** | Records current policy evaluation results that correspond to the evaluated expense version and current policy. Earlier or superseded results aren't copied to the posted report. |

The posted expense report retains the VAT specification, including the VAT rate, VAT base, VAT amount, reclaim percentage, reclaim amount, decision, and the user and time associated with the decision.

## Next steps

[Manage employee expenses](expense-management-overview.md)

## Related information

[Create and submit expense reports](expense-management-submit-report.md)  
[Approve expense reports](expense-management-approve-reports.md)  
[Manage travel requests](expense-management-travel-requisitions.md)
[Record and reimburse employees' expenses](../finance-how-record-reimburse-employee-expenses.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
