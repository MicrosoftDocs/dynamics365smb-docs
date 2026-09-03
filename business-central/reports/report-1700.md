---
title: Deferral Summary - G/L (report)
description: Analyze how deferral entries impact general ledger accounts over time and reconcile deferred balances as of a specific date.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1700_Primary
ms.date: 2026-09-03
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 2026-09-03
ai.usage: ai-assisted
---

# Deferral Summary - G/L (report)

The **Deferral Summary - G/L** report shows posted deferral activity for G/L accounts, breaking down each deferral schedule into the amount recognized and the amount still deferred as of a selected balance date. For each posted deferral line, it displays the posting date, document type and number, deferral account, deferral start date, and number of periods, along with the amount recognized, the remaining amount deferred, and the total amount to defer. The report includes subtotals per G/L account and grand totals across all selected accounts.

You can filter the report by G/L account number to limit the analysis to specific accounts, and set the Balance as of date to determine which posted deferral amounts count as recognized versus remaining. You can also choose to print each G/L account on a new page when multiple accounts are included, and use the Hide Zero Remaining Amounts option to suppress deferral headers whose remaining amount is zero, unless the deferral ends within the current accounting period based on the balance date.

## Use cases

[!INCLUDE [report-1700-scenario](../includes/report-1700-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile the total deferred balance for a G/L account against the general ledger as of a specific date.
* Identify how much of each deferral schedule has been recognized versus what remains to be recognized in future periods.
* Review deferral start dates and number of periods to verify that deferral schedules are set up as expected.
* Use the Hide Zero Remaining Amounts option to focus only on deferrals that still have an open balance.,Accountants performing period-end close can use the report to:

* Verify that deferral amounts recognized through the balance date match expected recognition patterns before closing a period.
* Trace individual posted documents and their associated deferral accounts to investigate discrepancies.
* Export the report to Excel for further analysis or to support audit documentation of deferred revenue and expenses.

## Try the report

Try the report here: [Deferral Summary - G/L](https://businesscentral.dynamics.com?report=1700)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
