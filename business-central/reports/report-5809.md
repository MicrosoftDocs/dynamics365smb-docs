---
title: Item Expiration - Quantity (report)
description: Find on-hand stock that is expired or soon will. 
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_5809_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Item Expiration - Quantity (report)

The **Item Expiration - Quantity** report shows current inventory levels for items that you track expiration for.

Specify an ending date and period length formula. The report uses this information to calculate columns for three preceding periods of equal length. Inventory is then totaled for each period to show stock expiry, and inventory that expires either before or after the range.

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
Get an overview of the quantities of selected items in inventory with expiration dates in a certain period. The list shows the number of units of the selected item that will expire in a given time period. For each of the items you specify, the report shows the number of units that will expire during each of three periods of equal length and the total inventory quantity.

Use filters to specify what the report includes. If you don't set filters, the report will include all your records. The quantities in the report reflect only the quantities of the item for which expiration dates are defined.

### What the report does
Shows current inventory levels for items with expiration date tracking enabled.

You will specify an ending date and period length formula, which the report uses to calculate columns for three preceding periods of equal length. Inventory is then totalled for each date bucket to show stock expiry across the calculated periods, as well as any inventory that expires either before or after the range.

### Use cases
Highlight stock on hand that's expired or soon to be expired. 

Please include your data sources and URLs

-->

Quality control managers use the report to:

* Find expired on-hand stock, or stock that's about to expire.
* Take corrective actions, such as dispose of expired items or schedule a quality control check for items that are about to expire.
* Comply with regulatory requirements for tracking and disposing of expired inventory.

Warehouse managers use the report to:

* Find expired on-hand stock, or stock that's about to expire.
* Take corrective actions, such as dispose of expired items or schedule a quality control check for items that are about to expire.
* Adjust inventory levels based on expiration dates to ensure that the warehouse isn't storing unused or expired products.

Purchasing managers use the report to:

* Monitor the expiration date of inventory to ensure that the warehouse isn't storing unused or expired products.
* Negotiate better pricing with suppliers for items that are close to expiring.
* Plan purchasing activities based on the expiration date of inventory to optimize inventory levels and reduce waste.

## Try the report

Try the report here: [Item Expiration - Quantity](https://businesscentral.dynamics.com?report=5809)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Inventory and warehouse report overview](../inventory-WMS-reports.md)   
[Ad hoc analysis of inventory data](../ad-hoc-analysis-inventory.md)   
[Inventory analytics overview](../inventory-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]