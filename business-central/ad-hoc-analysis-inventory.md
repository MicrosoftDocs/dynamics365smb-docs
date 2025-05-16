---
title: Ad-hoc analysis of inventory data
description: Learn how to use the data analysis mode to analyze inventory data.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 516, 9300, 5119, 9301, 9305
ms.date: 05/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Ad-hoc analysis of inventory data

This article explains how to use the **Data Analysis** feature to analyze inventory data directly from list pages and queries. You don't have to run a report or switch to another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "expiring stock" or "top sellers," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

Use the following list pages for ad-hoc analysis of inventory processes:

- [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis)

## Inventory ad-hoc analysis scenarios

Use the **Data Analysis** feature for quick fact checking and ad-hoc analysis:

- If you don't want to run a report.
- If a report for your specific need doesn't exist.
- If you want to quickly iterate to get a good overview on a part of your business.

The following sections provide examples of inventory scenarios in [!INCLUDE [prod_short](includes/prod_short.md)].

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Inventory on-hand](#example-inventory-on-hand) | Get an overview of items that are available in your inventory. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) | **Item No.**, **Remaining Quantity** |
|[Example: track expiring or old stock](#example-track-expiring-or-old-stock) | Get an overview of items in your inventory that have been on stock for a long time and aren't selling well. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) | **Posting Date Year**, **Posting Date Month**, **Item No.**, **Posting Date**, **Entry type**, **Quantity**, and **Remaining Quantity**. |
| [Returned items by return reason](#example-returned-items-by-return-reason) | Get an overview of goods that customers return, categorized by the return reason. Use this for analysis for quality control. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) | **Return Reason Code**, **Posting Date Month**, **Quantity** , **Cost Amount**, **Posting Date**, **Document Type**, **Item No.**, and  **Document No.** . |
| Inventory throughput | Get an overview of purchases and sales in your inventory by month or quarter. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) | **Posting Date Year**, **Posting Date Month**, **Item No.**, **Quantity**, **Sales Amount**, **Cost Amount (Actual)**, and **Posting Date Month** |
| [Inventory movements] | Get an overview of how goods in your inventory move between locations. | [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) | **Location Code**, **Quantity**, **Posting Date**, **Item No.** |

## Example: inventory on-hand

To analyze items in your inventory that are in stock, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field).
1. Drag the **Item No.** field to the **Row Groups** area. Drag the fields in that order.
1. Drag the field **Remaining Quantity** to the **Values** ares.
1. Set a **Not equal** filter to **0** on **Remaining Quantity**. If you don't allow negative stock levels, set a **Greater than** filter to **0**.
1. Optionally, add other fields to the analysis and maybe pivot on location or other fields.
1. Rename your analysis tab to **Inventory on Hand** or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-inventory-on-hand.png" alt-text="Example of how to do an inventory on-hand data analysis." lightbox="media/data-analysis-inventory-on-hand.png":::

## Example: track expiring or old stock

To analyze items in your inventory that have been on stock for a long time and aren't selling well, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Posting Date Year**, **Posting Date Month** and **Item No.** fields to the **Row Groups** area. Drag the fields in that order.
1. In the **Columns** area, choose the **Posting Date**, **Entry type**, **Quantity**, and **Remaining Quantity** fields.
1. Set a **Less than** filter to **Posting Date** to define what you mean by "old".
1. Rename your analysis tab to **Old stock** or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source="media/data-analysis-inventory-dead-stock.png" alt-text="Example of how to do a dead stock data analysis on the Item Ledger Entries page." lightbox="media/data-analysis-inventory-dead-stock.png":::

## Example: returned items by return reason

To analyze returned items sorted by the reasons for their return, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38) list.
1. Add the **Return Reason Code** field by personalizing the page. On the **Settings** menu, choose **Personalize**.
1. Exit personalization mode.
1. Choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Return Reason Code** and **Posting Date Month** fields to the **Row Groups** area. Drag the fields in that order.
1. Drag the  **Quantity** and **Cost Amount** fields to the **Values** area.
1. Add any other fields that you want in the analysis, and enable them in the **Columns** area. For example, you might add the **Posting Date**, **Document Type**, **Item No.**, and  **Document No.** fields.
1. Rename your analysis tab to **Returned items by return reason** or something that describes this analysis.  

## Example: inventory throughput

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Turn on the **Pivot Mode** toggle (located above the **Search** field on the right).
1. Drag the **Posting Date Year**, **Posting Date Month**, and **Item No.** fields to the **Row Groups** area.
1. Drag the **Quantity**, **Sales Amount**, and **Cost Amount (Actual)** fields to the **Values** area.
1. Drag the **Posting Date Month** field to the **Column Groups** area.
1. Rename your analysis tab to **Inventory throughput by Month** or something that describes this analysis.  

## Inventory movements

To track inventory movements between locations, follow these steps:

1. Open the [Item Ledger Entries](https://businesscentral.dynamics.com/?page=38&layout=analysis) list, and choose :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: to turn on analysis mode.
1. Go to the **Columns** menu and remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Location Code** field to the **Row Groups** area.
1. Drag the **Quantity** field to the **Values** area.
1. Add any other fields that you want in the analysis, and enable them in the **Columns** area. For example, you might add the **Item No.** field.
1. Rename your analysis tab to **Inventory movements** or something that describes this analysis.  

   > [!TIP]
   > If you add the Posting Date field, you can also track movements over time.

## Data foundation for ad-hoc analysis on inventory

When you post a sales order, [!INCLUDE [prod_short](includes/prod_short.md)] updates the customer's account, general ledger, and item ledger entries.

- For each sales order line, an item ledger entry is created in the **Item Ledger Entry** table (if the sales lines contain item numbers). In addition, sales orders are always recorded in the **Sales Shipment Header** and **Sales Invoice Header** tables. To learn more about posting sales, go to [Posting sales](ui-post-sales.md).

When you post a purchase document, [!INCLUDE [prod_short](includes/prod_short.md)] updates the vendor's account, general ledger (G/L), item ledger entries, and resource ledger entries.

- For each purchase line, as applicable, entries are created in the **Item Ledger Entry** table (if the purchase line is of the Item type). In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables. To learn more, go to [Posting purchases](purchasing-how-record-purchases.md#posting-purchases).

## Related information

[Analyze list and query data with analysis mode](analysis-mode.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)  
[Inventory overview](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
