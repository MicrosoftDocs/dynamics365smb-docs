---
title: Ad-hoc analysis of sales data
description: Learn how to use the data analysis mode to analyze sales data.
author: brentholtorf
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 516, 9300, 5119, 9301, 9305
ms.date: 04/28/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of sales data

This article explains how to use the **Data Analysis** feature to analyze sales data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "My customers" or "Sales statistics," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages for ad-hoc analysis of sales processes:

- [Sales Orders](https://businesscentral.dynamics.com/?page=9305&layout=analysis)
- General Ledger Entries
- [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis)
- Item Ledger Entries
- Posted Sales Invoices
- Sales Return Orders

## Sales ad-hoc analysis scenarios

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of sales scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Sales (expected sales volume)](#example-sales-expected-sales-volume) | Analyze your expected sales volume. | [Sales Orders](https://businesscentral.dynamics.com/?page=9305&layout=analysis) | **Sell-to Customer Name**, **Sell-to Customer No.**, **No.** , **Amount**, **Document Date Year**, and **Document Date Month**. |
| [Sales (Customer sales by volume)](#example-sales-customer-sales-by-volume) | Get an overview of the customers that purchase the most, or that owe the most. | [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis) | **Customer Name**, **Document No.**, **Amount**, and **Remaining Amount**. |
| [Finance (Accounts Receivables)](#example-finance-accounts-receivables) | See what your customers owe you, for example, broken down into time intervals for when amounts are due. | [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis) | **Customer Name**, **Due Date**, and **Remaining Amount**. |

## Example: Sales (expected sales volume)

To analyze your expected sales volume and sales amounts for unshipped orders for each customer by year or month, follow these steps:

1. Open the [Sales Orders](https://businesscentral.dynamics.com/?page=9305&layout=analysis) list and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Turn on **Pivot** mode (located directly above the **Search** field).
1. Drag the **Sell-to Customer Name**, **Sell-to Customer No.**, and **No.** fields to the **Row Groups** area. Drag the fields in that order.
1. Drag the field **Amount** field to the **Values** area.
1. Drag the **Document Date Year** and **Document Date Month** fields to the **Column Labels** area. Drag the fields in that order.
1. To do the analysis for a given year or quarter, apply a filter in the **Additional Filters** menu. The menu is on the right of the page, just below the **Columns** menu.
1. Rename your analysis tab to **Expected sales volume** or something that describes this analysis for you.

## Example: Sales (Customer sales by volume)

To produce an overview of the customers that purchase the most or that owe the most, follow these steps:

1. Open the [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis) list, and switch on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Drag the **Customer Name** field to the **Row Groups** area, and the **Document No.** field below it.
1. Choose the **Amount** and **Remaining Amount** fields.
1. To do the analysis for a given year or quarter, apply a filter in the **Additional Filters** menu. The menu is on the right of the page, just below the **Columns** menu.
1. Rename your analysis tab to **Customer by sales volume**, or something that describes this analysis for you.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-customer-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-customer-ledger-entries.png":::

## Example: Finance (Accounts Receivables)

To see what your customers owe you, maybe broken down into time intervals for when amounts are due, follow these steps:

1. Open the [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25&layout=analysis) list and turn on analysis mode.
1. On the **Columns** menu, remove all columns (select the box next to the **Search** field).
1. Turn on **Pivot** mode (located directly above the **Search** field).
1. Drag the **Customer Name** field to the **Row Groups** area, and drag the **Remaining Amount** field to the **Values** area.
1. Drag the **Due Date Month** field to the **Column Labels** area.
1. To do the analysis for a given year or quarter, apply a filter in the **Additional Filters** menu. The menu is on the right of the page, just below the **Columns** menu.
1. Rename your analysis tab to **Aged Accounts by Month**, or something that describes this analysis for you.

## Data foundation for ad-hoc analysis on sales

After you enter information on a sales order and add all the sales order lines, you can post the order. Posting creates a shipment and an invoice. [!INCLUDE [prod_short](includes/prod_short.md)] updates the customer's account, general ledger, and item ledger entries:

- For each sales order, a sales entry is created on the **G/L Entry** table. An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account. In addition, posting the order might result in a VAT entry and a general ledger entry for the discount amount.
- For each sales order line, an item ledger entry is created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry is created in the **G/L Entry** table (if the sales lines contain a general ledger account). In addition, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.

To learn more about posting sales, go to [Posting sales](ui-post-sales.md).

## Related information

[Posting sales](ui-post-sales.md)  
[Analyze list and query data with analysis mode](analysis-mode.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Sales overview](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
