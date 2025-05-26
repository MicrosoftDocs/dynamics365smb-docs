---
title: Design Details - Rounding
description: Rounding residuals can occur when you value the cost of an inventory decrease measured in a different quantity than the corresponding inventory increase.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/08/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Rounding
Rounding residuals can occur when you value the cost of an inventory decrease that is measured in a different quantity than the corresponding inventory increase. Rounding residuals are calculated for all costing methods when you run the **Adjust Cost - Item Entries** batch job.  

 When you use the average costing method, the rounding residual is calculated and recorded on a cumulative, entry-by-entry basis.  

 When you use a costing method other than Average, the rounding residual is calculated when the inventory increase has been fully applied, that is when the remaining quantity for the inventory increase is equal to zero. A separate entry is then created for the rounding residual, and the posting date on this rounding entry is the posting date of the last invoiced value entry of the inventory increase.  

## Example  
 The following example illustrates how different rounding residuals are handled for the average costing method and non-Average costing method, respectively. In both cases, the **Adjust Cost - Item Entries** batch job has been run.  

 The following table shows the item ledger entries that the example is based on.  

|Posting Date|Quantity|Entry No.|  
|------------------|--------------|---------------|  
|01-01-20|3|1|  
|02-01-20|-1|2|  
|03-01-20|-1|3|  
|04-01-20|-1|4|  

 For an item using the Average costing method, the rounding residual (1/300) is calculated with the first decrease (entry number 2) and is carried forward to entry number 3. Therefore, entry number 3 is valued at –3.34.  

 The following table shows the resulting value entries.  

|Posting Date|Quantity|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|------------------|--------------|----------------------------|---------------------------|---------------|  
|01-01-20|3|10|1|1|  
|02-01-20|-1|-3.33|2|2|  
|03-01-20|-1|-3.34|3|3|  
|04-01-20|-1|-3.33|4|4|  

 For an item using a costing method other than Average, the rounding residual (0.01) is calculated when the remaining quantity for the inventory increase is zero. The rounding residual has a separate entry (number 5).  

 The following table shows the resulting value entries.  

|Posting Date|Quantity|Cost Amount (Actual)|Item Ledger Entry No.|Entry No.|  
|------------------|--------------|----------------------------|---------------------------|---------------|  
|01-01-20|3|10|1|1|  
|02-01-20|-1|-3.33|2|2|  
|03-01-20|-1|-3.33|3|3|  
|04-01-20|-1|-3.33|4|4|  
|01-01-20|0|-0.01|1|5|  

## Related information  
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Design Details: Cost Adjustment](design-details-cost-adjustment.md)   
 [Design Details: Costing Methods](design-details-costing-methods.md)
 [Managing Inventory Costs](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
