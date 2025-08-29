---
title: Ship items
description: This article describes how to ship items from your warehouse.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 06/10/2024
ms.custom: bap-template
ms.search.form: 7335, 7337, 7339, 7340, 7341, 7362, 9008
ms.service: dynamics-365-business-central
---

# Ship items with a warehouse shipment

In [!INCLUDE[prod_short](includes/prod_short.md)], you pick and ship items using one of four methods, as described in the following table.

|Method|Outbound Process|Require Pick|Require Shipment|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Post the pick and shipment from the order line|||No dedicated warehouse activity.|  
|B|Post the pick and shipment from an inventory pick document|Turned on||Basic: Order-by-order.|  
|C|Post the pick and shipment from a warehouse shipment document||Turned on|Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post the pick from a warehouse pick document, and post the shipment from a warehouse shipment document|Turned on|Turned on|Advanced|  

To learn more about shipping items, go to [Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md).

This article refers to methods C and D in the table. In both methods, you start by creating a shipment document from a business source document. Then you pick the specified items for the shipment.

When a location requires warehouse shipments, you can ship items based on source documents that were released to the warehouse. Releasing source documents makes the items on them ready to be handled in the warehouse. The following are examples of source documents:

* Sales orders
* Purchase return orders
* Transfer orders
* Service orders

You can create a warehouse shipment in one of two ways:

* In a push fashion, when work is done on an order-by-order basis. Choose the **Create Warehouse Shipment** action in the source document to create a warehouse shipment for the document.
* In a pull fashion, where you use the **Release** action in the source document to release it to the warehouse. A warehouse employee creates a **Warehouse Shipment** for one or many released source documents. The following procedure describes how to create warehouse shipment in a pull fashion.

## To ship items using a warehouse shipment document

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Warehouse Shipments**, then choose the related link.  
2. Choose **New**.  
3. In the **No.** field, choose the number series to use to create an ID for the shipment.  
4. In the **Location Code** field, choose the location you're shipping from. 

    When you retrieve source document lines, some of the information from the location is copied to each line.  
5. If the location requires bins, fill in the **Bin Code** field. Depending on your setup, [!INCLUDE[prod_short](includes/prod_short.md)]] can add the bin code for you. Learn more at [Zone and bin codes](warehouse-how-ship-items.md#zone-and-bin-codes).  
6. You can get the source document in two ways:

    * Choose the **Get Source Documents** action. The **Source Documents - Outbound** page opens. Here you can select one or more source documents released to warehouse that requires shipment.
    * Choose the **Use Filters to Get Src. Docs.** action. The **Filters to Get Source Docs.** page opens. You can select the source document filter and apply it. All released source document lines that fulfill the filter criteria are added on the **Warehouse Shipment** page. Learn more at [How to Use Filters to Get Source Documents](warehouse-how-ship-items.md#how-to-use-filters-to-get-source-documents).

    > [!NOTE]
    > If your location uses cross-docking and bins for each line, you can review the quantity of items placed in the cross-dock bins. [!INCLUDE [prod_short](includes/prod_short.md)] calculates the quantities whenever the fields on the shipment are updated. If they're the items on the shipment you're preparing, you can create a pick for all the items and then complete the shipment. Learn more at [Cross-Dock Items](warehouse-how-to-cross-dock-items.md).

7. Create a warehouse pick. If the location requires picking, you can create pick activities for warehouse shipments in one of two ways:

    * In a push fashion, where you use the **Create Pick** action. Select the lines to pick and specify information about the picks. For example, which bins to take from and place in, and how many units to handle. The bins can be predefined for the warehouse location or resource.
    * In a pull fashion, where you use the **Release** action. On the **Pick Worksheet** page, use the **Get Warehouse Documents** action to get your assigned picks. When the warehouse picks are fully registered, the lines in the **Pick Worksheet** are deleted. Learn more at [Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md).

    > [!TIP]
    > For a location that doesn't require picking, you can print warehouse shipment and use it as a picking list.

8. Specify the quantity to ship.  

    For a location that requires picking, the **Qty. to Ship** field is updated automatically when the pick is registered. Otherwise, the **Qty. to Ship** field is filled with the quantity outstanding for each line when warehouse shipment line is created.

    You can change the quantity, but you can't ship more items than the number in the **Qty. Outstanding** field on the source document line or the **Qty. Picked** field if picking is required.

    To set the value in the **Qty. to Ship** field on all lines to zero, choose the **Delete Qty. to Ship** action. For example, setting the quantities to zero is useful if you're using a barcode scanner to update the shipping quantities. To add the quantity available for shipping, choose the **Autofill Qty. to Ship** action.

9. Post the shipment.

    [!INCLUDE [preview-posting-shipment](includes/preview-posting-shipment.md)]

## How to use filters to get source documents

From a warehouse shipment, you can use the **Filters to Get Source Docs.** page to retrieve the released source document lines that define which items to ship.

1. In the warehouse shipment, choose the **Use Filters to Get Src. Docs.** action. 
2. To set up a new filter, enter a descriptive code in the **Code** field, then choose the **Modify** action.

    The **Source Document Filter Card - Outbound** page opens.

3. Use the filters to define the type of source document lines to retrieve. For example you can select types of source documents, such as sales or transfer orders.
4. Choose **Run**.  

All released source document lines that meet the filter criteria are added on the **Warehouse Shipment** page on which you set the filters.

You can make an unlimited number of filter combinations. Filters are saved on the **Filters to Get Source Docs.** page and are available the next time you need them. You can change the criteria at any time by choosing the **Modify** action.

## Zone and bin codes

If bins are mandatory at the location, [!INCLUDE [prod_short](includes/prod_short.md)] suggests a zone and bin code on the warehouse shipment document.

* For advanced configurations in which a location uses directed put-away and pick, [!INCLUDE [prod_short](includes/prod_short.md)] uses the bin specified in the **Shipment Bin Code** field on the **Location Card**. If a **Shipment Bin Code** isn't specified, the field is blank. If the item and shipment bin don't match, [!INCLUDE [prod_short](includes/prod_short.md)] leaves the shipment bin blank.
* In other cases, [!INCLUDE [prod_short](includes/prod_short.md)] always uses the bin specified in the **Shipment Bin Code** field on the **Location Card** first. If a shipment bin code isn't specified, [!INCLUDE [prod_short](includes/prod_short.md)] uses the bin code from the source document.

## Handling Assemble-to-Order Items in Warehouse Shipments

In assemble-to-order scenarios, use the **Qty. to Ship** field on warehouse shipment lines to record how many units are assembled. The quantity is posted as assembly output when you post the warehouse shipment. For other warehouse shipment lines, the value in the **Qty. to Ship** field is zero.

When workers finish assembling some or all of the assemble-to-order quantity, record the quantity on the **Qty. to Ship** field on the warehouse shipment line. Then choose the **Post Shipment** action. The assembly output is posted, including the component consumption. A sales shipment for the quantity is posted for the sales order.

From the assembly order, you can choose **Asm.-to-Order Whse. Shpt. Line** to access the warehouse shipment line.

After you post the warehouse shipment, various fields on the sales order line are updated to show progress in the warehouse. The following fields are also updated to show how many assemble-to-order quantities remain to be assembled and shipped:

* **ATO Whse. Outstanding Qty.**
* **ATO Whse. Outstd. Qty. (Base)**

> [!NOTE]
> In combination scenarios where a part of the quantity must be assembled and another must be shipped from inventory, two warehouse shipment lines are created. One is for the assemble-to-order quantity, and one is for the inventory quantity.
>
> The assemble-to-order quantity is handled as described in this article. The inventory quantity is handled as a regular warehouse shipment line. To learn more about combination scenarios, go to [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## Related information

[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
