---
title: "Unit Cost Calculation"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "direct costs, calculating"
  - "unit costs, calculating"
  - "costs, calculating"
  - "average costs, unit cost calculations"
ms.assetid: 336da59e-eb99-4116-b2b3-96bd43b30a3f
caps.latest.revision: 4
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
---
# Unit Cost Calculation
As a rule, the value in the [\($ T\_27\_22 Unit Cost $\)](../Finance/-$-t_27_22-unit-cost-$-.md) field on the item card is based on the standard cost for items with costing method standard. For items with all other costing methods, it is based on the calculation of the inventory available \(invoiced costs and expected costs\) divided by the quantity on hand.  
  
 How the contents of the **Costing Method** field influence the unit cost calculation for purchases and sales is described in more detail in the following sections.  
  
## Unit Cost Calculation for Purchases  
 When you purchase items, the value in the **Last Direct Cost** field on the item card is copied to the [\($ T\_39\_22 Direct Unit Cost $\)](../Topic/\($%20T_39_22%20Direct%20Unit%20Cost%20$\).md) field on a purchase line or to the [\($ T\_83\_16 Unit Amount $\)](../Topic/\($%20T_83_16%20Unit%20Amount%20$\).md) line on an item journal line.  
  
 What you select in the **Costing Method** field influences how [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] calculates the contents of the **Unit Cost** field on the lines.  
  
### Costing Method FIFO, LIFO, Specific, or Average  
 [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] calculates the contents of the [\($ T\_39\_23 Unit Cost \(LCY\) $\)](../Topic/\($%20T_39_23%20Unit%20Cost%20\(LCY\)%20$\).md) field on the purchase line or the contents of the [\($ T\_83\_17 Unit Cost $\)](../Topic/\($%20T_83_17%20Unit%20Cost%20$\).md) field on the item journal line according to the following formula:  
  
 Unit Cost \(LCY\) \= \(Direct Unit Cost – \(Discount Amount\/ Quantity\)\) \* \(1 \+ Indirect Cost %" \/ 100\)\) \+ Overhead Rate  
  
### Costing Method Standard  
 The **Unit Cost \(LCY\)** field on the purchase line or the **Unit Cost** field is filled on the item journal line by copying the value in the **Unit Cost** field on the item card. By using costing method set as Standard, this is always based on the standard cost.  
  
 When you post the purchase, the unit cost from the purchase line or item journal line is copied to the purchase item invoice entry, and it can be seen on the entry list for the item.  
  
### All Costing Methods  
 The unit cost from the source document line is used to calculate the contents of the [\($ T\_5802\_43 Cost Amount \(Actual\) $\)](../Topic/\($%20T_5802_43%20Cost%20Amount%20\(Actual\)%20$\).md) field, or if applicable, the [\($ T\_5802\_151 Cost Amount \(Expected\) $\)](../Topic/\($%20T_5802_151%20Cost%20Amount%20\(Expected\)%20$\).md) field that relates to this item entry, regardless of the costing method of the item.  
  
## Unit Cost Calculation for Sales  
 When you sell items, the unit cost is copied from the [\($ T\_27\_22 Unit Cost $\)](../Finance/-$-t_27_22-unit-cost-$-.md) field on the item card to the sales line or the item journal line.  
  
 When you post, the unit cost is copied to the sales invoice item entry, and it can be seen on the entry list for the item. [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] uses the unit cost from the source document line to calculate the contents of the [\($ T\_5802\_43 Cost Amount \(Actual\) $\)](../Topic/\($%20T_5802_43%20Cost%20Amount%20\(Actual\)%20$\).md) field, or if applicable, the [\($ T\_5802\_151 Cost Amount \(Expected\) $\)](../Topic/\($%20T_5802_151%20Cost%20Amount%20\(Expected\)%20$\).md) field in the value entry related to this item entry.  
  
## See Also  
 [\($ T\_27\_21 Costing Method $\)](../Topic/\($%20T_27_21%20Costing%20Method%20$\).md)   
 [\($ T\_5802 Value Entry $\)](../Finance/-$-t_5802-value-entry-$-.md)   
 [Average Cost](../Finance/average-cost.md)