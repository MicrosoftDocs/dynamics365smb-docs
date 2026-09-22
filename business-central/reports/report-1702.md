---
title: Deferral Summary - Purchasing (report)
description: Review deferred purchasing expenses by vendor and posting period to verify accrual accuracy.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1702_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Deferral Summary - Purchasing (report)

The **Deferral Summary - Purchasing** report summarizes purchasing deferral activity by vendor and period. It shows how much of each deferred expense you recognized as of a chosen balance date and how much remains to be recognized in future periods. The report draws on posted deferral headers and lines linked to posted purchase invoices, credit memos, and return receipts. It presents the deferral account, start date, number of periods, line description, and amounts for each transaction, with subtotals per vendor and grand totals across the report.

You can filter the report by vendor number to limit the report to specific vendors, by document number to focus on particular purchase documents, and by the Balance as of date, which determines the cutoff used to split amounts into recognized versus remaining deferred. You can also choose to print each vendor on a new page when reviewing multiple vendors. You can hide posted deferral headers whose remaining amount is zero unless the deferral schedule ends within the current accounting period.

## Use cases

[!INCLUDE [report-1702-scenario](../includes/report-1702-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile deferred expense balances against the general ledger as of month-end or period-end.
* Verify that deferred amounts are being recognized on schedule for accrual accuracy.
* Identify vendors with outstanding remaining deferred amounts that need review before period close.
* Use the **Hide Zero Remaining Amounts** option to focus only on deferrals still active in the current accounting period.
Accounts payable clerks can use the report to:

* Look up deferral details for a specific vendor or purchase document to answer inquiries.
* Confirm the deferral start date and number of periods configured on a posted purchase line.
* Check the total amount deferred versus the amount already recognized for a transaction.

## Try the report

Try the report here: [Deferral Summary - Purchasing](https://businesscentral.dynamics.com?report=1702)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
