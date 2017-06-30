---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Deactivate Item Cost Tracking
When inventory is not tracked for an item, the item cost does not need to be tracked, and an item ledger entry does not need to be created.  
  
 You can deactivate item cost tracking for an item. Generally, item cost tracking should be deactivated for consumable items, such as waste paper products and for services that are counted as items, such as flat rate parking fees. Item cost tracking should be deactivated on items for which tracking could be misleading. Items for which item cost tracking has been deactivated are excluded from reservation, availability check, item tracking, and material planning systems.  
  
### To deactivate item cost tracking  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Select the required item, and on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, select the **No Stockkeeping** check box.  
  
     An item ledger entry will not be created when you post a transaction for this item. For more information, see the Item Ledger Entry table.  
  
    > [!NOTE]  
    >  You cannot select the **No Stockkeeping** check box on an item for which item ledger entries have already been posted.  
  
4.  Choose the **OK** button.  
  
## See Also  
 Item   
 Item Ledger Entry   
 [Swiss Inventory Management](../swiss-inventory-management.md)   
 [How to: Block Inventory Items for Sales or Purchases](../how-to-block-inventory-items-for-sales-or-purchases.md)