---
title: How to Reserve Items 
description: You can reserve items for sales orders, purchase orders, and production orders. You can also reserve items in inventory or inbound on open document lines.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.forms: 498, 497
ms.date: 08/11/2022
ms.author: bholtorf

---
# Reserve Items

You can reserve items for sales orders, purchase orders, service orders, assembly orders, transfer orders, and production orders. You can also reserve items in inventory or inbound on open document or journal lines. You do this on the **Reservation** page.

Each line you open to reserve items on the **Reservation** page displays information about one type of line (sales, purchase, or journal) or inventory entry. The lines describe how many items are available to be reserved from each type of line or entry.

## Reserve items for sales

The following procedure describes how to reserve items from a sales order. The steps are similar for purchase, service, transfer, and assembly orders.
  
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, then choose the related link.  
2. Choose the sales order.
3. On the **Lines** FastTab, choose the **Reserve** action. The **Reservation** page opens.  
4. Select the line you want to reserve the items from.  
5. Choose one of the following actions.  

    |**Function**|**Description**|
    |------------------|---------------------|  
    |**Auto Reserve**|To automatically reserve items on the **Reservation** page.|  
    |**Reserve from Current Line**|To reserve the items from the document on the line you have selected.|  
    |**Cancel Reservation from Current Line**|To cancel reservation of the items in the document on the line you've selected.|

> [!NOTE]  
> If item tracking lines exist for the sales order, the reservation system will take you through special steps. Learn more in the [To reserve a specific serial or lot number](inventory-how-to-reserve-items.md#reserve-a-specific-serial-or-lot-number) section.  

## Reserve an item for a production order line

You can reserve items for production orders. You have to distinguish between production order lines, meaning the parent item, and production order components.

In the following procedure, a firm planned production order is used.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Order**, then choose the related link.  
2. Open the firm planned production order you want to reserve parent items for.  
3. Select the relevant production order line.  
4. On the **Lines** FastTab, choose the **Reserve** action.
5. On the **Reservation** page, select the **Sales Line, Order** line, then choose the **Reserve from Current Line** action.  

The quantity you entered in the firm planned production order line is now reserved.

## Reserve items for production order components

You can reserve items for production orders. You have to distinguish between production order lines, meaning the parent item, and production order components.

In the following procedure, a firm planned production order is used.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Order**, then choose the related link.  
2. Open the firm planned production order you want to reserve component items for.  
3. Select the relevant production order line.  
4. On the **Lines** FastTab, choose **Line**, then choose **Components**.  
5. Select the relevant component line.  
6. On the **Lines** FastTab, choose the **Reserve** action.  
7. On the **Reservation** page, select a line, then choose the **Reserve from Current Line** action.  

The quantity you entered in the firm planned production component line is now reserved.

## Change a reservation

Sometimes, you may want to change an item reservation.

1. From the document line you made the reservation from, on the **Lines** FastTab, choose the **Reserve** action.  
2. On the **Reservation** page, choose the **Reservation Entries** action.
3. On the **Reservation Entries** page, update the **Quantity** field on the line you want to change.
4. Confirm the subsequent message by choosing the **OK** button.

## Cancel a reservation

Sometimes, you may want to cancel an item reservation.

1. From the document line you want to cancel a reservation from, on the **Lines** FastTab, choose the **Reserve** action.  
2. On the **Reservation** page, choose the **Reservation Entries** action.  
3. On the **Reservation Entries** page, choose the **Cancel Reservation** action.  
4. Confirm the subsequent message by choosing the **Yes** button.  

## Reserve a specific serial or lot number

From outbound documents for item-tracked items, such as sales orders or production component lists, you can reserve specific serial or lot numbers. This may be relevant, for example, if you need production components from a specific lot to ensure consistency with earlier production batches, or because a customer has requested a specific serial number. Learn more at [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).

This practice is referred to as a specific reservation, because you reserve from the quantity of item X that belongs to lot X. In contrast, if you reserve only from quantities of item X, then it is simply a normal, non-specific, reservation. Learn more at [Design Details - Item Tracking and Reservations](design-details-item-tracking-and-reservations.md).

The following procedure is based on a sales order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then select the related link.  
2. Create a sales order line for an item-tracked item.  
3. Assign serial and lot numbers to the sales order line. Learn more at [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).
4. On the sales order line, choose the **Reserve** action.  
5. Choose the **Yes** button to reserve specific serial or lot numbers.  
6. On the **Item Tracking List** page, select the serial and lot number combination you have assigned.  
7. Choose the **OK** button to open the **Reservation** page showing only supply with the specified item tracking number. If there are any non-specific reservations on any of the item tracking numbers you've specified for this line, you're informed of the quantity that has already been reserved.  
8. Choose either the **Auto Reserve** or the **Reserve from Current Line** action to create the reservation of the specific item tracking numbers.

## See also

[Inventory](inventory-manage-inventory.md)  
[Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)  
[Design Details: Item Tracking and Reservations](design-details-item-tracking-and-reservations.md)  
[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
