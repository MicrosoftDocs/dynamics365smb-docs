---
title: Ad-hoc analysis of inventory data
description: Learn how to use the data analysis mode to analyze inventory data.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 516, 9300, 5119, 9301, 9305
ms.date: 05/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of inventory data

This article explains how to use the **Data Analysis** feature to analyze inventory data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "Dead/old stock" or "XXX," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages for ad-hoc analysis of inventory processes:

- [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38)


## Inventory ad-hoc analysis scenarios

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of inventory scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Inventory on Hand](#example-inventory-on-hand) | Get an overview of items in your inventory that are available. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) | **Item No.**, **Remaining Quantity** |
| [Track dead/old stock](#example-inventory-track-deadold-stock) | Get an overview of items in your inventory that have been on stock for long and is not selling well. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) | **Posting Date Year**, **Posting Date Month**, **Item No.**, **Posting Date**, **Entry type**, **Quantity**, and **Remaining Quantity**. |
| [Returned items by return reason)](#example-returned-items-by-return-reason) | Get an overview of goods that customers return, broken down on the return reason. Use this for your quality control processes. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) | **Return Reason Code**, **Posting Date Month**, **Quantity** , **Cost Amount**, **Posting Date**, **Document Type**, **Item No.**, and  **Document No.** . |
| Inventory throughput | Get an overview of purchases/sales in your inventory by Month (or Quarter.) | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) | **Posting Date Year**, **Posting Date Month**, **Item No.**, **Quantity**, **Sales Amount**, **Cost Amount (Actual)**, and **Posting Date Month** | 
| [Inventory movements] | Get an overview of how goods in your inventory move between locations | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) | **Location Code**, **Quantity**, **Posting Date**, **Item No.** |



## Example: Inventory on Hand

To analyze items in your inventory that are in stock, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) list and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).

1. Drag the **Item No.** field to the **Row Groups** area. Drag the fields in that order.
1. Drag the field **Remaining Quantity** to the **Values** ares.
1. Set a 'Not equal' filter to 0 on **Remaining Quantity**. If you do not allow negative stock, you can use a 'Greater than' 0 filter.
1. Optionally, add other fields to the analysis and maybe pivot on location or other fields.
1. Rename your analysis tab to **Inventory on Hand** or something that describes this analysis for you.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-inventory-on-hand.png" alt-text="Example of how to do a dead stock data analysis on the Item Ledger Entries page." lightbox="media/data-analysis-inventory-on-hand.png":::


## Example: Inventory (Track dead/old stock)

To analyze items in your inventory that have been on stock for long and is not selling well, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) list and turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Drag the **Posting Date Year**, **Posting Date Month** and **Item No.** fields to the **Row Groups** area. Drag the fields in that order.
1. Enable the fields **Posting Date**, **Entry type**, **Quantity**, and **Remaining Quantity** in the Columns area (just pick them). 
1. Set a 'Less than' filter on _Posting Date_ to define what you mean by "old".
1. Rename your analysis tab to **Old stock** or something that describes this analysis for you.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-inventory-dead-stock.png" alt-text="Example of how to do a dead stock data analysis on the Item Ledger Entries page." lightbox="media/data-analysis-inventory-dead-stock.png":::


## Example: Returned items by return reason

To analyze items in your inventory that have been on stock for long and is not selling well, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) list 
1. Add the field **Return Reason Code** using personalization (in the very top menu to the right, go to Settings, Personlize). 
1. Exit personalization mode.
1. Now turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Drag the fields **Return Reason Code**, and **Posting Date Month** to the **Row Groups** area (in that order).
1. Now drag the fields **Quantity** and **Cost Amount** to the **Values** area.
1. Finally, pick any other fields that you want in the analysis, and enable them in the Columns area. For example, pick **Posting Date**, **Document Type**, **Item No.**, and  **Document No.**
1. Rename your analysis tab to **Returned items by return reason** or something that describes this analysis for you.  


## Example: Inventory throughput

To analyze items in your inventory that have been on stock for long and is not selling well, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) list and turn on analyze mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Turn on **Pivot** mode (located directly above the **Search** field).
1. Drag the fields **Posting Date Year**, **Posting Date Month**, and **Item No.** to the **Row Groups** area.
1. Now drag the fields **Quantity**, **Sales Amount**, and **Cost Amount (Actual)** to the **Values** area.
1. Finally, drag the field **Posting Date Month** to the **Column Groups** area.
1. Rename your analysis tab to **Inventory troughput by Month** or something that describes this analysis for you.  


## Inventory movements

To track inventory movements between locations, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) list and turn on analyze mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Drag the field **Location Code** to the **Row Groups** area.
1. Now drag the fields **Quantity** to the **Values** area.
1. Finally, pick any other fields that you want in the analysis, and enable them in the Columns area. For example, pick **Item No.**.
1. If you add fields the Posting Date hierachy, you can also track movements over time.
1. Rename your analysis tab to **Inventory movements** or something that describes this analysis for you.  


## Data foundation for ad-hoc analysis on inventory

When you post a sales order, [!INCLUDE [prod_short](includes/prod_short.md)] updates the customer's account, general ledger, and item ledger entries. 
- For each sales order line, an item ledger entry is created in the **Item Ledger Entry** table (if the sales lines contain item numbers). In addition, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables. To learn more about posting sales, go to [Posting sales](ui-post-sales.md).

When you post a purchase document, [!INCLUDE [prod_short](includes/prod_short.md)] updates the vendor's account, general ledger (G/L), item ledger entries, and resource ledger entries.
- For each purchase line, as applicable, entries are created in the **Item Ledger Entry** table (if the purchase line is of the Item type). In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables. To learn more, go to [Posting purchases](purchasing-how-record-purchases.md#posting-purchases).



## See also

[Analyze list and query data with analysis mode](analysis-mode.md)  
[Inventory analytics overview](inventory-analytics-overview.md)
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Inventory overview](inventory-manage-inventory.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]