---
title: Ad-hoc analysis of sales data
description: Learn how to use the data analysis mode in Business central to analyze sales data.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: bi, power BI, analysis, KPI
#TODO ms.search.form: 103, 108, 198, 490
ms.date: 04/28/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of sales data

In this article, you learn how to analyze sales data from list pages and queries using the *data analysis* feature. With data analysis feature, you can analyze data directly from the page, without having to run a report or switch another application like Excel. It provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using different options and filters, you can add multiple tabs that represent different tasks or views on the data. Examples could be "My customers", or "Sales statistics", or any other view you can imagine. For more information on how to use the *data analysis* feature, see [Analyze list and query data with analysis mode](analysis-mode.md).

The following list pages can be used for ad-hoc analysis of sales processes:
- [Sales Orders](https://businesscentral.dynamics.com/?page=9305)
- General Ledger Entries
- [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25)
- Item Ledger Entries
- Posted Sales Invoices
- Sales Return Orders


## Sales ad-hoc analysis scenarios

The *Analyze Data* feature is meant for quick fact checking and ad-hoc analysis when you don't want to run a report, if a report for your specific needs does exist, or if you want to quickly iterate to get a good overview on part of your business.

In the following sections, you'll find examples of usage scenarios within the sales area in the Business Central application.

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Sales (expected sales volume)](#example-sales-expected-sales-volume) | Analyse your expected sales volume. | [Sales Orders](https://businesscentral.dynamics.com/?page=9305) | **Sell-to Customer Name**, **Sell-to Customer No.**, **No.** , **Amount**, **Document Date Year** and **Document Date Month**. |
| [Sales (Customer sales by volume)](#example-sales-customer-sales-by-volume) | Get an overview of the customers that purchase the most or that owe the most. | [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) | **Customer Name**, **Document No.**, **Amount**, and **Remaining Amount**. |
| [Finance (Accounts Receivables)](#example-finance-accounts-receivables) | See what your customers owe you, for example, broken down into time intervals for when amounts are due. | [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) | **Customer Name**, **Due Date**, and **Remaining Amount**. |


## Example: Sales (expected sales volume)

To analyse your expected sales volume and see order details with the sales amount for orders not yet shipped broken down to customer and year/month, do as follows:

1. Open the [Sales Orders](https://businesscentral.dynamics.com/?page=9305) list and switch on the analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the *Search* field).
1. Turn on _Pivot_ mode (located directly above the _Search_ field). 
1. Now, drag the fields *Sell-to Customer Name*, *Sell-to Customer No.*, and *No.* fields to the *Row Groups* area (in that order). 
1. Then drag the field *Amount* to the *Values* area. 
1. Finally, find the *Document Date Year* and *Document Date Month* fields and drag them to the *Column Labels* area (in that order).
1. If you want to restrict the analysis to a given year/quarter, apply a filter in the *Additional Filters* menu (to the right, just below the **Columns** menu.) 
1. Rename your analysis tab to "Expected sales volume" or something that describes this analysis for you. 


## Example: Sales (Customer sales by volume)

To produce an overview of the customers that purchase the most or that owe the most, do as follows:

1. Open the [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) list and switch on the analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the *Search* field).
1. Now, drag the *Customer Name* field to the *Row Groups* area and the *Document No.* field below it.
1. Click *Amount* and *Remaining Amount* fields.
1. If you want to restrict the analysis to a given year/quarter, apply a filter in the *Additional Filters* menu (to the right, just below the **Columns** menu.) 
1. Rename your analysis tab to "Customer by sales volume" or something that describes this analysis for you. 

By following these steps, you should see something similar to this:

:::image type="content" source="media/data-analysis-customer-ledger-entries.png" alt-text="Example of how to do data analysis on the Customer Ledger Entries page." lightbox="media/data-analysis-customer-ledger-entries.png":::


## Example: Finance (Accounts Receivables)

To see what your customers owe you, maybe broken down into time intervals for when amounts are due, do as follows:

1. Open the [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) list and switch on the analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the *Search* field).
1. Turn on *Pivot* mode (located directly above the *Search* field).
1. Now, drag the *Customer Name* field to the *Row Groups* area and drag *Remaining Amount* to the *Values* area. 
1. Finally, find the *Due Date Month* field and drag it to the *Column Labels* area. 
1. If you want to restrict the analysis to a given year/quarter, apply a filter in the *Additional Filters* menu (to the right, just below the **Columns** menu.) 
1. Rename your analysis tab to "Aged Accounts by Month" or something that describes this analysis for you. 


## Data foundation for ad-hoc analysis on sales

When you have entered all the information on a sales order and added all the lines on it, you can post it. This creates a shipment and an invoice, and the customer's account, the general ledger, and the item ledger entries are updated:

- For each sales order, a sales entry is created in the **G/L Entry** table. An entry is also created in the customer's account in the **Cust. Ledger Entry** table and a general ledger entry is created in the relevant receivables account. In addition, posting the order might result in a VAT entry and a general ledger entry for the discount amount. 
- For each sales order line, an item ledger entry will be created in the **Item Ledger Entry** table (if the sales lines contain item numbers) or a general ledger entry will be created in the **G/L Entry** table (if the sales lines contain a general ledger account). In addition to this, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables.

For more information, see [Posting sales](ui-post-sales.md).


## See also

[Posting sales](ui-post-sales.md)  
[Analyze list and query data with analysis mode](analysis-mode.md)   
[Sales analytics overview](sales-analytics-overview.md)   
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)   
[Sales overview](sales-manage-sales.md)   
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]