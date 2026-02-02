---
title: Customer - Sales list (report)
description: Get an overview of customer sales for a period. You can use the information to report to customs and tax authorities.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_119_Primary
ms.date: 03/12/2025
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Customer - Sales list (report)

[!INCLUDE [deprecated-report-note](../includes/deprecated-report-note-include.md)]

The **Customer - Sales list** report shows customer sales for a period. You can choose to include only customers with total sales that exceed a minimum amount. You can also specify whether you want the report to show address details for each customer.

The report is based on recorded sales in the local currency (LCY) from customer ledger entries. The total reported sales are in LCY. The total is based on the customers that you include in the report. In other words, it's based on the customers that: 

* Are within the filters on the **Customer** FastTab.
* Have total sales that exceed the amount specified in the **Amounts (LCY) Greater Than** field on the **Options** FastTab.

> [!TIP]
> When you specify the period for the report, you use a date filter. To learn about entering date filters, go to [Period](../ui-enter-date-ranges.md#period).

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

### What the report does
The *Customer - Sales list* report shows customer sales for a period. 

You can choose to include only customers with total sales that exceed a minimum amount. 

You can also specify whether you want the report to show address details for each customer.

The report is based on recorded sales (LCY) from customer ledger entries. At the bottom of the report, the total reported sales are shown in LCY. The total is based on the customers you have included in the report, that is, the customers that are within the filters on the Customer FastTab and have total sales greater than the amount specified in the **Amounts (LCY) Greater Than** field on the **Options** FastTab.

### Use cases
Get an overview of customer sales for a period. You can use it to report to the customs and tax authorities.

Please include your data sources and URLs

-->

Sales representatives use the report to:

* Get an overview of customer sales for a period.

Sales managers use the report to:

* Monitor the financial performance of the company's sales operations.
* Identify areas for improvement and set sales targets.
* Evaluate the effectiveness of sales promotions and campaigns.

Controllers and tax compliance officers use the report to:

* Report customer sales to tax authorities.
* Verify the accuracy of customer sales data for tax purposes.

## Try the report

Try the report here: [Customer - Sales list](https://businesscentral.dynamics.com?report=119)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

[!INCLUDE [alternative_reports_sales](../includes/alternative_reports_sales.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
