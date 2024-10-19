---
title: Item Dimensions - Detail (report)
description: Analyse your item entries with dimension detail by building a grouping of dimensions for each permutation of dimension values, and view a breakdown of value entries for each segment
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_7150_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Item Dimensions - Detail (report)

The *Item Dimensions - Detail* report shows a breakdown of value entries based on dimension levels specified on the request page. 

Dimension levels are specified by selecting an analysis view configured with dimension codes, then picking a hierarchy of how the dimension groups are grouped under one another. Location is automatically included as a dimension.

This report can be based on analysis view entries from either sales, purchase or inventory areas.

## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with inventory.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Item Dimensions - Detail

### What the report does
Shows a breakdown of value entries based on dimension levels specified by the user. 

Dimension levels are specified by selecting an analysis view configured with dimension codes, then picking a hierarchy of how the dimension groups are grouped under one another. Location is automatically included as a dimension.

This report can be based on analysis view entries from either sales, purchase or inventory areas.

### Use cases
Analyse your item entries with dimension detail by building a grouping of dimensions for each permutation of dimension values, and view a breakdown of value entries for each segment

Please include your data sources and URLs

-->

As a supply chain manager, use the report to:
* Analyze inventory levels by dimension levels to ensure that inventory is optimized for each segment
* Use the data to plan purchasing activities for specific segments to optimize inventory levels and reduce waste
* Monitor inventory trends by location and dimension levels to identify areas for improvement or cost savings

As a financial analyst, use the report to:
* Analyze inventory trends by location and dimension levels to identify areas for cost savings or improvement
* Monitor inventory levels by dimension levels to ensure that inventory is optimized for each segment
* Calculate inventory turnover ratios and days in inventory for each dimension level to determine the effectiveness of inventory management

As a sales and marketing manager, use the report to:
* Analyze sales trends by location and dimension levels to identify areas for growth or improvement
* Use the data to plan promotions or markdowns for specific segments to improve sales
* Monitor inventory levels by dimension levels to ensure that inventory is optimized for each segment


## Analyze data by dimensions

Dimensions are values that categorize entries so you can track and analyze them on documents, such as sales or purchase orders. Dimensions can, for example, indicate the project or department an entry came from. An example is to set up a dimension called Department, then use that dimension when you post sales documents. This way, you can use business intelligence tools to see which department sold which items.

For more information, see 
* [Work with dimensions](../finance-dimensions.md)
* [Analyze data by dimensions](../bi-how-analyze-data-dimension.md)


## Try the report

Try the report here: [Item Dimensions - Detail](https://businesscentral.dynamics.com?report=7150)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]


## See also

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad-hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]