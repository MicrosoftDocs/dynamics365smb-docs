---
title: Deferral Summary - Purchasing (report)
description: Review deferred purchase expenses by vendor and posting period to verify accrual accuracy.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1702_Primary
ms.date: 2026-09-03
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 2026-09-03
ai.usage: ai-assisted
---

# Deferral Summary - Purchasing (report)

The **Deferral Summary - Purchasing** report lists posted purchase deferral entries by vendor, showing the posting date, document, line type and description, deferral account, deferral start date, and number of periods for each deferral schedule. It calculates the amount recognized up to a chosen balance date, the remaining amount still deferred, and the total amount originally deferred, with subtotals per vendor and a grand total for the report.

You can filter the report by vendor number to limit results to specific vendors, by document number to focus on particular purchase invoices or credit memos, and by the Balance as of date to control which posted deferral amounts count as recognized versus remaining. You can also choose to start each vendor on a new page and hide lines where the remaining deferred amount is zero, unless the deferral schedule closes within the current accounting period.

## Use cases

[!INCLUDE [report-1702-scenario](../includes/report-1702-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile purchasing deferral balances against the general ledger as of a chosen balance date.
* Verify that recognized and remaining deferred amounts are accurate before closing an accounting period.
* Identify vendors with open deferral schedules that still have remaining amounts to recognize.
* Confirm that credit memos and return receipts correctly reverse previously deferred purchase amounts.,Accounts payable clerks can use the report to:

* Look up the deferral account, start date, and number of periods tied to a specific purchase document.
* Filter by vendor or document number to investigate a single deferral schedule in detail.
* Check line-level descriptions and types to confirm which purchase lines are being deferred.

## Try the report

Try the report here: [Deferral Summary - Purchasing](https://businesscentral.dynamics.com?report=1702)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
