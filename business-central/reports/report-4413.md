---
title: Fixed Asset Projected Value (Excel report)
description: Review posted entries and projected depreciation in Excel for a fixed asset depreciation book, with running book values and configurable projection periods.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_4413_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 12/27/2024
ai-usage: ai-assisted
---

# Fixed Asset Projected Value Excel (report)

The **Fixed Asset Projected Value Excel** report combines posted fixed asset ledger entries with calculated depreciation for a selected depreciation book. It shows a running book value and identifies projected entries. The calculations don't post depreciation to the fixed asset ledger.

Specify **First Depreciation Date** and **Last Depreciation Date** for the projection. **Posted Entries From** controls which actual entries are included, not when depreciation starts. Use **Number of Days** or **Use Accounting Period** to set the projection intervals. **No. of Days in First Period** overrides the days used for the first depreciation calculation.

Select **Projected Disposal** to limit projections to the asset's projected disposal date when that date falls within the projection period. Inactive assets and assets already disposed of are excluded.

The report Excel workbook includes the following report and data worksheets:

- Projected Value (Print)
- Projected Value (Analysis)
- FixedAssetData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Projected value worksheets

These worksheets show the fixed asset posting date, posting type, number of depreciation days, amount, and book value for the fixed assets and period specified on the report request page.

The filters and slicers on the analysis worksheet let you zoom in on a fixed asset's class, subclass, or location. You can also filter by the two global dimensions. The dimension names depend on your company's setup.

:::image type="content" source="../media/excel-Fixed-Asset-Projected-Value-Projected-Value.png" alt-text="Screenshot of the Fixed Asset Projected Value worksheet." lightbox="../media/excel-Fixed-Asset-Projected-Value-Projected-Value.png":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Fixed asset data worksheet

This worksheet shows the raw data used in the report.

[!INCLUDE [excel-reports-data-worksheet-use-it-for](../includes/excel-reports-data-worksheet-use-it-for.md)]

:::image type="content" source="../media/excel-Fixed-Asset-Projected-Value-FixedAssetData.png" alt-text="Screenshot of the FixedAssetData worksheet" lightbox="../media/excel-Fixed-Asset-Projected-Value-FixedAssetData.png":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Supporting workbook worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4413-scenario](../includes/report-4413-scenario-include.md)]

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
- Plan for the replacement of assets based on their projected book value.
- Determine which assets are due for depreciation and plan for adjustments.

Finance managers use the report to:

- Review and adjust the budgeted depreciation amounts for an upcoming period.
- Analyze the projected book value of assets and determine whether to dispose of assets that aren't needed.
- Forecast the financial performance of an organization based on the projected values of depreciation.

Accountants use the report to:

- Calculate the tax implications of the projected depreciation amounts.
- Review depreciation forecasts by comparing the projected book value of assets with their posted book value.
- Determine whether to adjust financial statements based on the projected values of depreciation.

The report doesn't write amounts to a G/L budget.

## Try the report

Try the report here: [Fixed Asset Projected Value Excel](https://businesscentral.dynamics.com?report=4413)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your fixed assets. Learn more in the following articles:

- [Fixed Asset Projected Value (legacy report)](report-5607.md)
- [Using data analysis to analyze fixed assets data](../ad-hoc-analysis-fa.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Ad-hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]