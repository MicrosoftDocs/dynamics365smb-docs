---
title: Transfer Items Between Warehouse Locations| Microsoft Docs
description: Describes how to move inventory from one place or warehouse to another, either with the reclassification journal or with transfer orders.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: move, warehouse
ms.date: 01/25/2018
ms.author: SorenGP

---
# Transfer Inventory Between Locations
You can transfer inventory items between locations by creating transfer orders. Alternatively, you can use the item reclassification journal.

With transfer orders, you ship the outbound transfer from one location and receive the inbound transfer at the other location. This allows you to manage the involved warehouse activities and provides more certainty that inventory quantities are updated correctly.

With the reclassification journal, you simply fill in the **Location Code** and the **New Location Code** fields. When you post the journal, the item ledger entries are adjusted at the locations in question. With this method, warehouse activities are not managed.

> [!NOTE]  
>   If you have items recorded in your inventory without a location code, for example from a time when you only had one warehouse, then you cannot transfer those items using transfer orders. Instead, you must use the reclassification journal to reclassify the items from a blank location code to an actual location code.  For more information, see step 3 in the "To transfer items with the item reclassification journal" section.

To transfer items, locations and transfer routes must be set up. For more information, see [Set Up Locations](inventory-how-setup-locations.md).

## To transfer items with a transfer order
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer orders**, and then choose the related link.
2. In the **Transfer Order** window, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >   If you have filled in the **In-Transit Code**, **Shipping Agent Code**, and **Shipping Agent Service** fields in the **Trans. Route Spec.** window when you set up the transfer route, then the corresponding fields on the transfer order are filled in automatically.

    When you fill in the **Shipping Agent Service** field, the receipt date at the transfer-to location is calculated by adding the shipping time of the shipping agent service to the shipment date.

    As a warehouse worker at the transfer-from location, proceed to ship the items.
3. Choose the **Post** action, choose the **Ship** option, and then choose the **OK** button.

    The items are now in transit between the specified locations, according to the specifies transfer route.

    As a warehouse worker at the transfer-from location, proceed to receive the items.
4. Choose the **Post** action, choose the **Receive** option, and then choose the **OK** button.

## To transfer items with the item reclassification journal
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Reclass. Journals**, and then choose the related link.
2. In the **Item Reclass. Journal** window, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. In the **Location Code** field, enter the location where the items are currently stored.

    > [!NOTE]  
    >   To transfer items that have no location code, leave the **Location Code** field blank.
4. In the **New Location Code** field, enter the location that you want to transfer the items to.
5. Choose the **Post** action.

## See Also
[Manage Inventory](inventory-manage-inventory.md)  
[Set Up Locations](inventory-how-setup-locations.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Changing Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)
