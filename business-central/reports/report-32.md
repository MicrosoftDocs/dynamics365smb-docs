---
title: VAT Registration No. Check (Report)
description: Check VAT registration number formats and duplicates for customers, vendors, and contacts using country/region formats configured locally.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: VAT, tax compliance, EU sales, VIES, cross-border
ms.search.form: Report_32_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/25/2025
ai-usage: ai-assisted
---

# VAT Registration No. Check (report)

The **VAT Registration No. Check** report checks VAT registration number formats and duplicates for customers, vendors, and contacts. It compares numbers with the country/region formats configured in Business Central. It doesn't contact the European Union (EU) VAT Information Exchange System (VIES) or verify that a number is registered.

Use **Format Check** to list numbers that don't match a configured format. Use **Duplicate Check** to find repeated numbers within customers, vendors, or contacts. Both options are initially selected. Records with blank VAT registration numbers are excluded.

## Use cases

[!INCLUDE [report-32-scenario](../includes/report-32-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Run the report regularly to maintain up-to-date and accurate VAT number records.
> * Use it as a pre-check before submitting EU sales reports to avoid compliance issues.
> * Configure VAT registration number formats for the relevant countries/regions before checking formats.
> * Investigate duplicate numbers to determine whether they are appropriate for the records involved.

Finance teams and compliance officers can use this report to:

* Check VAT number formats and identify duplicates.
* Ensure readiness for EU cross-border reporting.
* Reduce the risk of audit findings or penalties due to incorrect VAT data.

## Try the report

Try the report here: [VAT Registration No. Check](https://businesscentral.dynamics.com?report=32)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[VAT management overview](../finance-manage-vat.md)  
[Built-in VAT reports in Business Central](../finance-vat-reports.md)  
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]