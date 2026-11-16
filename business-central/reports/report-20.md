---
title: Calculate and Post Tax Settlement (Report)
description: Calculate VAT settlement from open VAT entries, review a test report, or post the transfer to a settlement account and close the entries.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: VAT, tax, settlement, reporting, finance
ms.search.form: Report_20_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 06/25/2025
ai-usage: ai-assisted
---

# Calculate and Post Tax Settlement (report)

The **Calculate and Post Tax Settlement** report calculates the net amount of VAT that's due or refundable from open VAT entries. With **Post** turned on, it posts the transfer to the VAT settlement account and closes the settled VAT entries. With **Post** turned off, it only prints a test report. It doesn't save an unposted journal for later review.

Typically, businesses use the report at the end of a monthly or quarterly VAT filing period. Enter the starting and ending VAT reporting dates, posting date, document number, and settlement account. The report doesn't submit a tax return.

## Use cases

[!INCLUDE [report-20-scenario](../includes/report-20-scenario-include.md)]

> [!TIP]
> Here are some tips on how to use the report:
>
> * Run the report at the end of each VAT period to automate settlement.
> * Run with **Post** turned off and review the test report before running again with **Post** turned on.
> * Use filters to target specific VAT entries or periods.
> * Coordinate with finance teams to align on filing schedules and thresholds.

**Accountants** can use this report to:

* Calculate VAT obligations or refunds at the end of a filing period.
* Post VAT settlements efficiently and accurately.

**Controllers** can use it to:

* Ensure compliance with tax reporting requirements.
* Monitor VAT trends and filing consistency.

**Auditors** might reference it to:

* Verify VAT calculations and journal postings.
* Confirm completeness of tax settlement processes.

## Try the report

Try the report here: [Calc. and Post VAT Settlement](https://businesscentral.dynamics.com?report=20)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[VAT management overview](../finance-manage-vat.md)  
[Built-in VAT reports in Business Central](../finance-vat-reports.md)  
[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]