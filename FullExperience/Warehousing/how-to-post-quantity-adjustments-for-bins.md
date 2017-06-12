---
title: "How to: Post Quantity Adjustments for Bins"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "adjusting, bin quantities"
  - "bin quantity adjustments, without directed put-away and pick"
  - "bin quantity adjustments, with directed put-away and pick"
  - "bins, adjusting quantity"
  - "quantity posting, adjustments"
ms.assetid: 5666cca9-a582-4c19-9f8a-e8e96562ee50
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
# How to: Post Quantity Adjustments for Bins
If you are using bins at a location, you will need to occasionally adjust the quantity in a bin, when the quantity recorded in the system is inaccurate because of a physical gain or loss of an item. There are two methods of posting a quantity adjustment in a bin. Which one you use depends on whether the location is set up to use directed put\-away and pick or not. The two methods are described below.  
  
## Bin Adjustment in Basic Warehouse that Use Bins Only  
 If you are not using directed put\-away and pick at the location, you can change the quantity in a bin with the  **Item Journal** window. Posting the item journal adjusts the quantity in the item ledger entries and the related warehouse entries.  
  
#### To post bin adjustment in basic warehouses that use bins only  
  
1.  In the **Search** box, enter **Item Journal**, and then choose the related link.  
  
2.  Fill in the fields on each journal line.  
  
3.  Post the journal lines.  
  
## Bin Adjustment in Advanced Warehouses that Use Directed Put\-away and Pick  
 If you are using directed put\-away and pick at the location, you use the **Warehouse Item Journal** window to perform extraordinary quantity changes in the warehouse bins. For more information, see [How to: Register Quantity Adjustments in Warehouse Item Journals](../WarehouseActivities/how-to-register-quantity-adjustments-in-warehouse-item-journals.md).  
  
 When you register these differences, the positive and negative adjustment quantities are registered in the warehouse adjustment bin, but the quantities are not posted to the item ledger until you post the content of the adjustment bin.  
  
> [!NOTE]  
>  The entries in the adjustment bin may originate from the warehouse item journal, the warehouse physical inventory journal, the item journal, or a number of other documents that indicate changes in warehouse inventory. For more information, see [Warehouse Adjustment Bin](../Topic/\($%20R_7320%20Warehouse%20Adjustment%20Bin%20$\).md).  
  
 At appropriate intervals as defined by company policy, you must post the warehouse adjustment bin records in the item ledger. Some companies find it appropriate to post adjustments to the item ledger every day, while others may find it adequate to reconcile less frequently.  
  
#### To post bin adjustment in advanced warehouses that use directed put\-away and pick  
  
1.  In the **Search** box, enter **Item Journal**, and then choose the related link.  
  
2.  Fill in the fields on each journal line.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Calculate Whse. Adjustment**, and fill in the filters as appropriate in the batch job request window. The adjustments are calculated only for the entries in the adjustment bin that meet filter requirements.  
  
4.  On the **Options** FastTab, fill in the **Document No.** field with a number that you enter manually. Because no number series has been set up for this batch job, use the number scheme set up by the warehouse, or enter the date followed by your initials.  
  
5.  To run the **Calculate Whse. Adjustment** function, choose the **OK** button. The positive and negative adjustments are totaled for each item and lines are created in the item journal for any items where the sum is a positive or negative quantity.  
  
6.  Post the journal lines to enter the quantity differences in the item ledger. The inventory in the warehouse bins now corresponds precisely to the inventory in the item ledger.  
  
## See Also  
 [Count, Adjust, and Reclassify Inventory](../WarehouseActivities/count-adjust-and-reclassify-inventory.md)   
 [Warehouse Adjustment Bin](../WarehouseActivities/warehouse-adjustment-bin.md)   
 [Warehouse Item Journal](../Topic/\($%20N_7324%20Warehouse%20Item%20Journal%20$\).md)   
 [Bin Content](../Topic/\($%20N_7304%20Bin%20Content%20$\).md)   
 [Design Details: Warehouse Management](../ApplicationDesign/design-details-warehouse-management.md)