---
title: Warehouse Adjustment Bin (report)
description: Get an overview of adjustment bin usage (for advanced warehouse scenarios).
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_7320_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Warehouse Adjustment Bin (report)

The **Warehouse Adjustment Bin** report shows the remaining quantities in the adjustment bin.

This report is meant only for advanced warehouses.

Typically, the adjustment bin should be empty. There are two reasons for it to contain a quantity:

* When it's the result of physical counting process.
* When quantities are removed or added to the warehouse.

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
Warehouse Adjustment Bin

### What the report does
The *Warehouse Adjustment Bin* report shows the remaining quantities that are stored in the adjustment bin itself. 

This report is meant only for an advanced warehouse. 

Typically, the adjustment bin should be empty. There are two reasons for it to contain quantities. When it's the result of physical counting process, or if quantities are removed or added to the warehouse.


## What are warehouse adjustment bins used for?
In Dynamics 365 Business Central, a "Warehouse Adjustment Bin" is used to manage and correct discrepancies in inventory quantities within specific bins
Purpose: The primary purpose is to ensure inventory records are accurate by adjusting quantities when discrepancies are found. This could be due to errors during receiving, picking, shipping, or routine inventory counts.
Functionality: Adjustments are made to correct the recorded quantities to match the actual physical quantities. This involves either increasing or decreasing the quantity of items in a specific bin.
Process: Adjustments can be made manually or through a warehouse management system. Users can specify which bin the adjustment applies to, and whether the adjustment is an increase or decrease in quantity
Types of Adjustments: Positive Adjustments: When additional items are found and need to be added to the inventory. Negative Adjustments: When items are missing and need to be removed from the inventor


## Report use cases
The report helps businesses track changes in inventory levels within specific bins, ensuring accurate inventory records and efficient warehouse management.
Accurate adjustments help maintain precise inventory levels, which is essential for effective inventory management, accurate financial reporting, and optimal stock levels.


Please include your data sources and URLs

-->

Warehouse supervisors use the report to:

* Monitor the quantity of items in the adjustment bin and quickly find and address discrepancies.
* Analyze the root causes of discrepancies and take corrective action and prevent future discrepancies.
* Optimize warehouse processes, such as receiving, picking, and shipping, and reduce errors and improve accuracy.

Inventory managers use the report to:

* Monitor the quantity of items in the adjustment bin and ensure that inventory records are accurate and up-to-date.
* Help reconcile inventory records with physical inventory counts and make adjustments to ensure accurate financial reporting.
* Optimize inventory management processes, such as ordering and replenishing, and reduce discrepancies and improve accuracy.

Warehouse managers use the report to:

* Monitor the quantity of items in the adjustment bin and ensure that inventory records are accurate and up-to-date
* Identify trends or patterns in discrepancies and take action and prevent future discrepancies.
* Optimize warehouse processes and inventory management strategies for improved efficiency and accuracy.

## Try the report

Try the report here: [Warehouse Adjustment Bin](https://businesscentral.dynamics.com?report=7320)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)  
[Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)  
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]