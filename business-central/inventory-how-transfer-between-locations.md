---
title: Transfer items between warehouse locations
description: Learn how to move inventory from one place or warehouse to another, either with the reclassification journal or with transfer orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 08/12/2024
ms.custom: bap-template
ms.search.keywords: move, warehouse
ms.search.forms: 5746, 5745, 5759, 5753, 5743, 5758, 5752, 5744, 5749, 5740, 5741, 5742, 5757, 5748, 5747, 9285, 5756, 5755
ms.service: dynamics-365-business-central
---

# Transfer inventory between locations

You can transfer inventory items between locations by creating transfer orders. Alternatively, you can use the item reclassification journal.

> [!NOTE]
> To transfer items, you must set up locations and transfer routes. To learn more about setting up locations, go to [Set up locations](inventory-how-setup-locations.md). You can't use transfer orders for *blank* locations.

## Transfer orders

You can ship an outbound transfer from one location and receive an inbound transfer at the destination. You can:

* Track a quantity in transit.
* Define calendars, routings, and inbound and outbound handling times for date calculation and planning. To learn more about planning, go to [About Planning Functionality](production-about-planning-functionality.md).
* Use different warehouse features for inbound and outbound locations.
* Use transfer orders for direct transfers, with some limitations.

## Item reclassification journals

You can use the **Item Reclassification Journals** page to:

* Direct transfer of items between locations.
* Move items between bins. To learn more about transferring items between bins, go to [Move Items Unplanned in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).
* Change a lot or serial number to a new lot or serial number. To learn more about reclassifying serial and lot numbers, go to [Reclassify serial or lot numbers](inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers).
* Change the expiration date to a new date.
* Reclassify items from a blank location to an actual location.
* Create warehouse entries if you don't manage warehouse activities.

## To transfer items with a transfer order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer orders**, and then choose the related link.
2. On the **Transfer Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > If you filled in the **In-Transit Code**, **Shipping Agent Code**, and **Shipping Agent Service** fields on the **Trans. Route Spec.** page when you set up the transfer route, the corresponding fields on the transfer order are filled in automatically.

    When you fill in the **Shipping Agent Service** field, the receipt date at the transfer-to location is calculated by adding the shipping time of the shipping agent service to the shipment date.

3. There are several ways to fill in the lines:

    |Option  |Description  |
    |---------|---------|
    |Manually     | On the **Lines** FastTab, fill in a line for an item, or use the **Select items** action to choose multiple items.        |
    |Automatically     | * Choose the **Get Bin Content** action to select existing items from a specific bin at the location.<br><br>* Choose the **Get Receipt Lines** to select items that just arrived at the transfer-from location.        |

    You can now ship the items.
4. Choose the **Post** action, choose the **Ship** option, and then choose the **OK** button.

    The items are now in transit between the specified locations according to the transfer route.

    As a warehouse worker at the transfer-from location, proceed to receive the items. The transfer order lines are the same as when shipped and can't be edited.
5. Choose the **Post** action, choose the **Receive** option, and then choose the **OK** button.

### Undo a transfer shipment

If you find a mistake in a quantity on a posted transfer order, as long as the shipment isn't received you can easily correct the quantity. On the **Posted Transfer Shipment** page, the **Undo Shipment** action creates corrective lines, as follows:

* The value in the **Quantity Shipped** field is decreased by the undone quantity.
* The value in the **Qty. to Ship** field is increased by the undone quantity.
* The **Correction** checkbox is selected for the lines.

If the quantity shipped in a warehouse shipment, a corrective line is created in the posted warehouse shipment.

To complete the correction, reopen the transfer order, enter the correct quantity, and then post the order. If you're using a warehouse shipment to ship the order, create and post a new warehouse shipment.

### Post multiple transfer orders in a batch

The following procedure explains how to post transfer orders in a batch.

1. 1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer orders**, and then choose the related link.  
2. On the **Transfer Orders** page, select the orders to post.
3. In the **No.** field, open the context menu and choose **Select More**.
4. Select the checkbox for the lines for each order that you want to post.
5. Choose the **Post** action, and then choose **Post Batch**.
6. On the **Batch Post Transfer Order** page, fill in the fields as necessary.

   > [!TIP]
    > For transfer orders that use an in-transit location, you can choose either **Ship** or **Receive**. Repeat this step if you need to do both. For orders where **Direct Posting** is turned on, both options work in the same way and post the order completely.

7. Select **OK**.
8. To view potential issues, open the **Error Message Register** page.

    > [!NOTE]
    > Posting multiple documents might take some time and block other users. Consider enabling background posting. For more information, see [Use Job Queues to Schedule Tasks](/dynamics365/business-central/admin-job-queues-schedule-tasks).

### Schedule a job queue entry to post multiple documents in a batch

Alternatively, you can use the job queue to schedule posting to happen at a time that's convenient for your organization. For example, it might make sense for your business to run certain routines when most of the data entry is done for the day.

The following procedure shows how to set up the **Batch Post Transfer Orders** report to automatically post direct transfer orders at 4 PM on weekdays. That time is just an example. The steps are the same for other documents.  

1. Search for the **Job Queue Entries** page, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Object Type to Run** field, select **Report**.  
4. In the **Object ID to Run** field, select **5707, Batch Post Transfer Orders**.
5. Select the **Report Request Page** checkbox.
6. On the **Batch Post Transfer Orders** request page, choose the **Ship** option, filter on **Direct Transfer**, and then select **OK**.

   > [!IMPORTANT]
   > It's important to set filters. Otherwise, [!INCLUDE [prod_short](includes/prod_short.md)] will post all documents, even if they aren't ready. Consider setting a filter on the **Status** field for the value **Released**, and a filter on the **Posting Date** field for the value **..today**. To learn more about filters, go to [Sorting, Searching, and Filtering](/dynamics365/business-central/ui-enter-criteria-filters).

7. Select all checkboxes from **Run on Mondays** to **Run on Fridays**.
8. In the **Starting Time** field, enter **4 PM**.
9. Choose the **Set Status to Ready** action.

### Comparison of different settings for transfer orders

You can post transfer orders in different modes, with or without an in-transit location. Turn off the **Direct Transfer** toggle and select the temporary location in the **In Transit Code** field on the **Transfer Order** page. When you post the shipment of a transfer order that uses the in-transit location, the items on the line are no longer available at one of your locations because they're in transit. Direct posting ensures that an in-transit location isn't used and the shipment and receipt process simultaneously. The exact behavior of direct posting might can be different based on the value selected in the **Direct Transfer Posting** field on the **Inventory Setup** page.

The following table describes how the combinations differ.

|Capability|The **Direct Transfer** field is disabled in the **Transfer Order** page|**Direct Transfer** is enabled on the **Transfer Order** page</br>**Direct Transfer Posting** is set to **Direct Transfer** on the **Inventory Setup** page|**Direct Transfer** is enabled in the **Transfer Order** page</br>**Direct Transfer Posting** is set to **Receipt and Shipment** on the **Inventory Setup** page|
|---|---|---|---|
|Use in-transit location|Yes|No|No|
|Can post receipt without shipment.</br>Can use **Undo receipt**.|Yes|No|No|
|Partial posting|Yes|No|Yes|
|Item ledger entries|4:</br>Transfer from From-Location,</br>Transfer to In-Transit,</br>Transfer from In-Transit,</br>Transfer to To-Location.|2:</br>Transfer from From-Location,</br>Transfer to To-Location.|4:</br>Transfer from From-Location,</br>Transfer to *blank*,</br>Transfer from *blank*,</br>Transfer to To-Location.|
|Posted documents|Posted transfer shipment,</br>Posted transfer receipt.|Posted direct transfer|Posted transfer shipment,</br>Posted transfer receipt.|
|Reservation: inbound and outbound|Yes|Yes|Yes|
|Item Charges - assign to posted transfer receipt|Yes|No|Yes|
|Warehouse handling|Full|No|Limited, see below|

Warehouse handling matrix for configuration: **Direct Transfer** is enabled on the **Transfer Order** page and **Direct Transfer Posting** is set to **Direct Transfer** on the **Inventory Setup** page.

|From \ To|To: No warehouse handling|To: Warehouse receipt|To: Inventory Put-away|To: Directed put-away and pick|
|-|-|-|-|-|
|**From: No warehouse handling**|1|Not supported|1, 4|Not supported|
|**From: Warehouse shipment**|1, 2|Not supported|1,2,4|Not supported|
|**From: Inventory put-away**|1, 3|Not supported|1,3,4|Not supported|
|**From: Directed put-away and pick**|2|Not supported|2|Not supported|

The numbers in the cells show the posting options that are supported.

1. Post from transfer order. For some combinations, you might need to fill in the **Qty. to Ship** field.
2. Create and post a warehouse shipment.
3. Create and post an inventory pick.
4. Create and post an inventory put-away. For some combinations you might need to fill in the **Qty. to Ship** field.

Regardless of the method, the shipment and receipt transactions are performed. For example you can create a transfer order from a location that requires inventory-pick to a location that requires inventory put-away. You can create and post the inventory put-away, and both the shipment and receipt transactions are created. You can also post such documents from a transfer order or from an inventory pick.  

For more information about warehouse handling, see [Warehouse management overview](design-details-warehouse-management.md).

## To transfer items with the item reclassification journal

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Reclass. Journals**, and then choose the related link.
2. On the **Item Reclass. Journal** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. In the **Location Code** field, enter the location where the items are currently stored.

    > [!NOTE]  
    > To transfer items that have no location code, leave the **Location Code** field blank.
4. In the **New Location Code** field, enter the location that you want to transfer the items to.
5. Choose the **Post** action.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]


## Related information

[Manage Inventory](inventory-manage-inventory.md)  
[Set Up Locations](inventory-how-setup-locations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
