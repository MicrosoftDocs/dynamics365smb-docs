---
title: Deferral Summary - Sales (report)
description: Analyze deferred sales revenue by customer and accounting period to reconcile recognized and remaining amounts.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1701_Primary
ms.date: 2026-09-03
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 2026-09-03
ai.usage: ai-assisted
---

# Deferral Summary - Sales (report)

The **Deferral Summary - Sales** report shows deferred revenue from posted sales documents, broken down by customer, document, and deferral schedule. For each posted deferral line, it shows the amount already recognized as of a chosen balance date, the amount still remaining to be deferred, and the total amount originally deferred, letting you track how revenue recognition is progressing across accounting periods.

You can filter the report by customer number and document number to narrow the results to specific customers or transactions, and by the Balance as of date to control which posting dates are treated as recognized versus still deferred. You can also choose to print each customer on a new page, and hide posted deferral headers with a zero remaining amount unless the deferral ends within the current accounting period based on the Balance as of date.

## Use cases

[!INCLUDE [report-1701-scenario](../includes/report-1701-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile deferred sales revenue balances as of a specific accounting date before closing a period.
* Review recognized versus remaining deferred amounts for individual customers or documents.
* Identify deferral schedules that are ending in the current accounting period and confirm they've fully recognized their amounts.
* Verify deferral accounts and start dates used on posted sales invoices and credit memos.,Accountants and auditors can use the report to:

* Trace how a specific posted invoice or credit memo's deferred amount is being recognized period by period.
* Confirm that reversed amounts from credit memos and return receipts are reflected correctly in the deferral totals.
* Export the report to Excel to analyze deferral recognition patterns across customers and periods.

## Try the report

Try the report here: [Deferral Summary - Sales](https://businesscentral.dynamics.com?report=1701)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
