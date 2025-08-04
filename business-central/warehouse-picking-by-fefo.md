---
title: How to enable picking by FEFO
description: First-Expired-First-Out (FEFO) is a sorting method that ensures that items with the earliest expiration dates are picked first.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 08/12/2024
ms.service: dynamics-365-business-central
---
# Enable picking items by FEFO

First-Expired-First-Out (FEFO) is a sorting method that ensures that items with the earliest expiration dates are picked first.  

 This functionality only works when the following criteria are met:

- The item must be assigned an item tracking code where the **SN Warehouse Tracking**, **Lot Warehouse Tracking**, or **Package Warehouse Tracking** fields are selected. The item must be posted to inventory with an expiration date.
- On the location, the **Pick According to FEFO** toggle must be turned on.

Depending on which document you plan to use, make some more settings:

- **Inventory Pick**. You can use picking by FEFO for locations with and without bins.
- **Warehouse Pick**. On the location, the **Bin Mandatory** toggles must be turned on.

When all the criteria are met, the serial/lot-numbered items to pick are sorted with the oldest first in all picks and movements.  

> [!NOTE]  
> If some serial or lot-numbered items have specific tracking defined in the source document, such as sales order, then those are respected first and under them, the remaining, non-specific, serial/lot numbers are listed according to FEFO.
<br /><br />
If two serial or lot-numbered items have the same expiration date, [!INCLUDE [prod_short](includes/prod_short.md)] selects the item with the lowest serial or lot number.
<br /><br />
When picking serial or lot-numbered items in locations set up for directed put-away and pick, only quantities in bins of the type *Pick* are picked according to FEFO.  
<br /><br />
To enable movements according to FEFO, leave the **From Bin** field empty on the **Inventory Movement** or **Movement Worksheet** pages.  
<br /><br />
If the **Strict Expiration Posting** field is selected on the **Item Tracking Code Card**, only items that aren't expired are included in the pick, and the lines are sorted according to the FEFO principle.
<br /><br />
> If you posted the item to inventory without an expiration date, [!INCLUDE [prod_short](includes/prod_short.md)] populates the serial or lot number as a warehouse pick, but not an inventory pick.

## Related information  

[Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md)   
[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
