---
title: "How to: Make General Changes in Direct Unit Cost"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "direct unit costs"
ms.assetid: 38ead21e-98ed-44eb-9c3c-e0f3252a14e2
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
# How to: Make General Changes in Direct Unit Cost
If you need to change the direct unit cost for several items, you can use the **\($ B\_794 Adjust Item Costs\/Prices $\)** batch job.  
  
 The batch job changes the contents in the **Unit Price** field on the item card. The batch job changes the content of the field in the same way for all items or selected items. The batch job multiplies the value in the field by an adjustment factor that you specify.  
  
### To make a general change in direct unit cost  
  
1.  In the **Search** box, enter **\($ B\_794 Adjust Item Costs\/Prices $\)**, and then choose the related link.  
  
2.  On the **Options** FastTab, in the **Adjust Field** field, specify which item or SKU card field you want to adjust.  
  
3.  In the **Adjustment Factor** field, specify the factor by which the value will be adjusted. For example, enter **1.5** to increase the value by 50%.  
  
4.  On the **Item** FastTab, set filters to specify, for example, which items to process with the batch job.  
  
5.  Choose the **OK** button.  
  
## See Also  
 [\($ B\_794 Adjust Item Costs\-Prices $\)](../Finance/-$-b_794-adjust-item-costs-prices-$-.md)