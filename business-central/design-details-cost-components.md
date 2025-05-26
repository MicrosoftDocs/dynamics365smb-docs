---
title: Design Details - Cost Components | Microsoft Docs
description: Cost components are different types of costs that make up the value of an inventory increase or decrease.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords:
ms.date: 06/08/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Cost Components
Cost components are different types of costs that make up the value of an inventory increase or decrease.  

 The following table shows the different cost components and any subordinate cost components that they consist of.  

|Cost Component|Subordinate Cost Component|Description|  
|--------------------|--------------------------------|---------------------------------------|  
|Direct cost|Unit cost (direct purchase price)|Cost that can be traced to a cost object.|  
|Direct cost|Freight cost (item charge)|Cost that can be traced to a cost object.|  
|Direct cost|Insurance cost (item charge)|Cost that can be traced to a cost object.|  
|Indirect cost||Cost that cannot be traced to a cost object.|  
|Variance|Purchase variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Material variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Capacity variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Subcontracted variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Capacity overhead variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Variance|Manufacturing overhead variance|The difference between actual and standard costs, which is only posted for items using the **Standard** costing method.|  
|Revaluation||A depreciation or appreciation of the current inventory value.|  
|Rounding||Residuals caused by the way in which valuation of inventory decreases are calculated.|  

> [!NOTE]  
>  Freight and insurance costs are item charges that can be added to an item’s cost at any time. When you run the **Adjust Cost - Item Entries** batch job, the value of any related inventory decreases are updated accordingly.  

## Related information  
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Design Details: Variance](design-details-variance.md)
 [Managing Inventory Costs](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
