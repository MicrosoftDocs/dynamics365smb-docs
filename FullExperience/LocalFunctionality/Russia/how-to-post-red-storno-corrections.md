---
title: "How to: Post Red Storno Corrections"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "inventory, posting corrections"
  - "correcting, item documents"
ms.assetid: 2c402146-f234-4652-92cd-67fa1de8dcd9
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Post Red Storno Corrections
You can set up inventory to use the same column for original and corrective postings. This is often referred to as *red storno*. You can use red storno posting to post the following inventory entries:  
  
-   Corrective entries in the item journal.  
  
-   Reversal of item documents such as item receipts and item shipments.  
  
-   Posting item revaluation or item reclassification journals.  
  
-   Periodic adjustments of item costs.  
  
> [!NOTE]  
>  You must enable red storno in the **\($ N\_461 Inventory Setup $\)** window before you can post corrective entries. For more information, see [Inventory Setup](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/inventory-setup.md).  
  
### To post corrective entries in the item journal  
  
1.  In the **Search** box, enter **Item Journal**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_83\_5 Entry Type $\)**|Select the same entry type as the original posting.|  
    |**\($ T\_83\_13 Quantity $\)**|Enter the quantity with the opposite sign of the original posting, such as **\-4**.|  
    |**\($ T\_83\_12460 Red Storno $\)**|Select to post as a corrective posting.|  
  
     You must also select the appropriate entries in the **\($ T\_83\_29 Applies\-to Entry $\)** or **\($ T\_83\_5807 Applies\-from Entry $\)** fields.  
  
3.  Post the journal.  
  
     The correction is posted, and any general ledger account correspondence that you have set up will be considered.  
  
### To reverse item documents  
  
1.  To reverse an item receipt, in the **Search** box, enter **Item Receipt**, and then choose the related link.  
  
     To reverse an item shipment, in the **Search** box, enter **Item Shipment**, and then choose the related link.  
  
2.  On the **General** FastTab, select the **\($ T\_12450\_30 Correction $\)** field.  
  
3.  On the **Actions** tab, in the **Process** group, choose **Copy Document**.  
  
4.  In the **\($ B\_12470 Copy Document $\)** window, set the appropriate filters, and then choose the **OK** button.  
  
5.  Make the needed changes to quantity and amounts.  
  
     You must also select the appropriate entries in the **\($ T\_12453\_29 Applies\-to Entry $\)** or **\($ T\_12453\_5807 Applies\-from Entry $\)** fields. These fields identify the incorrectly posted document.  
  
6.  Post the document.  
  
### To post item revaluation or item reclassification journals  
  
1.  To post an item revaluation, in the **Search** box, enter **Revaluation Journal**, and then choose the related link.  
  
     To post an item reclassification, in the **Search** box, enter **Item Reclass Journal**, and then choose the related link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_83\_29 Applies\-to Entry $\)**|Specifies the item entry that you want to revalue or reclassify.|  
    |**\($ T\_83\_5807 Applies\-from Entry $\)**|Specifies the item entry that you want to revalue or reclassify.|  
    |**\($ T\_83\_12460 Red Storno $\)**|Select to post as a corrective posting.|  
  
3.  Post the document.  
  
## See Also  
 [Inventory Setup](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/inventory-setup.md)   
 [\($ T\_83 Item Journal Line $\)](../Topic/\($%20T_83%20Item%20Journal%20Line%20$\).md)