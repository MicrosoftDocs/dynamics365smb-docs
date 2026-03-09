---
title: Day Book Customer Ledger Entry (report)
description: Get a daily transaction overview for customer postings, similar in intent to a sales day book or a chronological audit-style listing of customer postings.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_2501_Primary
ms.date: 03/08/2025
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 08/25/2025
ai.usage: ai-assisted
---

# Day Book Customer Ledger Entry (report)

The **Day Book Customer Ledger Entry** report shows chronological listings of posted customer ledger entries and their associated general ledger entry amounts, discount, actual amount, tax base, and tax amount, all grouped by posting date.

Setting the **Posting Date** field is mandatory for running the report.

You can choose to include details on customer ledger entries and/or general ledger entries in the report output.

## Use cases

[!INCLUDE [report-2501-scenario](../includes/report-2501-scenario-include.md)]

Use the report for:
* Daily control and reconciliation
* Audit trail reviews
* End of day or period transaction verification

How this differs from other customer-related reports in the finance area
* Unlike Customer - Trial Balance, it is date-driven, not balance-driven
* Unlike Customer Ledger Entries (page), it is print-oriented and structured for formal reporting
* Unlike Aged AR, it focuses on posting activity, not open balances
* This is the only printed report that is providing evidence of the associated general ledger entries for each posted sales transaction. 


## Try the report

Try the report here: [Day Book Customer Ledger Entry](https://businesscentral.dynamics.com?report=2501)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze your customer transactions. To learn more, go to:
* [Ad-hoc analysis of sales data](../ad-hoc-analysis-sales.md)
* [Customer - Trial Balance](report-129.md) 
* [Customer - Balance to date](report-121.md) 
* [Aged Accounts Receivables Excel](report-4402.md)

## Related information

[Ad-hoc analysis of sales data](../ad-hoc-analysis-sales.md)
[Customer - Trial Balance](report-129.md) 
[Customer - Balance to date](report-121.md) 
[Aged Accounts Receivables Excel](report-4402.md)
[Built-in key finance reports](../finance-reports.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]