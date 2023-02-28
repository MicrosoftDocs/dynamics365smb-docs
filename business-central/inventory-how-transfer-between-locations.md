---
title: Transfer Items Between Warehouse Locations
description: Learn how to move inventory from one place or warehouse to another, either with the reclassification journal or with transfer orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: move, warehouse
ms.search.forms: 5746, 5745, 5759, 5753, 5743, 5758, 5752, 5744, 5749, 5740, 5741, 5742, 5757, 5748, 5747, 9285, 5756, 5755
---
# Transfer Inventory Between Locations

You can transfer inventory items between locations by creating transfer orders. Alternatively, you can use the item reclassification journal.

> [!NOTE]
> To transfer items, you must set up locations and transfer routes. To learn more about setting up locations, go to [Set Up Locations](inventory-how-setup-locations.md). You can't use transfer orders for *blank* locations.

## Transfer orders

You can ship an outbound transfer from one location and receive an inbound transfer at the destination. You can:

* Track a quantity in transit
* Define calendars, routings, and inbound and outbound handling times for date calculation and planning. To learn more about planning, go to [About Planning Functionality](production-about-planning-functionality.md).
* Use different warehouse features for inbound and outbound locations.
* With some limitations, you can use transfer orders for direct transfers.

## Item reclassification journals

* Simple, direct transfer of items between locations.
* Move items between bins. To learn more about transferring items between bins, go to [Move Items Unplanned in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)
* Change a lot or serial number to a new lot or serial number. To learn more about reclassifying serial and lot numbers, go to [Reclassify serial or lot numbers](inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers).
* Chang the expiration date to a new date.
* Reclassify items from a *blank* location to an actual location.
* Warehouse activities are not managed. Warehouse entries will be created.

## To transfer items with a transfer order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer orders**, and then choose the related link.
2. On the **Transfer Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >   If you filled in the **In-Transit Code**, **Shipping Agent Code**, and **Shipping Agent Service** fields on the **Trans. Route Spec.** page when you set up the transfer route, the corresponding fields on the transfer order are filled in automatically.

    When you fill in the **Shipping Agent Service** field, the receipt date at the transfer-to location is calculated by adding the shipping time of the shipping agent service to the shipment date.

3. To fill in the lines, either enter them manually or choose one of the following options on the under the **Functions** action:

    * Choose the **Get Bin Content** action to select existing items from a specific bin at the location.
    * Choose the **Get Receipt Lines** to select items that have just arrived at the transfer-from location.

    As a warehouse worker at the transfer-from location, proceed to ship the items.
4. Choose the **Post** action, choose the **Ship** option, and then choose the **OK** button.

    The items are now in transit between the specified locations, according to the specifies transfer route.

    As a warehouse worker at the transfer-from location, proceed to receive the items. The transfer order lines are the same as when shipped and cannot be edited.
5. Choose the **Post** action, choose the **Receive** option, and then choose the **OK** button.

## To transfer items with the item reclassification journal

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Reclass. Journals**, and then choose the related link.
2. On the **Item Reclass. Journal** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. In the **Location Code** field, enter the location where the items are currently stored.

    > [!NOTE]  
    > To transfer items that have no location code, leave the **Location Code** field blank.
4. In the **New Location Code** field, enter the location that you want to transfer the items to.
5. Choose the **Post** action.

## See related [Microsoft training](/training/modules/transfer-items/)

## See also

[Manage Inventory](inventory-manage-inventory.md)  
[Set Up Locations](inventory-how-setup-locations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
