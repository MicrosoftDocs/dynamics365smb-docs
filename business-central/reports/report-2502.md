---
title: Day Book Vendor Ledger Entry (report)
description: Get a daily transaction overview for vendor postings, similar in intent to a vendor day book or a chronological audit-style listing of vendor postings.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_2502_Primary
ms.date: 03/08/2025
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 08/25/2025
ai.usage: ai-assisted
---

# Day Book Vendor Ledger Entry (report)

The **Day Book Vendor Ledger Entry** report shows shows chronological listings of posted vendor ledger entries and their associated general ledger entry amount, discount, actual amount, tax base, and tax amount, all grouped by posting date.

Setting the field **Posting Date** is mandatory for running the report.

You can choose to include details on vendor ledger entries and/or general ledger entries in the report output.

## Use cases

[!INCLUDE [report-2502-scenario](../includes/report-2502-scenario-include.md)]

Use the report for:
* Daily or period based review of vendor postings
* Audit and control purposes, to verify what vendor transactions were posted on a given day or period
* Chronological documentation of accounts payable activity, similar in spirit to a purchase day book in traditional accounting systems

How it differs from other vendor-related reports in the finance area
* Unlike Vendor - Trial Balance, it is transaction driven, not balance driven.
* Unlike the Vendor Ledger Entries page, it is print oriented and formal, suitable for  documentation and audit evidence of the associated general ledger entries for each posted document. 
* Unlike aging or balance reports, it focuses on what was posted, not what remains open.


## Try the report

Try the report here: [Day Book Vendor Ledger Entry](https://businesscentral.dynamics.com?report=2502)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze your vendor transactions. To learn more, go to:

* [Ad-hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)
* [Vendor - Trial Balance](report-329.md) 
* [Aged Accounts Payable Excel](report-4403.md)

## Related information

[Ad-hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)
[Vendor - Trial Balance](report-329.md) 
[Aged Accounts Payable Excel](report-4403.md)
[Built-in key finance reports](../finance-reports.md)  
[Ad-hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]