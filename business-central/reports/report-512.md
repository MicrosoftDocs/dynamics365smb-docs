---
title: Intercompany Transactions (Report)
description: Review current-company G/L entries and mapped customer or vendor entries for intercompany partners, with opening balances and period transactions.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting, intercompany, consolidation
ms.search.form: Report_512_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/21/2025
ai-usage: ai-assisted
---

# Intercompany Transactions (report)

The **Intercompany Transactions** report shows posted G/L entries with an intercompany partner code, and customer and vendor ledger entries for the customer or vendor assigned to that partner. It reads entries in the current company, not entries from the partner company.

Set **Starting Date** and **Ending Date**, and filter the partner code as needed. The report shows opening balances, transactions in the selected period, and running balances. Use it as an input to intercompany reconciliation before consolidation.

## Use cases

[!INCLUDE [report-512-scenario](../includes/report-512-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Run this report regularly to maintain accurate intercompany records.
> * Use it in conjunction with your consolidation tools to ensure all internal transactions are accounted for.
> * Pay attention to journal entries that might not be reflected in sales or purchase documents.

Controllers and finance teams can use the report to:

* Review the current company's entries associated with intercompany partners.
* Reconcile balances before financial consolidation.
* Investigate partner-related balances and transactions.

Auditors can use the report to:

* Verify the accuracy and completeness of intercompany transactions.
* Identify discrepancies or missing entries that could affect consolidated financial statements.

## Try the report

Try the report here: [Intercompany Transactions](https://businesscentral.dynamics.com?report=512)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]