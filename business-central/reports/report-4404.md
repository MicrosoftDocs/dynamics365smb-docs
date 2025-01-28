---
title: Vendor - Top 10 List Excel (Excel report)
description: Analyze the effect of vendors on cash flow, and prioritize vendor payments.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_4404_Primary
ms.date: 12/15/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/15/2024
ai.usage: ai-assisted
---

# Vendor - Top 10 List Excel (report)

The **Vendor - Top 10 List Excel** report shows summarized purchase and balance data in local currency (LCY) for the top number of vendors selected. 

You can specify how many vendors to include in the report.

Data is summarized for the period specified in the request page's **Date filter** parameters. 

The report Excel workbook contains two worksheets that you can use to analyze your vendors:

- Top Vendor List, 
- TopVendorData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Top Vendor List worksheet

This worksheet shows current purchase amounts and balance in LCY by vendor. You can group data by a Year-Quarter-Month-Day hierarchy on the due date.

With filters and slicers, you can zoom into a single vendor or a group of vendors.

:::image type="content" source="../media/excel-top-10-vendors-top-vendor-list.png" alt-text="Screenshot of the Top Vendor List worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## TopVendorData worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-top-10-vendors-top-vendor-data.png" alt-text="Screenshot of the TopVendorData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4404-scenario](../includes/report-4404-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Shows information on purchases from vendors for a selected period. You can choose the number of vendors that are included in the report.
The vendors are sorted in order of amount, and you can choose whether they're sorted by purchase amount or balance. The report gives a quick overview of the vendors from which you purchase the most or to which you owe the most.

### What the report does
Provides a list of vendors with the most transactions within a selected period. You can choose to display more than 10 vendors.

The vendors are sorted by purchase amount within the selected period. The list gives a quick overview of vendors with the largest balance and highest purchase volume.

This report can be used to provide information to monitor supplier relationships, plan upcoming payments and identify potential cashflow issues.

### Use cases
Review vendors with the most transactions within a selected period to manage cash flow & prioritise vendor payments.

Please include your data sources and URLs
 -->

Procurement managers use the report to:

- Monitor vendor performance. The report provides a complete view of the vendors with the most transactions in a selected period. Use this information to monitor vendor performance and identify any discrepancies in pricing or delivery timelines.
- Prioritize vendor payments. The report provides a quick overview of the vendors with the largest balance and the highest purchase volume. Use this information to prioritize vendor payments and manage cash flow effectively.

Accounts payable specialists use the report to:

- Manage vendor relationships. The report provides a comprehensive view of the vendors that the company purchases from the most. Use this information to monitor and manage vendor relationships, ensure timely payments, and avoid potential disputes with vendors.

Controllers use the report to:

- Forecast cash flow. The report provides a quick overview of the vendors with the largest balance and the highest purchase volume. Use this information to forecast cash flow, identify potential cash flow issues, and take action to avoid disruptions in cash flow.

## Try the report

Try the report here: [Vendor - Top 10 List Excel](https://businesscentral.dynamics.com?report=4404)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your vendors. To learn more, go to:

- [Power BI Purchasing app](../purchases-powerbi-app.md)
- [Using data analysis to analyze vendors](../ad-hoc-analysis-purchasing.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Power BI Purchasing app](../purchases-powerbi-app.md)  
[Using data analysis to analyze vendors](../ad-hoc-analysis-purchasing.md)  
[Purchase reports](../purchase-reports.md)  
[Purchasing analytics overview](../purchasing-analytics-overview.md)  
[Accounts payable analytics](../receivables-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]