---
title: Fixed Asset Projected Value (report)
description: Review projected depreciation amounts and book value for a future period for your fixed assets.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_5607_Primary
ms.date: 11/11/2024
ms.service: dynamics-365-business-central
---

# Fixed Asset Projected Value (report)

The **Fixed Asset Projected Value** report shows the projected depreciation amounts and book value for a future period for your assets.

The report is a detailed analysis that forecasts the future value of an organization's fixed assets over a specified period. Forecasts are useful when you use multiple depreciation methods and you want to review the projected depreciation values.

Projected depreciation is calculated for two periods:

- For the first period, the report uses the dates in the Posted Entries From field and the First Depreciation Date field. If you enter a date before the last posted depreciation entry, no depreciation is calculated as of the first depreciation date.
- For the second period, the report uses the dates in the First Depreciation Date field and the Last Depreciation Date field. The depreciation amount calculated for the second period can show as a single amount, or as several amounts broken down by the time interval specified in the **Number of Days** field.

You can explore the following budgeted depreciation information:

- The book value and accumulated depreciation at the beginning of the selected period.
- Changes during the period.
- The book value and accumulated depreciation at the end of the selected period.

The report is useful, for example, when you have different depreciation methods and want to estimate depreciation for the next year.

> [!NOTE]
> You can use the report to create the budget amounts for depreciation by selecting a budget and the **Copy to G/L Budget** field.

## Use cases

[!INCLUDE[report-5607-scenario](../includes/report-5607-scenario-include.md)]

## Try the report

Try the report here: [Fixed Asset Projected Value](https://businesscentral.dynamics.com?report=5607)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze your fixed assets. To learn more, go to:

- [Fixed Asset Projected Value Excel](report-4413.md)
- [Using data analysis to analyze fixed assets data](../ad-hoc-analysis-fa.md)  

## Related information

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]