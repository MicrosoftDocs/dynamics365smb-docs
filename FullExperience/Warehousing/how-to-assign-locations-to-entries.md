---
title: "How to: Assign Locations to Entries"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "locations, assigning to entries"
ms.assetid: ba94c69d-4029-4844-8874-e084843a1c00
caps.latest.revision: 5
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Assign Locations to Entries
You can assign a location to an entry after you have posted it, for example, if you have forgotten to define a location for a purchase or sales order.  
  
### To assign a locations to a posted entry  
  
1.  In the **Search** box, enter **Item Reclass. Journal**, and then choose the related link.  
  
2.  In the **Item No.** field, enter the number of the item on the entry you want to assign a location to.  
  
3.  In the **New Location Code** field, enter the location you want to assign to the entry.  
  
4.  In the **Applies\-to Entry** field, enter the entry number of the entry to which you want to add the location information.  
  
5.  Post the entry.  
  
 When you use a journal line to add information on an entry, two item ledger entries are created, one with a negative quantity and the location code from the **Location Code** field, and one with a positive quantity and the location code from the **New Location Code** field.  
  
> [!NOTE]  
>  You cannot use the item reclassification journal to change a location if either the old or new location uses directed put\-away and pick. You must instead use the transfer order.  
  
## See Also  
 [Item Ledger Entries](../Topic/\($%20N_38%20Item%20Ledger%20Entries%20$\).md)   
 [Item Reclass. Journal](../WarehouseActivities/-$-n_393-item-reclass.-journal-$-.md)   
 [Count, Adjust, and Reclassify Inventory](../WarehouseActivities/count-adjust-and-reclassify-inventory.md)   
 [How to: Set Up Locations](../DesignAndEngineering/how-to-set-up-locations.md)