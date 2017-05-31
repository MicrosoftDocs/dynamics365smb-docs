---
title: "How to: Deactivate Item Cost Tracking"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "stockkeeping, deactivating"
  - "item cost tracking deactivation"
ms.assetid: cbd9683e-e406-4e39-afc7-3add2876c60b
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Deactivate Item Cost Tracking
When inventory is not tracked for an item, the item cost does not need to be tracked, and an item ledger entry does not need to be created.  
  
 You can deactivate item cost tracking for an item. Generally, item cost tracking should be deactivated for consumable items, such as waste paper products and for services that are counted as items, such as flat rate parking fees. Item cost tracking should be deactivated on items for which tracking could be misleading. Items for which item cost tracking has been deactivated are excluded from reservation, availability check, item tracking, and material planning systems.  
  
### To deactivate item cost tracking  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Select the required item, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, select the **\($ T\_27\_11500 No Stockkeeping $\)** check box.  
  
     An item ledger entry will not be created when you post a transaction for this item. For more information, see the [\($ T\_32 Item Ledger Entry $\)](../Topic/\($%20T_32%20Item%20Ledger%20Entry%20$\).md) table.  
  
    > [!NOTE]  
    >  You cannot select the **\($ T\_27\_11500 No Stockkeeping $\)** check box on an item for which item ledger entries have already been posted.  
  
4.  Choose the **OK** button.  
  
## See Also  
 [\($ T\_27 Item $\)](../Topic/\($%20T_27%20Item%20$\).md)   
 [\($ T\_32 Item Ledger Entry $\)](../Topic/\($%20T_32%20Item%20Ledger%20Entry%20$\).md)   
 [Swiss Inventory Management](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-inventory-management.md)   
 [How to: Block Inventory Items for Sales or Purchases](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-block-inventory-items-for-sales-or-purchases.md)