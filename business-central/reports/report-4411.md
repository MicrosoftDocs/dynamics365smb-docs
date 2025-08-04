---
title: Fixed Asset Details (Excel report)
description: Get details about fixed assets transactions and reference data that can help you manage your fixed assets.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_4411_Primary
ms.date: 12/27/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/27/2024
ai.usage: ai-assisted
---

# Fixed Asset Details Excel (report)

The **Fixed Asset Details Excel** report shows fixed assets ledger entries for one or more fixed assets for a given depreciation book. You can choose to include reversed entries and inactive fixed assets.

The report Excel workbook contains two worksheets that you can use to analyze your fixed assets data:

- Fixed Asset Details
- FixedAssetData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Fixed Asset Details worksheet

This worksheet shows fixed assets ledger entries sorted by fixed asset numbers. It shows data for asset description, posting date, FA posting category, FA posting type, document type, document number, description, amount, number of depreciation days, user ID (who did it), G/L entry number, and entry number.

The filters and slicers on the worksheet let you zoom in on a fixed asset's class, subclass, or location. You can also filter by department code or project code, if needed.

:::image type="content" source="../media/excel-Fixed-Asset-Details-Fixed-Asset-Details.png" alt-text="Screenshot of the Fixed Asset Details worksheet" lightbox="../media/excel-Fixed-Asset-Details-Fixed-Asset-Details.png":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## FixedAssetData worksheet

This worksheet shows the raw data used in the report.

[!INCLUDE [excel-reports-data-worksheet-use-it-for](../includes/excel-reports-data-worksheet-use-it-for.md)]

:::image type="content" source="../media/excel-Fixed-Asset-Details-FixedAssetData.png" alt-text="Screenshot of the FixedAssetData worksheet" lightbox="../media/excel-Fixed-Asset-Details-FixedAssetData.png":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4411-scenario](../includes/report-4411-scenario-include.md)]

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
Fixed Asset Details

## Report description
The Fixed Asset Details report provides a comprehensive overview of all relevant information pertaining to each fixed asset owned by an organization. This report serves as a detailed transaction information and reference tool for asset management.

### What the report does
The Fixed Asset Details report shows the fixed asset ledger entries for fixed assets. It provides detailed information about each fixed asset, including acquisition cost, depreciation, and book value.


Please include your data sources and URLs

-->

Fixed asset managers use the report to:

- Track the current status of fixed assets and their location in an organization.
- Plan for the future replacement or upgrade of fixed assets based on their age and condition.
- Calculate the depreciation of fixed assets and ensure that it complies with accounting standards.

Facilities managers use the report to:

- Track the maintenance history and service records for each fixed asset.
- Identify any upcoming maintenance or service needs for fixed assets and plan accordingly.
- Monitor the condition of fixed assets and identify opportunities for repair or replacement.

Financial analysts use the report to:

- Analyze the value of fixed assets over time and identify trends or patterns.
- Calculate the return on investment for fixed assets and assess their overall contribution to the organization's financial performance.
- Identify discrepancies or errors in the fixed asset ledger entries and work with the accounting team to correct them.

## Try the report

Try the report here: [Fixed Asset Details Excel](https://businesscentral.dynamics.com?report=4411)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your fixed assets. To learn more, go to:

- [Fixed Asset Details (legacy report)](report-5604.md)
- [Using data analysis to analyze fixed assets data](../ad-hoc-analysis-fa.md)  

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP
- [Steve Chinsky ](https://www.linkedin.com/in/steve-chinsky-321a20/) | Microsoft MVP
- [Rob Delprado](https://www.linkedin.com/in/robb-delprado/) | Microsoft MVP

## Related information

[Ad-hoc analysis of fixed assets data](../ad-hoc-analysis-fa.md)  
[Fixed assets analytics overview](../fa-analytics-overview.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]