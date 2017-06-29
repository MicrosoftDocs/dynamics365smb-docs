---
title: "Set Up Inventory Valuation and Costing"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "valuations, inventory"
  - "inventory, setting up"
  - "cost of goods, setting up"
  - "inventory costing"
  - "inventory valuation"
ms.assetid: 3fddfbd3-5ed8-4963-9434-48fc7b0ca06b
caps.latest.revision: 4
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
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
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
# Set Up Inventory Valuation and Costing
The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Set a costing method for each item to govern how its incoming cost is used to assess inventory value and the cost of goods sold.|[Design Details: Costing Methods](../ApplicationDesign/design-details-costing-methods.md)|  
|Ensure that the cost is automatically posted to the general ledger whenever an inventory transaction is posted.|Automatic Cost Posting|  
|Ensure that expected costs are posted to the general ledger to see from the interim G\/L accounts an estimate of the amounts due and the cost of the traded items before they are actually invoiced.|Expected Cost Posting to G\-L|  
|Set the system up to adjust for any cost changes automatically every time you post inventory transactions.|Automatic Cost Adjustment|  
|Define if the average cost is to be calculated per item only or per item for each stockkkeping unit and for each variant of the item.|Average Cost Calc. Type|  
|Select the period of time you would like the program to use for calculating the weighted average cost of items that use the average costing method.|Average Cost Period|  
|Define inventory periods to control inventory value over time by disallowing transaction posting in closed inventory periods.|"Creating Inventory Periods" in [Working with Inventory Periods](../Finance/how-to-work-with-inventory-periods.md)|  
|Ensure that sales returns are applied to the original transaction to preserve inventory value \(works the same way for purchase returns\).|Exact Cost Reversing Mandatory|  
|Predefine item charge types that you allow to be posted in relation to orders and thereby add to the unit cost of the traded items.|Item Charge|  
|Ensure that value entries posted with the item journal are not duplicated by value entries posted with the regular Post Cost to G\/L Batch Job.|[How to: Post Purchases and Inventory Adjustments](../Finance/how-to-post-purchases-and-inventory-adjustments.md)|  
|Set up the rounding rules to apply when adjusting or suggesting item prices and when adjusting or suggesting standard costs.|Rounding Method|  
  
## See Also  
 [Set Up Posting Groups](../Finance/set-up-posting-groups.md)   
 [Manage Inventory Costs](../Finance/manage-inventory-costs.md)