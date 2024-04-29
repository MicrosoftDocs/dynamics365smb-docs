---
title: Ad-hoc analysis of purchasing data
description: Learn how to use the data analysis mode in Business central to analyze purchasing data.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: bi, power BI, analysis, KPI
#TODO ms.search.form: 103, 108, 198, 490
ms.date: 04/29/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of purchasing data

In this article, you learn how to analyze purchasing data from list pages and queries using the *data analysis* feature. With data analysis feature, you can analyze data directly from the page, without having to run a report or switch another application like Excel. It provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using different options and filters, you can add multiple tabs that represent different tasks or views on the data. Examples could be "My vendors", or "Purchasing statistics", or any other view you can imagine. For more information on how to use the *data analysis* feature, see [Analyze list and query data with analysis mode](analysis-mode.md).

The following list pages can be used for ad-hoc analysis of sales processes:
- TODO

## Purchasing ad-hoc analysis scenarios

The *Analyze Data* feature is meant for quick fact checking and ad-hoc analysis when you don't want to run a report, if a report for your specific needs does exist, or if you want to quickly iterate to get a good overview on part of your business.

In the following sections, you'll find examples of usage scenarios within the purchasing area in the Business Central application.

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Finance (Accounts TODO)](#example-finance-accounts-receivables) | See what your customers owe you, for example, broken down into time intervals for when amounts are due. | [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) | **Customer Name**, **Due Date**, and **Remaining Amount**. |



## Example: Finance (Accounts TODO)

To see what your customers owe you, maybe broken down into time intervals for when amounts are due, do as follows:

1. Open the [Customer Ledger Entries](https://businesscentral.dynamics.com/?page=25) list and switch on the analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the *Search* field).
1. Turn on *Pivot* mode (located directly above the *Search* field).
1. Now, drag the *Customer Name* field to the *Row Groups* area and drag *Remaining Amount* to the *Values* area. 
1. Finally, find the *Due Date Month* field and drag it to the *Column Labels* area. 
1. If you want to restrict the analysis to a given year/quarter, apply a filter in the *Additional Filters* menu (to the right, just below the **Columns** menu.) 
1. Rename your analysis tab to "Aged Accounts by Month" or something that describes this analysis for you. 


## Data foundation for ad-hoc analysis on purchasing

When a purchase document is posted, the vendor's account, the general ledger (G/L), the item ledger entries, and the resource ledger entries are updated.

- For each purchase document, a purchase entry is created in the **G/L Entry** table. An entry is also created in the vendor's account in the **Supplier Ledger Entry** table and a G/L entry is created in the relevant payables account. In addition, posting the purchase can result in a value-added tax (VAT) entry and a G/L entry for the discount amount. 
- For each purchase line, as applicable, entries are created in the:
    - **Item Ledger Entry** table if the purchase line is of the Item type.
    - **G/L Entry** table if the purchase line is of the G/L Account type.
    - **Resource Ledger Entry** table if the purchase line is of the Resource type.
- In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables.

For more information, see [Posting purchases](purchasing-how-record-purchases.md#posting-purchases).


## See also

[Posting purchases](purchasing-how-record-purchases.md#posting-purchases)
[Analyze list and query data with analysis mode](analysis-mode.md)   
[Purchasing overview](purchasing-manage-purchasing.md)   
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)   
[Purchasing overview](purchasing-manage-purchasing.md)   
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]