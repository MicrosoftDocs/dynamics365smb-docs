---
    title: Design Details - Item Tracking and Planning | Microsoft Docs
    description: Because they are stored in the reservation system, item tracking numbers are fully coordinated with order tracking records.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Item Tracking and Planning
Because they are stored in the reservation system, item tracking numbers are fully coordinated with order tracking records. This means that items with order tracking records can be assigned item tracking numbers. Conversely, items that have item tracking numbers can become order tracking records. For more information, see [Design Details: Item Tracking Design](design-details-item-tracking-design.md).

For more information about the integrated systems, see [Design Details: Reservations, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md).

Because order tracking is only concerned with specific item application, the coordination with item tracking numbers only applies to items that are set up to use specific item tracking. This is set by the **SN Specific Tracking** and **Lot Specific Tracking** fields on the item card, which specify the following:

- The item must carry a serial number or lot number when it is posted.
- The item must apply to the same serial number or lot number when it is posted outbound.

In alignment with standard supply/demand balancing principles, the planning system and the related order tracking feature only match supply and demand carrying item tracking numbers if the item in question uses specific item tracking. In all other cases, the planning and order tracking systems ignore item tracking numbers when they apply supply to meet demand or apply demand to supply. For more information, see [Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md).

For example, when order tracking exists for a given item, it implies that records for the item are already in the **Reservation Entry** table, which is the core of the reservation system, before the item tracking numbers are defined. Therefore, the following coupling restrictions apply to the item tracking numbers to be order tracked:

- Demand with a serial number or lot number can only cover supply with the same serial number or lot number.
- Demand without a serial or lot number can cover any supply, with or without a serial or lot number.

Apart from their consequences on dynamic order tracking, the item tracking coupling restrictions do not affect the planning system significantly.

On the supply side, a serial or lot number is typically not entered until immediately before the order is posted, such as a purchase receipt into the warehouse. When entering a serial or lot number on the demand side, such as on a sales order, that serial or lot number is already in inventory. Accordingly, item tracking numbers are typically not an issue in supply planning.

For items that use specific item tracking, all demand carrying serial or lot numbers must be matched by corresponding supply. In most cases, it does not make sense to reorder a specific serial or lot number, so the planning of purchase or production supplies is probably not affected. However, when transferring items from one location to another, it is likely that the transfer is for a specific lot, so planning transfer supplies might be affected by the specific coupling restriction.

For more information, see [Design Details: Transfers in Planning](design-details-transfers-in-planning.md).

## Balancing Demand and Supply
If an item requires specific item tracking, then an order tracking link is made from all the item’s item tracking demand to any corresponding item tracking supply, with the sole limitation that supply should come before demand. If, under those circumstances, no item tracking supply can be found that corresponds to the item tracking-specific demand, then a new item tracking supply is created immediately and without considering order sizing, planning parameters, or rescheduling of existing supply of the same serial or lot number.

If item tracking numbers are assigned on the demand side or on the supply side without requiring specific item tracking, then an order track link is made from the demand to that supply, based on the most suitable timing and quantity, as in the usual balancing procedure. The specified item tracking number goes into the order tracking record in the same way that any specified item tracking quantity defines one end of the order tracking link. This means that the item tracking number that is entered is preserved while it is also part of the order tracking record.

If item tracking numbers are assigned on the supply side without requiring specific item tracking, then this supply is regarded as fixed by the planning system. No resizing or rescheduling is suggested for this supply, but the supply is taken into consideration when the planning system tries to meet the gross requirements.

For more information, see [Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md).  

## See Also  
[Design Details: Item Tracking Design](design-details-item-tracking-design.md)  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)  
[Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)  
