---
    title: How to Enable Picking by FEFO | Microsoft Docs
    description: First-Expired-First-Out (FEFO) is a sorting method that ensures that the oldest items, those with the earliest expiration dates, are picked first.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2021
    ms.author: bholtorf

---
# Enable Picking Items by FEFO
First-Expired-First-Out (FEFO) is a sorting method that ensures that the oldest items, those with the earliest expiration dates, are picked first.  

 This functionality only works when the following criteria are met:  

-   The item must have a serial/lot number.  
-   On the item’s item tracking code setup, the **SN Warehouse Tracking** field or the **Lot Warehouse Tracking** field must be selected.  
-   The item must be posted to inventory with an expiration date.  
-   On the location, the **Require Pick**, **Pick According to FEFO**, and **Bin Mandatory** toggles must be turned on.  

 When all the criteria are met, then serial/lot-numbered items to be picked are sorted with the oldest first in all picks and movements, except for items that use SN-specific or lot-specific tracking.  

> [!NOTE]  
> If some serial or lot-numbered items use specific tracking, then those are respected first and under them, the remaining, non-specific, serial/lot numbers are listed according to FEFO.
<br /><br />
If two serial or lot-numbered items have the same expiration date, then the application selects the item with the lowest serial or lot number.
<br /><br />
When picking serial or lot-numbered items in locations set up for directed put-away and pick, only quantities on bins of type *Pick* are picked according to FEFO.  
<br /><br />
To enable movements according to FEFO, leave the **From Bin** field empty on the **Inventory Movement** page or the **Movement Worksheet** pages.  
<br /><br />
If the **Strict Expiration Posting** field is selected on the **Item Tracking Code Card**, only items that are not expired will be included in the pick, and the lines are sorted according to the FEFO principle.

## See Also  
[Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md)   
[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]