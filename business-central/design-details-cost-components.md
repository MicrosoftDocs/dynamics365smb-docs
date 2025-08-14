---
title: Design details cost components
description: Cost components are different types of costs that make up the value of an inventory increase or decrease.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords:
ms.date: 07/01/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Design details: cost components

Cost components are different types of costs that make up the value of an inventory increase or decrease.  

The following table shows the different cost components and any subordinate cost components that they consist of.  

|Cost component|Subordinate cost component|Description|  
|--------------------|--------------------------------|---------------------------------------|  
|Direct cost|Unit cost (direct purchase price)|Cost that you can trace to a cost object.|  
|Direct cost|Freight cost (item charge)|Cost that you can trace to a cost object.|  
|Direct cost|Insurance cost (item charge)|Cost that can be traced to a cost object.|  
|Indirect cost||Cost that you can't trace to a cost object.|  
|Direct cost-Non Inventory||Cost that you can't trace to a cost object.|
|Variance|Purchase variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Material variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Capacity variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Subcontracted variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Capacity overhead variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Manufacturing overhead variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Direct Cost - Non Inventory|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|
|Revaluation||A depreciation or appreciation of the current inventory value.|  
|Rounding||Residuals caused by the way in which valuation of inventory decreases are calculated.|  

> [!NOTE]  
> Freight and insurance costs are item charges that you can add to an item’s cost at any time. When you run the **Adjust Cost - Item Entries** batch job, the value of related inventory decreases update accordingly.  

## Examples

The tables in the following sections explain the accounts in more detail. They show the posting setups that include the accounts, and how the records are used.

### Assembly output

**Account**

|Page  |Field  |Source  |
|---------|---------|---------|
|Inventory Posting Setup     | Inventory Account         | * The Inventory Posting Group comes from the assembly item.<br>* The Location Code comes from the assembly order.         |

**Balancing Account**

|Page  |Field  |Source  |
|---------|---------|---------|
|General Posting Setup     | Inventory Adjustment Account         | * The General Business Posting Group comes from the assembly order.<br>* The General Product Posting Group comes from the assembly item.<br><br>The following field values are also transferred from the inventory posting setup:<br><br>* Material Variance<br>* Capacity Variance Account<br>* Capacity Overhead Variance Account<br>* Manufacturing Overhead Variance Account where the Inventory Posting Group comes from the assembly item and the Location Code comes from the assembly order.         |

## Related information  

[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Variance](design-details-variance.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
