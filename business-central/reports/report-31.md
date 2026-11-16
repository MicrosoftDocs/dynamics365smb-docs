---
title: VAT Exceptions for VAT Differences (Report)
description: Review posted VAT entries with VAT differences above a minimum threshold, with options for reversed entries and additional reporting currency.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: VAT, tax, exceptions, reporting, finance
ms.search.form: Report_31_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/25/2025
ai-usage: ai-assisted
---

# VAT Exceptions (report)

The **VAT Exceptions** report lists existing VAT entries whose recorded **VAT Difference** meets or exceeds the **Min. VAT Difference** threshold in either direction. It helps you review VAT adjustments before filing returns. It doesn't detect transactions that have no VAT entry.

Filter by **Posting Date** to select the period. You can include reversed entries and show amounts in the additional reporting currency. In that currency, the threshold applies to the additional-currency VAT difference.

## Use cases

[!INCLUDE [report-31-scenario](../includes/report-31-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Run the report when reviewing recorded VAT differences.
> * Set a nonzero threshold to focus on larger differences.
> * Investigate document references for entries that need explanation.

Accountants can use the report to:

* Review VAT differences on posted VAT entries.
* Investigate larger adjustments before filing.

Controllers can use the report to:

* Review the scale of VAT adjustments in the selected posting period.
* Support internal audits and tax reporting accuracy.

Auditors might reference the report to:

* Identify VAT differences that need supporting explanations during an audit.

## Try the report

Try the report here: [VAT Exceptions](https://businesscentral.dynamics.com?report=31)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[VAT management overview](../finance-manage-vat.md)  
[Built-in VAT reports in Business Central](../finance-vat-reports.md)  
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]