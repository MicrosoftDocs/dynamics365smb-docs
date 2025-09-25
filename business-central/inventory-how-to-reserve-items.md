---
title: How to reserve items 
description: Learn about reserving items for sales orders, purchase orders, and production orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords:
ms.search.forms: 498, 497
ms.date: 06/10/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Reserve items

You can reserve items for sales orders, purchase orders, service orders, assembly orders, transfer orders, and production orders. You can also reserve items in inventory or inbound on open document or journal lines.

Each line you open to reserve items displays information about one type of line (sales, purchase, or journal) or inventory entry. The lines describe how many items are available to be reserved from each type of line or entry.

> [!TIP]
> Based on the quantities you reserve in inventory, [!INCLUDE [prod_short](includes/prod_short.md)] displays a status on the documents so that you’re quickly aware of the next step. For example, to indicate that you can ship a sales order or start to work on a project, assembly, or production order. The status also helps reduce the risk of accidental partial shipments or hold-ups due to missing stock for production and assembly orders.
>
> The **Reserved from stock** field can help you understand whether you can ship or pick for a specific order or order line. For lines, the Reserved from stock field is available on FactBoxes. To access the information for the entire order, the field is on the **Statistics** page.

## Reserve items for sales

The following procedure describes how to reserve items from a sales order. The steps are similar for purchase, service, transfer, and assembly orders.
  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, then choose the related link.  
2. Choose the sales order.
3. On the **Lines** FastTab, choose the **Reserve** action. The **Reservation** page opens.  
4. Select the line you want to reserve the items from.  
5. Choose one of the following actions.  

    |**Action**|**Description**|
    |------------------|---------------------|  
    |**Auto Reserve**|Automatically reserve items on the **Reservation** page.|  
    |**Reserve from Current Line**|Reserve the items on the selected line.|  
    |**Cancel Reservation from Current Line**|Cancel reservation of the items on the selected line.|

> [!NOTE]  
> If there are item tracking lines for the sales order, the reservation system takes you through a few special steps. Learn more at [To reserve a specific serial or lot number](inventory-how-to-reserve-items.md#reserve-a-specific-serial-or-lot-number).  

## Reserve an item for a production order line

You can reserve items for production orders. You must distinguish between production order lines, meaning the parent item, and production order components.

In the following procedure, a firm planned production order is used.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Firm Planned Prod. Order**, then choose the related link.  
2. Open the firm planned production order you want to reserve parent items for.  
3. Select the relevant production order line.  
4. On the **Lines** FastTab, in the **Functions** group, choose the **Reserve** action.
5. On the **Reservation** page, select the Sales Line, Order Line, then choose the **Reserve from Current Line** action.  

The quantity you entered in the firm planned production order line is now reserved.

## Reserve items for production order components

You can reserve items for production orders. You have to distinguish between production order lines, meaning the parent item, and production order components.

In the following procedure, a firm planned production order is used.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Firm Planned Prod. Order**, then choose the related link.  
2. Open the firm planned production order you want to reserve component items for.  
3. Select the relevant production order line.  
4. On the **Lines** FastTab, choose **Line**, then choose **Components**.  
5. Select the relevant component line.  
6. On the **Lines** FastTab, choose the **Reserve** action.  
7. On the **Reservation** page, select a line, then choose the **Reserve from Current Line** action.  

The quantity you entered in the firm planned production component line is now reserved.

## Reserve items in bulk

Use the **Reservation Worksheet** page to reserve and allocate incoming goods in bulk. For example, bulk reservations can help ensure that quantities are available for your sales and production orders. You can have multiple batches for different purposes. For example, you might allocate production orders on a weekly basis but reserve daily for sales.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Reservation Worksheet**, then choose the related link.  
1. Choose the **Get Demand** action. The **Get Demand to Reserve** page opens.
1. On the **Get Demand to Reserve** page, specify the kind of demand you want to reserve from available inventory.
1. Fill in the filters as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. Optional: To allocate the items right away, choose the **Allocate** action.
1. On the **Allocation Policy** page, choose a policy for each step.

   |Allocation policy  |Description  |
   |---------|---------|
   |Basic (No Conflicts)     | Allocates stock to a demand if there are no conflicts and the demand can be fully covered. For example, you have sales order A with a quantity of 10, and a job with a quantity of 7. If you have 20 in stock, both demands receive full quantity. If your stock is 12, no stock is allocated. You must manually allocate the quantity.        |
   |Equally    | Distributes available stock to demand equally. For example, you have a sales order with a quantity of 10, and a job with a quantity of 7. If your stock level is 20, then both demands receive full quantity. If your stock is 12, both demands get 6.        |
   |By Customer Priority|Distribution based on the **Priority** field on the **Customer Card** page. In cases of low inventory quantities, [!INCLUDE [prod_short](includes/prod_short.md)] supplies higher-priority customers first.|

1. To reserve all lines where **Accept** is turned on, choose the **Make reservation** action.

## Change a reservation

You can change an item reservation.

1. On the document line you made the reservation from, on the **Lines** FastTab, choose the **Reserve** action.  
2. On the **Reservation** page, choose the **Reservation Entries** action.
3. On the **Reservation Entries** page, update the **Quantity** field on the line you want to change.
4. Confirm the subsequent message by choosing the **OK** button.

## Cancel a reservation

You can cancel an item reservation.

1. From the document line you want to cancel a reservation from, on the **Lines** FastTab, choose the **Reserve** action.  
2. On the **Reservation** page, choose the **Reservation Entries** action on the **Lines** FastTab.  
3. On the **Reservation Entries** page, choose the **Cancel Reservation** action.  
4. Confirm the subsequent message by choosing the **Yes** button.  

## Reserve a specific serial or lot number

From outbound documents for item-tracked items, such as sales orders or production component lists, you can reserve specific serial or lot numbers. For example, reserving specific serial or lot numbers can be useful in the following situations:

* You need production components from a specific lot to ensure consistency with earlier production batches.
* Because a customer requested a specific serial number.

Learn more at [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).

This practice is referred to as a specific reservation, because you reserve from the quantity of item X that belongs to lot X. In contrast, if you reserve only from quantities of item X, then it's simply a normal, nonspecific, reservation. Learn more at [Design Details - Item Tracking and Reservations](design-details-item-tracking-and-reservations.md).

The following procedure is based on a sales order.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then select the related link.  
2. Create a sales order line for an item-tracked item.  
3. Assign serial and lot numbers to the sales order line. Learn more at [Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md).
4. On the sales order line, choose the **Reserve** action.  
5. Choose the **Yes** button to reserve specific serial or lot numbers.  
6. On the **Item Tracking List** page, select the serial and lot number combination you assigned.  
7. Choose the **OK** button to open the **Reservation** page showing only supply with the specified item tracking number. If the line has nonspecific reservations on any of the item tracking numbers, you're informed of the quantity that is already reserved.  
8. Choose either the **Auto Reserve** or the **Reserve from Current Line** action to create the reservation of the specific item tracking numbers.

## Related information

[Inventory](inventory-manage-inventory.md)  
[Design Details: Reservation, Order Tracking, and Action Messaging](design-details-reservation-order-tracking-and-action-messaging.md)  
[Design Details: Item Tracking and Reservations](design-details-item-tracking-and-reservations.md)  
[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
