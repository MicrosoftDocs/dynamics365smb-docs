---
title: Item Dimensions - Total (report)
description: Analyse your item entries with dimension totals by building a grouping of dimensions for each permutation of dimension values, and view a calculated total based on user defined columns (i.e. net change, balance at date, actual vs budget).
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_7151_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Item Dimensions - Total (report)

The *Item Dimensions - Total* report shows calculated item entry totals for dimension levels specified by the user, for a given date period.

Dimension levels are specified by selecting an analysis view configured with dimension codes, then picking a hierarchy of how the dimension groups are grouped under one another. Location is automatically included as a dimension.

This report can be based on analysis view entries from either sales, purchase or inventory areas.

Calculated totals are fully customisable through the adoption of Analysis Columns, which provides ability to specify calculation methods (net change or balance), item entry source (budget or actual), analysis type (quantity, sales amounts or cost amounts) and even period/date formula methods for finer month comparison controls.

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


### What the report does
Shows calculated item entry totals for dimension levels specified by the user, for a given date period.

Dimension levels are specified by selecting an analysis view configured with dimension codes, then picking a hierarchy of how the dimension groups are grouped under one another. Location is automatically included as a dimension.

This report can be based on analysis view entries from either sales, purchase or inventory areas.

Calculated totals are fully customisable through the adoption of Analysis Columns, which provides ability to specify calculation methods (net change or balance), item entry source (budget or actual), analysis type (quantity, sales amounts or cost amounts) and even period/date formula methods for finer month comparison controls.

### Use cases
Analyse your item entries with dimension totals by building a grouping of dimensions for each permutation of dimension values, and view a calculated total based on user defined columns (i.e. net change, balance at date, actual vs budget)

Please include your data sources and URLs

-->

As a supply chain manager, use the report to:
* Analyze inventory levels by dimension levels to ensure that inventory is optimized for each segment
* Use the data to plan purchasing activities for specific segments to optimize inventory levels and reduce waste
* Monitor inventory trends by location and dimension levels to identify areas for improvement or cost savings

As a financial controller, use the report to:
* Analyze inventory trends by location and dimension levels to identify areas for cost savings or improvement
* Monitor inventory levels by dimension levels to ensure that inventory is optimized for each segment
* Calculate inventory turnover ratios and days in inventory for each dimension level to determine the effectiveness of inventory management

As a sales and marketing manager, use the report to:
* Analyze sales trends by location and dimension levels to identify areas for growth or improvement
* Use the data to plan promotions or markdowns for specific segments to improve sales
* Monitor inventory levels by dimension levels to ensure that inventory is optimized for each segment



## Analyze data by dimensions

[!INCLUDE[Analyze-data-by-dimensions](../includes/analyze-data-by-dimensions-report-include.md)]


## Try the report

Try the report here: [Item Dimensions - Total](https://businesscentral.dynamics.com?report=7151)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]


## See also

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad-hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]