---
    title: How to Cross-Dock Items | Microsoft Docs
    description: Cross-docking functionality is available to you if you have set up your location to require warehouse receive and put-away processing.
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
# Cross-Dock Items
Cross-docking functionality is available to you if you have set up your location to require warehouse receive and put-away processing.  

When you cross-dock items, you process items in receiving and shipping without ever placing them in storage, thereby expediting the item through the put-away and pick processes and limiting the physical handling of items. You can cross-dock items for both shipments and for production orders. When you prepare a shipment or pick items for production and you are using bins, the item is automatically picked from a cross-dock bin before any other bin. You must look in the cross-dock area to see if the items you need are available there before you get the items in their usual storage area.  

If you have calculated cross-dock quantities, put-away lines to the cross-dock bin for cross-dock calculations are created when you post the receipt. Other put-away lines are created as usual.  

If you want to post the cross-dock items right away to make them available for picking, you must also register a put-away for the other items originating from the receipt line, namely those that need to be stored. If only some items on a receipt line are being cross-docked, you must therefore make an effort to put away the remaining items as quickly as possible. Alternatively, your warehouse policy could be to encourage cross-docking of entire receipt lines whenever possible.  

In the put-away instruction, you can to your advantage delete both Take and Place instruction lines for each receipt line that concern receipts that are to be fully put away in storage. These lines can later be created as put-away lines from the put-away worksheet or the posted receipt. When they are deleted, you can then put away and register the lines that concern cross-dock items.  

If you have selected the **Use Put-away Worksheet** field on the location card and have posted your receipt with calculated cross-docks, all the receipt lines become available in the worksheet. The cross-dock information is lost and cannot be recreated. Therefore, if you wish to use cross-dock functionality, you should relay lines to the put-away worksheet by deleting put-away instructions rather than using the automatic relay function provided in the **Use Put-away Worksheet** field.  

If you post the warehouse receipt and you do not have the **Use Put-away Worksheet** field selected, the items to be cross-docked appear as separate lines on the put-away instruction. The **Cross-Dock Information** field on each put-away line shows whether the line contains cross-dock items, items from the same receipt that all need to be stored, or items that need to be stored originating from a receipt line where some of the items are to be cross-docked. With this field, employees can easily see why the full receipt quantity is not being placed in storage.  

The application does not keep separate records about items that have been cross-docked, but registers them as ordinary put-away instructions.  

## To set up the warehouse for cross-docking  
1.  Set up at least one cross-dock bin, if you are using bins. Set up a cross-dock zone, if you are using directed put-away and pick.  

    A cross-dock bin has the **Cross-Dock Bin** field selected and must have both **Receive** and **Pick** bin types selected. For more information, see [Create Bins](warehouse-how-to-create-individual-bins.md) and [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).  

    If you are using zones, create a zone for your cross-dock bins, and select the **Cross-Dock Bin Zone** field. For more information, see [Set Up Locations to Use Bins](warehouse-how-to-set-up-locations-to-use-bins.md).  

2.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Location**, and then choose the related link.  
3.  On the **Location** page, select the location that you want to set up the warehouse for cross-docking, and then choose the **Edit** action.  
4.  On the **Warehouse** FastTab, select the **Use Cross-Docking** check box and fill in the **Cross-Dock Due Date Calc.** field with the time to search for cross-dock opportunities.

    The **Use Cross-Docking** option is only available if the **Require Receive**, **Require Shipment**, **Require Pick**, and **Require Put-away** fields are selected.  

5.  If you are using bins, on the **Bins** FastTab, fill in the **Cross-Dock Bin Code** field with the code of the bin you would like to use as the default cross-dock bin.  
6.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Stockkeeping Unit**, and select the related link.  
7.  For each item or stockkeeping unit that you want to be able to cross-dock, select the item, and then choose the **Edit** action.
8. On the **Stockkeeping Unit Card** page, select the **Use Cross-Docking** check box.  

> [!NOTE]  
>  Cross-docking is only possible if your location is set up to require warehouse receive and put-away processing.  

## To cross-dock items without viewing the opportunities  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, and then choose the related link.  
2.  Create a warehouse receipts for an item that has arrived and can perhaps be cross-docked. For more information, see [Receive Items](warehouse-how-receive-items.md).  
3.  Fill in the **Qty. to Receive** field, and then choose the **Calculate Cross-Dock** action.  

    Outbound source documents requesting the items that are scheduled to leave the warehouse within the date formula time period are identified.  [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates quantities so that you can cross-dock as much as possible and avoid having to put items away, without piling up too many items in the cross-dock area. The value in the **Qty. to Cross-Dock** field is thus the sum of all the outbound lines requesting the item within the look-ahead period minus the quantity of the items that have already been placed in the cross-dock area, or it is the value in the **Qty. to Receive** field on the receipt line, whichever is smaller. You cannot cross-dock more than you have received.  

4.  If you want to cross-dock the quantity as suggested, post the receipt. You can also decide to change the quantity to cross-dock to a higher or lower value and then post the receipt.  

    The amounts to be cross-docked now appear as lines in the put-away instruction, assuming the **Use Put-away Worksheet** field is cleared. The quantities not cross-docked also become lines in the put-away instruction.  

    If you have bins, the cross-docked items have been assigned to the default cross-dock bin defined on the location card.  

5.  Delete the **Take** and **Place** lines for items that are not going to be cross-docked at all.  
6.  Print the put-away instruction for the remaining lines, and place the quantities of the receipt that need to be stored in the appropriate bins or in the appropriate area of the warehouse. Place the cross-dock items in the area or bin designated for them by warehouse policy. Sometimes, warehouse policy might require that you to just leave them in the receiving area.  
7.  To register the cross-docked items as being put-away and available for picking, choose the **Register** action.  

## To cross-dock items after viewing the opportunities  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, and then choose the related link.  
2.  Create a warehouse receipts for an item that has arrived and can perhaps be cross-docked. For more information, see [Receive Items](warehouse-how-receive-items.md).  

    You want to view the source document lines that are requesting the item before you post the receipt.  
3.  Choose the **Calculate Cross-Dock** action.  

    On the **Cross-Dock Opportunities** page you can see the most important details about the lines requesting the item, such as type of document, quantity requested, and due date. This information might help you to decide how much to cross-dock, where to place the items in the cross-dock area, or how to group them.  

4.  Choose **Autofill Qty. to Cross-Dock** action to see how the quantities on the receipt lines are calculated. When you change the number of items in the **Qty. to Cross-Dock** field on each line, the calculation is updated as you make changes. This does not mean that the particular shipment or production order will actually receive the items being suggested for cross-docking, because these manipulations are for testing purposes only. The process can be informative, however, if more than one unit of measure is involved.  
5.  If you want to reserve a quantity of the item for a particular order line, place your cursor on that line, and then choose the **Reserve** action. On the **Reservation** page, you can now reserve any available quantity of the item for this specific order. This reservation is like any other reservation and does not have higher priority because it was created in connection with cross-docking. For more information, see [Reserve Items](inventory-how-to-reserve-items.md).   
6.  When you are finished recalculating or reserving, choose the **OK** button to bring the calculation as you have revised it into the **Qty. to Cross-Dock** field on the receipt line, or choose the **Cancel** button if you want to return to the warehouse receipt, where you can calculate the cross-dock again if you wish.  
7.  Now post the receipt, and you can continue in the put-away instruction as described in steps 3 through 7 in the “To cross-dock items without viewing the opportunities” section.  

> [!NOTE]  
>  In the warehouse put-away, you can continue to change the quantities that are being put away in storage or cross-docked, as necessary. For example, you might decide to cross-dock an extra quantity to expedite the cross-dock registration.  

## To view cross-docked items in a shipment or pick worksheet  
If you are using bins, you can see, each time you open a shipment or the pick worksheet, an updated calculation of the quantity of each item in the cross-dock bins. This is valuable information if you are waiting for an item to come in. When you see that the item is available in the cross-dock bin, you can then quickly create a pick for all the items on the shipment. In the pick worksheet, you can modify the lines as appropriate and then create a pick.  

You have to look for items in the cross-dock area first when you pick items for shipment. If you have noted during the receipt process the source documents that were the basis for cross-docking, you have a better idea of whether the item can be found in the cross-dock area or not.  

When a production order has been released, the lines are available in the pick worksheet, and you can see in the **Qty. on Cross-Dock Bin** field whether the items you are waiting for have arrived and been placed in the cross-dock bins. When you create a pick instruction, application suggests that you first pick the cross-docked items and will only later search for the item in storage bins.  

If you are not using bins, you must remember to check the cross-dock area from time to time, or rely on notifications from receipts that items for production have arrived.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
