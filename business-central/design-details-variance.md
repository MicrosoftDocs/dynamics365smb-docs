---
title: Design details variance
description: Variance is the difference between the actual cost and the standard cost.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 07/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design details: variance

Variance is the difference between the actual cost and the standard cost, as described in the following formula:  

- actual cost – standard cost = variance  

If the actual cost changes, for example, because you post an item charge on a later date, the variance updates accordingly.  

> [!NOTE]  
> Revaluation doesn't affect the variance calculation because revaluation only changes the inventory value.  

## Example  

The following example illustrates how [!INCLUDE [prod_short](includes/prod_short.md)] calculates variance for purchased items based on the following scenario:  

1. You purchase an item for 90.00 in local currency (LCY), but the standard cost is LCY 100.00. Accordingly, the purchase variance is LCY –10.00.  
2. The purchase variance account is credited with LCY 10.00.  
3. You post an item charge of LCY 20.00. Accordingly, the actual cost increases to LCY 110.00, and the value of the purchase variance becomes LCY 10.00.  
4. The purchase variance account is debited with LCY 20.00. Accordingly, the net purchase variance becomes LCY 10.00.  
5. You revalue the item from LCY 100.00 to LCY 70.00. This doesn't affect the variance calculation, only the inventory value.  

The following table shows the resulting value entries.  

![Purchase variance calculation.](media/design_details_inventory_costing_11_purchase_variance.png "Purchase variance calculation")  

## Determining the standard cost  

The standard cost is used when calculating variance and the amount to capitalize. Because the standard cost can change over time due to manual update calculation, you need a point in time when the standard cost is fixed for variance calculation. This point is when you invoice the inventory increase. For produced or assembled items, the point when standard cost is determined is when the cost is adjusted.  

 The following table shows how different cost shares are calculated for produced and assembled items when you use the Calculate Standard Cost action.  

|Cost share|Purchased item|Produced/Assembled item|  
|----------------|--------------------|------------------------------|  
|**Standard Cost**||Single-Level Material Cost + Single-Level Material Non-Inventory Cost + Single-Level Capacity Cost + Single-Level Subcontrd. Cost + Single-Level Cap. Ovhd. Cost + Single-Level Mfg. Ovhd. Cost</br>Go to the **Manufacturing Setup** page and turn on the **Include Non-Inventory Items to Produced Items** toggle to include Single-Level Material Non-Inventory Cost into produced items. Single-Level Material Non-Inventory Cost cannot be included into cost of assembled items.|  
|**Single-Level Material Cost**|Unit Cost|Sum of standard or unit costs of components and subassemblies </br></br> Only items of type Inventory|  
|**Single-Level Material Non-Inventory Cost**|Not applicable|Sum of unit costs of components  </br></br> Only items of type Non-Inventory|
|**Single-Level Capacity Cost**|Not applicable|![Equation 2.](media/design_details_inventory_costing_11_equation_2.png "Equation 2")|  
|**Single-Level Subcontrd. Cost**|Not applicable|![Equation 3.](media/design_details_inventory_costing_11_equation_3.png "Equation 3")|  
|**Single-Level Cap. Ovhd Cost**|Not applicable|![Equation 4.](media/design_details_inventory_costing_11_equation_4.png "Equation 4")|  
|**Single-Level Mfg. Ovhd Cost**|Not applicable|(Single-Level Material Cost + Single-Level Material Non-Inventory Cost + Single-Level Capacity Cost + Single-Level Subcontrd. Cost + Single-Level Cap. Ovhd Cost) * Indirect Cost % / 100 + Overhead Rate|
|**Rolled-up Material Cost**|Unit Cost|![Equation 5.](media/design_details_inventory_costing_11_equation_5.png "Equation 5")|  
|**Rolled-up Material Non-Inventory Cost**|Not applicable|Sum of Rolled-up Material Non-Inventory Cost + Single-Level Material Non-Inventory Cost|
|**Rolled-up Capacity Cost**|Not applicable|![Equation 6.](media/design_details_inventory_costing_11_equation_6.png "Equation 6")|  
|**Rolled-Up Subcontracted Cost**|Not applicable|![Equation 7.](media/design_details_inventory_costing_11_equation_7.png "Equation 7")|  
|**Rolled-up Capacity Ovhd. Cost**|Not applicable|![Equation 8.](media/design_details_inventory_costing_11_equation_8.png "Equation 8")|  
|**Rolled-up Mfg. Ovhd. Cost**|Not applicable|![Equation 9.](media/design_details_inventory_costing_11_equation_9.png "Equation 9")|  

## Related information  
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Design Details: Costing Methods](design-details-costing-methods.md)
 [Managing Inventory Costs](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
