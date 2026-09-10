---
title: Deferral Summary - Sales (report)
description: Analyze deferred sales revenue by customer and period, showing recognized and remaining amounts as of a chosen balance date.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1701_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Deferral Summary - Sales (report)

The **Deferral Summary - Sales** report summarizes sales deferral activity by customer. It lists each posted deferral line with its posting date, document number and type, line description, deferral account, deferral start date, number of periods, and the amounts recognized, remaining, and total deferred as of a specified balance date. It draws data from posted deferral headers linked to posted sales invoices, credit memos, and return receipts. It provides subtotals per customer along with grand totals for recognized, remaining, and total deferred amounts.

You can filter the report by customer number to limit results to specific customers, by document number to focus on particular sales documents, and by the Balance as of date to control which posting dates are counted as recognized versus remaining. You can also choose to print each customer on a new page. Use the **Hide Zero Remaining Amounts** option to suppress deferral headers with a zero remaining balance unless they close out within the current accounting period.

## Use cases

[!INCLUDE [report-1701-scenario](../includes/report-1701-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile deferred sales revenue balances against the general ledger as of a specific balance date.
* Review recognized versus remaining deferred amounts for each customer and document.
* Identify deferral headers with zero remaining balances that fall outside the current accounting period by using the **Hide Zero Remaining Amounts** option.
* Verify deferral start dates and number of periods used for revenue recognition schedules.
Accounting managers can use the report to:

* Audit deferral activity across posted invoices, credit memos, and return receipts for accuracy.
* Analyze deferred revenue trends by customer to support period-end close procedures.
* Export the report to Excel for further analysis of deferral accounts and recognition patterns.

## Try the report

Try the report here: [Deferral Summary - Sales](https://businesscentral.dynamics.com?report=1701)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
