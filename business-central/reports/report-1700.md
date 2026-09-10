---
title: Deferral Summary - G/L (report)
description: Analyze how deferral entries affect general ledger accounts over time and reconcile recognized versus remaining deferred amounts as of a specific date.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_1700_Primary
ms.date: 09/10/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 09/10/2026
ai.usage: ai-assisted
---

# Deferral Summary - G/L (report)

The **Deferral Summary - G/L** report shows posted deferral entries linked to general ledger accounts. It summarizes how deferral amounts are recognized over time. For each posted deferral header, it displays the posting date, document type and number, deferral account, deferral start date, and number of periods. It also shows the amount recognized as of the specified balance date, the remaining amount deferred, and the total amount to defer. Totals are calculated per G/L account and for the report as a whole, giving finance teams a clear view of outstanding deferrals at any point in time.

You can filter the report by G/L account number to limit the analysis to specific accounts, and by the Balance as of date to determine which posting dates count as recognized versus remaining deferred amounts. You can also choose to start each G/L account on a new page when printing multiple accounts. Enable the **Hide Zero Remaining Amounts** option to suppress posted deferral headers whose remaining amount is zero, unless the deferral reaches zero within the current accounting period based on the balance date.

## Use cases

[!INCLUDE [report-1700-scenario](../includes/report-1700-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile deferred revenue or expense balances on G/L accounts as of a period-end or any chosen balance date.
* Review how much of each deferral is recognized versus how much remains outstanding.
* Use the **Hide Zero Remaining Amounts** option to focus only on deferrals that still require attention.
* Verify that deferral schedules align with posted G/L entries before closing an accounting period.
Accountants can use the report to:

* Trace individual posted deferral headers back to their source document type and number.
* Check the deferral start date and number of periods to confirm recognition schedules are correct.
* Print or export account-by-account deferral details, with each G/L account starting on a new page if needed.

## Try the report

Try the report here: [Deferral Summary - G/L](https://businesscentral.dynamics.com?report=1700)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
