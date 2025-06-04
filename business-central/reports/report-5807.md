---
title: Item Age Composition - Quantity (report)
description: Review the age of stock in your warehouse by quantity and identify unused or slow moving inventory.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_5807_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Item Age Composition - Quantity (report)

The **Item Age Composition - Quantity** report shows on-hand inventory aged by receipt date.

You can configure the report's aging to generate three equal length periods on an ending date. The inventory's age is calculated for each period, as well as before and after the period. The report also shows the total inventory.

The values represent the remaining quantity for open inbound item ledger entries, which are usually a result of purchases, output, or positive adjustments. The posting date for entries determines the bucket their value is in.

To determine the age of inventory by warehouse, you can filter the report by location. You can also filter by item.

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with inventory.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Get an overview of the current age composition of selected items in your inventory. This report categorizes of on-hand value for selected items into three period buckets. You can specify the end date of the last bucket and duration of time buckets (period). The report analyzes the remaining quantity of open item ledger entries that are usually a result of purchases, output, or positive adjustments.

### What the report does
Shows the quantity of inventory on hand, aged by receipt date.

You can configure report aging to generate three equal length periods as of the ending date. The inventory's age is then calculated for each period, as well as before and after the entire range. The total inventory is also shown.

The values represent the remaining quantity for open inbound item ledger entries (usually a result of purchases, output, or positive adjustments). The bucket the value is in is determined by the Posting Date of each entry.

You can filter the report by Location to determine the age of Inventory by warehouse. It can also be filtered by any Item field.


### Use cases
Review the age of stock in your warehouse by quantity to determine obsolescence and identify slow moving inventory.

Please include your data sources and URLs


-->

Inventory and warehouse managers use the report to:

* Review the age of stock in their inventory or warehouse by quantity to identify unused or slow-moving inventory.
* Analyze inventory aging to identify which products are in high demand and they should reorder.
* Monitor inventory aging to ensure that the warehouse isn't storing unused or expired items.

Purchasing managers use the report to:

* Analyze inventory aging to identify which products are in high demand and they should reorder.
* Review the age of stock in their inventory or warehouse by quantity to identify unused or slow-moving inventory.
* Negotiate better pricing with suppliers for slow-moving inventory.

Financial analysts use the report to:

* Monitor inventory aging to ensure that the warehouse isn't storing unused or expired items.
* Calculate inventory turnover ratios and days in inventory to ensure effective inventory management.

## Try the report

Try the report here: [Item Age Composition - Quantity](https://businesscentral.dynamics.com?report=5807)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]