---
title: "How to: Set Up Physical Inventory Counting Periods"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, setting up counting periods"
  - "counting, setting up periods for physical inventories"
  - "inventory, counting"
  - "physical inventory, counting"
  - "counting, periods"
  - "assigning, counting periods"
ms.assetid: 9c3e786f-729e-429e-8af2-814d3a1d709e
caps.latest.revision: 5
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
# How to: Set Up Physical Inventory Counting Periods
A physical inventory is typically taken at some recurring interval, for example monthly, quarterly, or annually. You can set up whatever inventory counting periods necessary.  
  
 You set up the inventory counting periods that you want to use and then assign one to each SKU or item. When you perform a physical inventory and use the function **Calculate Counting Period** in the warehouse physical inventory journal or in the physical inventory journal, lines for the bins containing these items or SKUs are created automatically.  
  
### To set up counting periods  
  
1.  In the **Search** box, enter **\($ N\_7381 Phys. Invt. Counting Periods $\)**, and then choose the related link.  
  
2.  Fill in the **Code** field with a short descriptive code for the counting period.  
  
3.  Enter a short description in the **Description** field, if you wish.  
  
4.  Fill in the **Count Frequency per Year** field with the number of times you want to perform a physical inventory each year.  
  
### To assign a counting period to an item or stockkeeping unit  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Select the item to which you want to assign a counting period.  
  
3.  On the **Warehouse** FastTab, select the **Phys Invt Counting Period Code** field, and select the appropriate counting period.  
  
     Choose the **Yes** button to change the code and calculate the first counting period for the item. The next time you choose to calculate a counting period in the warehouse physical inventory journal, the item appears as a line in the **Phys. Invt. Item Selection** window. You can now begin to count the item on a periodic basis.  
  
## See Also  
 [How to: Perform a Physical Inventory](../DesignAndEngineering/how-to-perform-a-physical-inventory.md)   
 [\($ N\_7381 Phys. Invt. Counting Periods $\)](../Topic/\($%20N_7381%20Phys.%20Invt.%20Counting%20Periods%20$\).md)