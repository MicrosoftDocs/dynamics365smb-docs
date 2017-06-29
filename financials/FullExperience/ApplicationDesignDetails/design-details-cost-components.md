---
title: "Design Details: Cost Components"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "cost components"
  - "costs, components"
ms.assetid: a0edd0ec-b901-4216-8e45-2e9beea1305b
caps.latest.revision: 7
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Design Details: Cost Components
Cost components are different types of costs that make up the value of an inventory increase or decrease.  
  
 The following table shows the different cost components and any subordinate cost components that they consist of.  
  
|Cost component|Subordinate cost component|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
|--------------------|--------------------------------|---------------------------------------|  
|Direct cost|Unit cost \(direct purchase price\)|Cost that can be traced to a cost object.|  
|Direct cost|Freight cost \(item charge\)|Cost that can be traced to a cost object.|  
|Direct cost|Insurance cost \(item charge\)|Cost that can be traced to a cost object.|  
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
>  Freight and insurance costs are item charges that can be added to an item’s cost at any time. When you run the **Adjust Cost \- Item Entries** batch job, the value of any related inventory decreases are updated accordingly.  
  
## See Also  
 [Design Details: Inventory Costing](../ApplicationDesign/design-details-inventory-costing.md)   
 [Design Details: Variance](../ApplicationDesign/design-details-variance.md)