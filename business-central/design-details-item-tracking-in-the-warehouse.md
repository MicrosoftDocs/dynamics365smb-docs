---
title: Design Details - Item Tracking in the Warehouse
description: Inbound and outbound warehouse documents have standard functionality for assigning and selecting item tracking numbers.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: design, item, tracking, serial number, lot number, outbound documents
ms.date: 06/15/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Item Tracking in the Warehouse
Serial number and lot number handling is primarily a warehouse task and therefore all inbound and outbound warehouse documents have standard functionality for assigning and selecting item tracking numbers.  

However, because the reservation system is based on item ledger entries, warehouse activity documents that register only warehouse entries are not fully supported. Because reservations and item tracking numbers can be handled only at the location level, not at the bin and zone level, the **Item Tracking Lines** page cannot be opened from warehouse activity documents. The same applies to the **Reservation** page.  

After a serial or lot number has been added to an item at a warehouse location, it can be moved and reclassified freely within the warehouse by using an independent item tracking structure that is unrelated to the reservation system. **Serial No.** and **Lot No.** fields are accessed directly on warehouse document lines. When the serial or lot number later partakes in outbound posting, it is synchronized with the reservation system as a part of ordinary bin adjustment. For more information, see [Design Details: Integration with Inventory](design-details-integration-with-inventory.md).  

However, the reservation system does take warehouse activities into consideration when it calculates availability. For example, items that are allocated to picks, or registered as picked, cannot be reserved. For more information, see [Design Details: Warehouse Availability](design-details-availability-in-the-warehouse.md).

## Related information  
[Design Details: Item Tracking](design-details-item-tracking.md)  
[Design Details: Integration with Inventory](design-details-integration-with-inventory.md)  
[Design Details: Warehouse Availability](design-details-availability-in-the-warehouse.md)  
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
