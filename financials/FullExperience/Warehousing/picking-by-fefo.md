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
# Picking by FEFO
First-Expired-First-Out \(FEFO\) is a sorting method that ensures that the oldest items, those with the earliest expiration dates, are picked first.  
  
 This functionality only works when the following criteria are met:  
  
-   The item must have a serial\/lot number.  
  
-   On the item’s item tracking code setup, the **SN-Specific Warehouse Tracking** field or the **Lot-Specific Warehouse Tracking** field must be selected.  
  
-   The item must be posted to inventory with an expiration date.  
  
-   On the location card, the **Require Pick** check box must be selected.  
  
-   On the location card, the **Pick According to FEFO** check box must be selected.  
  
-   On the location card, the **Bin Mandatory** check box must be selected.  
  
 When all the criteria are met, then serial\/lot-numbered items to be picked are sorted with the oldest first in all picks and movements, except for items that use SN-specific or lot-specific tracking.  
  
> [!NOTE]  
>  If some serial\/lot-numbered items use specific tracking, then those are respected first and under them, the remaining, non-specific, serial\/lot numbers are listed according to FEFO.  
  
 If two serial\/lot-numbered items have the same expiration date, then the program selects the item with the lowest serial or lot number. If the serial or lot numbers are the same, then the program selects the item that was registered first.  
  
> [!NOTE]  
>  -   When picking serial\/lot-numbered items in locations set up for directed put-away and pick, only quantities on bins of type *Pick* are picked according to FEFO.  
> -   To enable movements according to FEFO, either in the **Inventory Movement** window or the **Movement Worksheet** window, you must leave the **From Bin** field empty.  
> -   If the **Strict Expiration Posting** field is selected, then only items that are not expired will be included in the pick. This applies even if you are not using Pick according to FEFO.  
  
## See Also  
 [Pick Items](../FullExperience/pick-items.md)   
 SN Specific Tracking   
 Require Pick   
 Inventory Movement   
 Movement Worksheet   
 [How to: Pick Items for Warehouse Shipment](../FullExperience/how-to-pick-items-for-warehouse-shipment.md)   
 [How to: Pick Items with Inventory Picks](../FullExperience/how-to-pick-items-with-inventory-picks.md)   
 Strict Expiration Posting   
 Pick According to FEFO   
 Bin Mandatory