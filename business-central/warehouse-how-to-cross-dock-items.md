---
title: Cross-Dock Items
description: Learn how to receive and ship items without putting them in storage.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 10/09/2023
ms.custom: bap-template
ms.search.form: 15, 5703, 7302, 7332, 5768
ms.service: dynamics-365-business-central
---
# Cross-Dock Items

Cross-dock items are items you receive and ship without putting them away. The put-away and pick processes require limited handling of items. You can cross-dock items for shipments and for production orders.

## Cross-dock bins and zones

If you're using bins, set up at least one cross-dock bin, and then specify the bin in the **Cross-Dock Bin Code** field on your locations. If you're using directed put-away and picks, set up a cross-dock zone.

When you prepare a shipment or pick items for production and you're using bins, the item is automatically picked from a cross-dock bin before any other bin. You must look in the cross-dock area to see whether the items you need are available there before you get the items in their usual storage area.  

If you've calculated cross-dock quantities, put-away lines to the cross-dock bin for cross-dock calculations are created when you post the receipt. Other put-away lines are created as usual.  

## Cross-dock select lines for a receipt

If you want to post the cross-dock items right away to make them available for picking, you must also register a put-away for the other items originating from the receipt line, namely those that need to be stored. If only some items on a receipt line are being cross-docked, you must therefore make an effort to put away the remaining items as quickly as possible. Alternatively, your warehouse policy could be to encourage cross-docking of entire receipt lines whenever possible.

In the put-away instruction, delete the Take and Place instruction lines for each receipt line for the items to put away. You can recreate the instruction lines later as put-away lines from the put-away worksheet or the posted receipt. After you delete the instruction lines you can put away and register the lines for cross-dock items.  

## About the Put-away Worksheet page

If you turn on the **Use Put-away Worksheet** toggle on the **Location Card** page, and post your receipt with calculated cross-docks, all receipt lines become available in the worksheet. The cross-dock information is lost and can't be recreated. Therefore, to use cross-dock functionality, you should relay lines to the put-away worksheet by deleting put-away instructions rather than using the automatic relay function provided in the **Use Put-away Worksheet** field.  

If you post the warehouse receipt and the **Use Put-away Worksheet** toggle is turned off, the cross-dock items become separate lines on the put-away instructions. The **Cross-Dock Information** field on each put-away line shows whether the line contains the following:

* Cross-dock items.
* All of the items from a receipt must be stored.
* Some items from a receipt must be stored, and some are to be cross-docked.

[!INCLUDE [prod_short](includes/prod_short.md)] doesn't keep separate records for cross-docked items. It registers them as ordinary put-away instructions.  

## To set up the warehouse for cross-docking  

1. If you're using bins, set up at least one cross-dock bin. If you're using directed put-away and picks, set up a cross-dock zone.  

    A cross-dock bin has the **Cross-Dock Bin** field selected. To learn more about bins, go to [Create Bins](warehouse-how-to-create-individual-bins.md).  

    If you are using zones, create a zone for your cross-dock bins, and select the **Cross-Dock Bin Zone** field. If you are using directed put-away and picks, select bin type with **Pick** selected, for example you can use *PICK* or *PUTPICK*. To learn more about zones and bin types, go to [Set Up Locations to Use Bins](warehouse-how-to-set-up-locations-to-use-bins.md) and [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).  

2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Location**, and then choose the related link.  
3. On the **Location** page, select the location that you want to set up the warehouse for cross-docking, and then choose the **Edit** action.  
4. On the **Warehouse** FastTab, turn on the **Use Cross-Docking** toggle and fill in the **Cross-Dock Due Date Calc.** field with the time to search for cross-dock opportunities.

    The **Use Cross-Docking** option is only available if the **Require Receipt**, **Require Shipment**, **Require Pick**, and **Require Put-away** fields are selected.  

5. If you're using bins, on the **Bins** FastTab, fill in the **Cross-Dock Bin Code** field with the code of the bin you would like to use as the default cross-dock bin.  
6. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Stockkeeping Unit**, and select the related link.  
7. For each item or stockkeeping unit that you want to be able to cross-dock, select the item, and then choose the **Edit** action.
8. On the **Stockkeeping Unit Card** page, select the **Use Cross-Docking** check box.  

> [!NOTE]  
>  Cross-docking is only possible if your location is set up to require warehouse receive and put-away processing.  

## To cross-dock items without viewing the opportunities  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, and then choose the related link.  
2. Create a warehouse receipt for an item that's arrived and can be cross-docked. To learn more about receiving, go to [Receive Items](warehouse-how-receive-items.md).  
3. Fill in the **Qty. to Receive** field, and then choose the **Calculate Cross-Dock** action.  

    Outbound source documents requesting the items that are scheduled to leave the warehouse within the date formula time period are identified. [!INCLUDE[prod_short](includes/prod_short.md)] calculates quantities so that you can cross-dock as much as possible and avoid having to put items away, without piling up too many items in the cross-dock area. The value in the **Qty. to Cross-Dock** field is the sum of all the outbound lines for the item within the look-ahead period minus the quantity that is already placed in the cross-dock area, or it is the value in the **Qty. to Receive** field on the receipt line, whichever is smaller. You can't cross-dock more than you have received.  

4. To cross-dock the quantity as suggested, post the receipt. You can also decide to change the quantity to cross-dock to a higher or lower value and then post the receipt.  

    The amounts to be cross-docked now appear as lines in the put-away instruction, assuming the **Use Put-away Worksheet** field is cleared. The quantities not cross-docked also become lines in the put-away instruction.  

    If you have bins, the cross-docked items have been assigned to the default cross-dock bin defined on the location card.  

5. Delete the **Take** and **Place** lines for items that you won't cross-dock.  
6. Print the put-away instruction for the remaining lines, and place the quantities of the receipt that need to be stored in the appropriate bins or in the appropriate area of the warehouse. Place the cross-dock items in the area or bin designated for them by warehouse policy. Sometimes, warehouse policy might require that you to just leave them in the receiving area.  
7. To register the cross-docked items as being put-away and available for picking, choose the **Register** action.  

## To cross-dock items after viewing the opportunities  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, and then choose the related link.  
2. Create a warehouse receipt for an item that has arrived and can be cross-docked.  

    You want to view the source document lines that are requesting the item before you post the receipt.  
3. Choose the **Calculate Cross-Dock** action.  

   On the **Cross-Dock Opportunities** page you can see the most important details about the lines requesting the item, such as type of document, quantity requested, and due date. This information might help you to decide how much to cross-dock, where to place the items in the cross-dock area, or how to group them.  

4. Choose **Autofill Qty. to Cross-Dock** action to show how the quantities on the receipt lines are calculated. When you change the number of items in the **Qty. to Cross-Dock** field on each line, the calculation updates. The update doesn't mean that the shipment or production order will actually receive the items being suggested for cross-docking. It's for testing purposes only. The process can be informative, however, if more than one unit of measure is involved.  
5. To reserve a quantity of the item for an order line, choose the line, and then choose the **Reserve** action. On the **Reservation** page, reserve available quantity of the item. The reservation is like any other reservation and doesn't have higher priority because it was created in connection with cross-docking. To learn more about reservations, go to [Reserve Items](inventory-how-to-reserve-items.md).   
6. When you're finished recalculating or reserving, choose the **OK** button to bring the calculation to the **Qty. to Cross-Dock** field on the receipt line, or choose the **Cancel** button to return to the warehouse receipt and calculate the cross-dock again.  
7. Post the receipt. You can continue in the put-away instruction as described in steps 3 through 7 in [To cross-dock items without viewing the opportunities](#to-cross-dock-items-without-viewing-the-opportunities).  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

    > [!NOTE]  
    > In the warehouse put-away, you can continue to change the quantities that are being put away in storage or cross-docked, as necessary. For example, you might decide to cross-dock an extra quantity to expedite the cross-dock registration.  

## To view cross-docked items in a shipment or pick worksheet  

If you're using bins, when you open a shipment or the pick worksheet the quantity of each item in the cross-dock bins updates. When the item is available in the cross-dock bin, you can create a pick for the items on the shipment. In the pick worksheet, you can edit the lines as needed.  

When a production order is released, the lines are available in the pick worksheet and the **Qty. on Cross-Dock Bin** field shows whether the items have arrived and are in the cross-dock bins. When you create a pick instruction, [!INCLUDE [prod_short](includes/prod_short.md)] suggests that you pick the cross-docked items first. Items in storage bins are suggested afterward.  

If you aren't using bins, remember to check the cross-dock area from time to time, or rely on notifications from receipts that items for production have arrived.  

## Related information  

[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
