---
title: Item Age Composition - Value (report)
description: Review the age of stock in your warehouse by value and identify unused or slow-moving inventory.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_5808_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Item Age Composition - Value (report)

The **Item Age Composition - Value** report shows the value of on-hand inventory aged by receipt date.

You can configure the report's aging to generate three equal length periods on an ending date. The inventory's age is calculated for each period, as well as before and after the period. The report also shows total value of inventory.

The values represent the total cost of the remaining quantity for open inbound item ledger entries, which are usually a result of purchases, output, or positive adjustments. The posting date of each entry determines the bucket they're in.

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
Shows the value of inventory on hand, aged by receipt date.

You can configure report aging to generate three equal length periods as of the ending date. The inventory's age is then calculated for each period, as well as before and after the entire range. The total value of inventory is also shown.

The values represent the total cost of the remaining quantity for open inbound item ledger entries (usually a result of purchases, output, or positive adjustments). The bucket the value is in is determined by the Posting Date of each entry.

You can filter the report by Location to determine the age of Inventory by warehouse. It can also be filtered by any Item field.


### Use cases
Review the age of stock in your warehouse by value to determine obsolescence and identify slow moving inventory.

For slow moving inventory, consider actions such as a promotion or a markdown.

Please include your data sources and URLs
-->

Warehouse managers use the report to:

* Review the age of stock in your warehouse by value to identify unused or slow-moving inventory.
* Analyze inventory aging to identify which items are in high demand and which aren't.
* Plan promotions or markdowns to sell slow-moving inventory and improve sales.

Sales and marketing managers use the report to:

* Analyze inventory aging to identify which items are in high demand and which aren't.
* Review the age of stock in your warehouse by value to identify unused or slow-moving inventory.
* Plan promotions or markdowns to sell slow-moving inventory and improve sales.

Financial analysts use the report to:

* Calculate inventory turnover ratios and days in inventory to ensure effective inventory management.

## Try the report

Try the report here: [Item Age Composition - Value](https://businesscentral.dynamics.com?report=5808)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]