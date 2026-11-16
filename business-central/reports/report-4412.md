---
title: Fixed Asset Analysis (Excel report)
description: Analyze fixed asset acquisitions, depreciation, and book values in Excel for a selected depreciation book and period, including projected depreciation.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_4412_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 12/26/2024
ai-usage: ai-assisted
---

# Fixed Asset Analysis Excel (report)

The **Fixed Asset Analysis Excel** report shows fixed asset details in given time periods, such as:

- Book value
- Depreciation
- Acquisitions

Specify a depreciation book and valid starting and ending dates. You can include inactive fixed assets or select **Only Sold Assets** to include assets disposed of within the selected period. Select **Budget Report** to include calculated future depreciation and book value.

The report Excel workbook includes the following report and data worksheets:

- Fixed Asset Analysis (Print)
- Fixed Asset Analysis
- Book Value
- FixedAssetData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Fixed asset analysis worksheet

This worksheet shows details about your fixed assets, such as fixed assets class, sub class, description, acquisition date, and disposal date. It also shows their value at the starting date and ending date of the specified period.

The filters and slicers on the worksheet let you zoom in on a fixed asset's class, subclass, or location. You can also filter by the two global dimensions. The dimension names depend on your company's setup.

:::image type="content" source="../media/excel-fixed-assets-analysis-fixed-assets-analysis.png" alt-text="Screenshot of the Fixed Asset Analysis worksheet" lightbox="../media/excel-fixed-assets-analysis-fixed-assets-analysis.png":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Book value worksheet

This worksheet shows fixed asset details in the given time periods, such as:

- Book value
- Depreciations
- Acquisitions

The filters and slicers on the worksheet let you zoom in on a fixed asset's class, subclass, or location. You can also filter by the two global dimensions. The dimension names depend on your company's setup.

:::image type="content" source="../media/excel-fixed-assets-analysis-book-value.png" alt-text="Screenshot of the fixed asset Book Value worksheet." lightbox="../media/excel-fixed-assets-analysis-book-value.png":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Fixed asset data worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-fixed-assets-analysis-FixedAssetData.png" alt-text="Screenshot of the FixedAssetData worksheet" lightbox="../media/excel-fixed-assets-analysis-FixedAssetData.png":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Supporting workbook worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4412-scenario](../includes/report-4412-scenario-include.md)]

## Try the report

Try the report here: [Fixed Asset Analysis Excel](https://businesscentral.dynamics.com?report=4412)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your fixed assets. Learn more in the following articles:

- [Fixed Asset Analysis (legacy report)](report-5600.md)
- [Using data analysis to analyze fixed assets data](../ad-hoc-analysis-fa.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Ad-hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]