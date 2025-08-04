---
title: Customer - Top 10 List Excel (Excel report)
description: Review customers with the most transactions in a selected period directly in Excel. Identify sales trends and manage debt collections.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_4409_Primary
ms.date: 12/16/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/16/2024
ai.usage: ai-assisted
---

# Customer - Top 10 List Excel (report)

The **Customer - Top 10 List Excel** report shows shows summarized sales and balance data in local currency (LCY) for the number of customers and for the period specified in the request page's **Quantity** and **Datefilter** parameters. The Quantity parameter is the number of "top" customers to rank.

The report Excel workbook contains two worksheets that you can use to analyze your customers:

- Top Customer List
- TopCustomerData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Top Customer List worksheet

This worksheet shows current sales amounts and balance in LCY by customer.

With filters and slicers, you can zoom in on a single customer or a group of customers.

:::image type="content" source="../media/excel-top-10-customers-top-customer-list.png" alt-text="Screenshot of the Top Customer List worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## TopCustomerData worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-top-10-customers-top-customer-data.png" alt-text="Screenshot of the TopCustomerData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4409-scenario](../includes/report-4409-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Shows information on customers' purchases and balances for a selected period. You can choose the number of customers that will be included in the report. Only customers that have either purchases during the period or a balance at the end of the period will be included.
The customers are sorted in order of amount, and you can choose whether they're sorted by sales amount or balance. The report gives a quick overview of the customers that purchase the most or that owe the most.

### What the report does
Provides a list of customers with the most transactions within a selected period. You can choose to display more than 10 customers. 

The customers are sorted by sales amount within the selected period. The list gives a quick overview of customers with the largest balance and highest sales volume.

You can choose to display a bar chart, or pie chart to visually represent the calculated figures. 

This report can be used to provide information to identify sales trends, upcoming collectable debts, and major revenue sources in the company.

### Use cases
Review customers with the most transactions within a selected period to identify sales trends and manage collectable debts.

Please include your data sources and URLs

-->

Sales representatives use the report to:

- Identify which customers bought the most within a selected period and prioritize follow-up.
- Identify overdue payments or outstanding balances, and communicate updated payment timelines to customers.
- Identify sales trends and adjust sales strategies.

Sales managers use the report to:

- Analyze sales performance across customers and regions.
- Determine which customers have the largest outstanding balances and prioritize follow-up.
- Identify sales trends and make data-driven decisions to improve performance.

Credit or accounts receivable managers use the report to:

- Identify customers with outstanding balances and prioritize follow-up.
- Analyze sales trends and adjust credit policies.
- Forecast future cash flows and adjust collection strategies.

Marketing managers use the report to:

- Analyze sales trends across customers and regions.
- Identify the customers with the highest sales volume and target them for future marketing campaigns.
- Identify sales trends and adjust marketing strategies.

Customer success managers use the report to:

- Identify the customers with the highest sales volume and provide them with personalized support.
- Identify overdue payments or outstanding balances, and communicate updated payment timelines to customers.
- Identify sales trends and make data-driven decisions to improve customer satisfaction.

## Try the report

Try the report here: [Customer - Top 10 List Excel](https://businesscentral.dynamics.com?report=4409)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your customers. To learn more, go to:

- [Power BI Sales app](../sales-powerbi-app.md)
- [Using data analysis to analyze sales](../ad-hoc-analysis-sales.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Power BI Sales app](../sales-powerbi-app.md)  
[Using data analysis to analyze sales](../ad-hoc-analysis-sales.md)  
[Sales reports](../sales-reports.md)  
[Sales analytics overview](../sales-analytics-overview.md)  
[Accounts receivables analytics](../receivables-reports.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]