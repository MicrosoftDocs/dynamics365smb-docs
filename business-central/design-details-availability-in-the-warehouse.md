---
title: Design Details - Availability in the Warehouse
description: Learn about the different factors that affect item availability in your warehouse.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 02/22/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Design Details: Availability in the Warehouse

Stay on top of item availability to ensure that outbound orders flow efficiently, and that your delivery times are optimal.  

Availability can vary, depending on several factors. Fr example:

* Allocations at the bin level when warehouse activities such as picks and movements happen.
* When the inventory reservation system imposes restrictions to comply with.

Before allocating quantities to picks for outbound flows, [!INCLUDE [prod_short](includes/prod_short.md)] verifies that all conditions are met.

When conditions aren't met, error messages are shown. One typical message is the generic "Nothing to handle." message. The message can be shown for many different reasons in outbound and inbound flows where a document line contains the **Qty. to Handle** field.

## Bin content and reservations  

Item quantities exist both as warehouse entries and as item ledger entries in inventory. These two types of entries contain different information about where items are and whether they're available. Warehouse entries define an item’s availability by bin and bin type, which is called bin content. Item ledger entries define an item’s availability by its reservation for outbound documents.  

[!INCLUDE [prod_short](includes/prod_short.md)] calculates the quantity that's available to pick when bin content is coupled with reservations.  

## Quantity available to pick  

[!INCLUDE [prod_short](includes/prod_short.md)] reserves items for pending sales order shipments so that they aren't picked for other sales orders that ship earlier. [!INCLUDE [prod_short](includes/prod_short.md)] subtracts quantities of items that are already being processed, as follows:

* Quantities reserved for other outbound documents.
* Quantities on existing pick documents.
* Quantities picked but not yet shipped or consumed.  

The result is calculated dynamically and displayed in the **Available Qty. to Pick** field on the **Pick Worksheet** page. The value is also calculated when users create warehouse picks directly for outbound documents. The following are examples of outbound documents:

* Sales orders
* Production consumption
* Outbound transfers

The result is available in these documents in the quantity fields, such as the **Qty. to Handle** field.  

> [!NOTE]  
> For the priority of reservations, the quantity to reserve is subtracted from the quantity available to pick. For example, if the quantity available in pick bins is 5 units, but 100 units are in put-away bins, when you reserve more than 5 units for another order, an error message is displayed because the additional quantity must be available in pick bins.  

### Calculating the quantity available to pick  

[!INCLUDE [prod_short](includes/prod_short.md)] calculates the quantity available to pick as follows:  

quantity available to pick = quantity in pick bins - quantity on picks and movements – (reserved quantity in pick bins + reserved quantity on picks and movements)  

The following diagram shows the different elements of the calculation.  

![Available to pick with reservation overlap.](media/design_details_warehouse_management_availability_2.png "Available to pick with reservation overlap")  

## Quantity available to reserve

Because the concepts of bin content and reservation coexist, the quantity of items that are available to reserve must align with allocations to outbound warehouse documents.  

You can reserve all inventory items, except items for which outbound processing has started. The quantity that's available to reserve is defined as the quantity on all documents and bin types. The following outbound quantities are exceptions:  

* Quantity on unregistered pick documents  
* Quantity in shipment bins  
* Quantity in to-production bins  
* Quantity in open shop floor bins  
* Quantity in to-assembly bins  
* Quantity in adjustment bins  

The result is displayed in the **Total Available Quantity** field on the **Reservation** page.  

On a reservation line, the quantity that can't be reserved because it's allocated in the warehouse is displayed in the **Qty. Allocated in Warehouse** field on the **Reservation** page.  

## Check whether items are available for picking

[!INCLUDE [inventory-availability-overview](includes/inventory-availability-overview.md)]

### Calculating the quantity available to reserve

[!INCLUDE [prod_short](includes/prod_short.md)] calculates the quantity available to reserve as follows:  

quantity available to reserve = total quantity in inventory - quantity on picks and movements for source documents - reserved quantity - quantity in outbound bins  

The following diagram shows the different elements of the calculation.  

![Avaliable to reserve per warehouse allocation.](media/design_details_warehouse_management_availability_3.png "Avaliable to reserve per warehouse allocation")  

## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)
[View the Availability of Items](inventory-how-availability-overview.md)
[Pick for Production, Assembly, or Jobs in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
