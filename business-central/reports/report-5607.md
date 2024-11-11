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
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/23/2024
ai.usage: ai-assisted
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

<!-- 

Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with fixed asset management or finance for fixed assets.

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

Do not start lines with "Use the data to"

## Report name
Fixed Asset Projected Value

## Report description
The *Fixed Asset Projected Value* report shows the projected depreciation amounts and book value for a future period for your assets. 
The report is a detailed analysis that forecasts the future value of an organization's fixed assets over a specified period. This is specially useful where there are multiple depreciation methods and there is need to review the projected values of depreciation.
You can see the following budgeted depreciation information: 
- The book value and accumulated depreciation at the beginning of the selected period. 
- Changes during the period. 
- The book value and accumulated depreciation at the end of the selected period.
The report is useful when you are using different depreciation methods for your assets and want to estimate next year's depreciation, for example. 
**Note:** You can use the report to create the budget amounts for depreciation by selecting a budget and the **Copy to G/L Budget** field.

### Use cases
See projected depreciation amounts and book value for a future period for your assets

Please include your data sources and URLs

-->

Fixed asset managers use the report to:

- Estimate the amount of accumulated depreciation of your assets at the end of the selected period.
- Plan for the replacement of assets whose projected book value is less than their actual value.
- Determine which assets are due for depreciation and plan for adjustments.

Finance managers use the report to:

- Review and adjust the budgeted depreciation amounts for an upcoming period.
- Analyze the projected book value of assets and determine whether to dispose of assets that aren't needed.
- Forecast the financial performance of an organization based on the projected values of depreciation.

Accountants use the report to:

- Calculate the tax implications of the projected depreciation amounts.
- Reconcile financial statements by comparing the projected book value of assets with the actual book value.
- Determine whether to adjust financial statements based on the projected values of depreciation.

## Try the report

Try the report here: [Fixed Asset Projected Value](https://businesscentral.dynamics.com?report=5607)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## See also

[Fixed assets report overview](../fa-reports.md)  
[Ad hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]