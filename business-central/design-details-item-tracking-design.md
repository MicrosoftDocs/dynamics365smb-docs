---
title: Design Details - Item Tracking Design
description: This topic describes the design behind item tracking in Business Central as it matures through product versions.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: design, item, tracking, tracing
ms.date: 06/08/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design Details: Item Tracking Design

Item tracking in [!INCLUDE[prod_short](includes/prod_short.md)] started with [!INCLUDE [navnow_md](includes/navnow_md.md)]. The item tracking functionality is in a separate object structure with intricate links to posted documents and item ledger entries, and it is integrated with the reservation system, which handles reservation, order tracking, and action messaging. For more information, see [Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md) in the Supply Planning design details.  

This design incorporates item tracking entries in total availability calculations throughout the system, including planning, manufacturing, and warehousing. Serial and lot numbers are applied on the item ledger entries to ensure simple access to historical data for item tracking purposes. With 2021 release wave 1, item tracking in [!INCLUDE [prod_short](includes/prod_short.md)] includes package numbers.  

With the addition of serial, lot, and package numbers, the reservation system handles permanent item attributes while also handling intermittent links between supply and demand in the form of order tracking entries and reservation entries. Another different characteristic of serial or lot numbers compared to the conventional reservation data is the fact that they can be posted, either partially or fully. Therefore, the **Reservation Entry** table (T337) now works with a related table, the **Tracking Specification** table (T336), which manages and displays summing across active and posted item tracking quantities. For more information, see [Design Details: Active versus Historic Item Tracking Entries](design-details-active-versus-historic-item-tracking-entries.md).  

The following diagram outlines the design of item tracking functionality in [!INCLUDE[prod_short](includes/prod_short.md)].  

![Example of item tracking flow.](media/design_details_item_tracking_design.png "Example of item tracking flow")  

The central posting object is redesigned to handle the unique subclassification of a document line in the form of serial or lot numbers, and special relation tables are added to create the one-to-many relations between posted documents and their split item ledger entries and value ledger entries.  

Codeunit 22, **Item Jnl. – Post Line**, now splits the posting according to the item tracking numbers that are specified on the document line. Each unique item tracking number on the line creates its own item ledger entry for the item. This means that the link from the posted document line to the associated item ledger entries is now a one-to-many relation. This relation is handled by the following item tracking relation tables.  

|Field|Description|  
|---------------|---------------------------------------|  
|**Item Entry Relation** (T6507)|Relates shipped or received lines to item ledger entries|  
|**Value Entry Relation** (T6508)|Relates invoiced lines to value entries|  

For more information, see [Design Details: Item Tracking Posting Structure](design-details-item-tracking-posting-structure.md).  

## Related information

[Design Details: Item Tracking](design-details-item-tracking.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]  
