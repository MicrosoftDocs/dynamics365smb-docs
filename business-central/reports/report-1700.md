---
title: Deferral Summary - G/L (report)
description: Analyze deferred amounts and recognition patterns for general ledger transactions as of a chosen balance date.
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

The **Deferral Summary - G/L** report shows posted deferral entries for G/L accounts, breaking down each deferral into the amount recognized as of a chosen balance date and the amount still remaining to be deferred. It lists posting date, document type and number, deferral account, deferral start date, and number of periods for each entry, and includes subtotals per account and grand totals for recognized, remaining, and total deferred amounts.

You can filter the report by G/L account number to limit the analysis to specific accounts, by the balance as of date to control the cutoff used to split recognized amounts from remaining deferred amounts, by the New Page per G/L Acc. option to start a new page for each account in printed layouts, and by Hide Zero Remaining Amounts to exclude posted deferral headers whose remaining amount is zero, unless the deferral ends within the current accounting period.

## Use cases

[!INCLUDE [report-1700-scenario](../includes/report-1700-scenario-include.md)]

Controllers and finance teams can use the report to:

* Reconcile deferred balances on G/L accounts against the general ledger as of period end.
* Verify that deferral schedules are recognizing amounts correctly over time.
* Identify deferrals that still have remaining amounts to be recognized in future periods.
* Review deferral activity by account to support month-end or year-end close procedures.,Accountants can use the report to:

* Trace individual deferral entries back to their source document type and number.
* Check the deferral start date and number of periods used to calculate recognition schedules.
* Use the Hide Zero Remaining Amounts option to focus only on deferrals still in progress.

## Try the report

Try the report here: [Deferral Summary - G/L](https://businesscentral.dynamics.com?report=1700)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Finance reports](../finance-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
