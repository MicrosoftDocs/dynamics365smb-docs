---
title: Ship Items
description: This article describes how to ship items from your warehouse depending on your warehouse configuration for shipment processing.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 7335, 7337, 7339, 7340, 7341, 7362, 9008
ms.date: 09/02/2022
ms.author: edupont

---
# Ship Items

When you ship items from a warehouse that's not set up for warehouse shipment processing, you simply record the shipment on the related business document, such as a sales order, service order, purchase return order, or outbound transfer order.

When you ship items from a warehouse that's set up for warehouse shipment processing, you can only ship items based on source documents that other company units have released to the warehouse for action.

> [!NOTE]
> If your warehouse uses cross-docking and bins for each line, you can view the quantity of items placed in the cross-dock bins. The application calculates these quantities automatically whenever the fields on the shipment are updated. If they are the items that apply to the shipment you're preparing, you can create a pick for all the lines and then complete the shipment. Learn more at [Cross-Dock Items](warehouse-how-to-cross-dock-items.md).

## Ship items with a sales order

The following instructions describe how to ship items from a sales order. The steps are similar for purchase return orders, service orders, and outbound transfer orders.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, then choose the related link.
2. Open an existing sales order or create a new one. Learn more at [Sell Products](sales-how-sell-products.md).
3. In the **Qty. to Ship** field, enter the shipped quantity.

    The value in the **Qty. Shipped** field is updated. If this is a partial shipment, then the value is lower than the value in the **Quantity** field. Learn more at [Process Partial Shipments](sales-how-send-partial-shipments.md).
4. Choose the **Post** action.

> [!NOTE]
> If your organization does not use sales orders, then, when you post the sales invoice, [!INCLUDE [prod_short](includes/prod_short.md)] assumes you've shipped the full quantity. If this conflicts with how your organization works, we recommend you use sales orders and register shipments as explained in this article.

## Ship items with a warehouse shipment

First you create a shipment document from a business source document. Then you pick the specified items for the shipment.

### Create a warehouse shipment

Typically, the employee responsible for shipping creates a warehouse shipment. The following procedure describes how to create the shipment manually in the default version of [!INCLUDE[prod_short](includes/prod_short.md)]. However, your organization may have automated part of the process, such as with the use of hand-held or mounted scanners supported by external providers.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments**, then choose the related link.  
2. Choose **New**.  

    Fill in the fields on **General** FastTab. When you retrieve source document lines, some of the information is copied to each line.  

    For a warehouse configured with directed put-away and pick, if the location has a default zone and bin for shipments, the **Zone Code** and **Bin Code** fields are filled in automatically, but you can change them as appropriate.  

    > [!NOTE]  
    > If you wish to ship items with warehouse class codes other than the class code of the bin in the **Bin Code** field on the document header, you must delete the contents of the **Bin Code** field on the header before you retrieve source document lines for the items.  
3. Choose the **Get Source Documents** action. The **Source Documents** page opens.

    From a new or open warehouse shipment, you can use the **Filters to Get Source Docs.** page to retrieve the released source document lines that define which items to ship.

    1. Choose the **Use Filters to Get Src. Docs.** action.  
    2. To set up a new filter, enter a descriptive code in the **Code** field, then choose the **Modify** action.  
    3. Define the type of source document lines you want to retrieve by filling in the relevant filter fields.  
    4. Choose the **Run** action.  

    All released source document lines that fulfill the filter criteria are now inserted in the **Warehouse Shipment** page from which you activated the filter function.  

    The filter combinations you define are saved on the **Filters to Get Source Docs.** page until the next time you need it. You can make an unlimited number of filter combinations. You can change the criteria at any time by choosing the **Modify** action.

4. Select the source documents for which you want to ship items, then choose **OK**.  

The lines of the source documents appear on the **Warehouse Shipment** page. The **Qty. to Ship** field is filled with the quantity outstanding for each line, but you can change the quantity as necessary. If you deleted the contents of the **Bin Code** field on the **General** FastTab before getting the lines, you must fill in an appropriate bin code on each shipment line.  

> [!NOTE]  
> You cannot ship more items than the number in the **Qty. Outstanding** field on the source document line. To ship more items, use the filter function to retrieve another source document that contains a line for the same item.  

When you have the lines you want to ship, you can start the process that sends the lines to warehouse employees to pick.

### Pick and ship

Typically, a warehouse worker responsible for picking creates a pick document, or opens an already created pick document.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments**, then choose the related link.
2. Select the warehouse shipment you want to pick for, then choose the **Create Pick** action.
3. Fill in the fields in the request page, then choose **OK**. The specified warehouse pick document is created.

    Alternatively, open an existing warehouse pick document.
4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link. Select the warehouse pick you want to work on.

    If the warehouse is set up to use bins, then the pick lines have been converted to Take and Place action lines.

    If you're using directed put-away and pick, you can sort the lines, assign an employee to the pick, set a break-bulk filter, and print the pick instructions.

5. Perform the actual picking of items and place them in the specified shipping bin, or shipping area if you do not have bins.
6. Choose the **Register Pick** action.

    The **Qty. to Ship** field and the **Document Status** field on the header of the shipment document are updated. The items you have picked are no longer available for other orders to pick or for internal operations.
7. Print your shipping documents, prepare the shipment packages, and then post the shipment.

To learn more about picking for warehouse shipments, see [Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md).

You can also use the pick worksheet to make several pick instructions into one instruction (for several shipments) and thereby improve the efficiency of picking in the warehouse. Learn more at [Plan Pick in Worksheets](warehouse-how-to-plan-picks-in-worksheets.md).

> [!NOTE]
> If you're waiting for the arrival of particular items at the warehouse and you use cross-dock functionality, then [!INCLUDE[prod_short](includes/prod_short.md)] calculates the quantity of the item in the cross-dock bin on each shipment or pick worksheet line. It updates this field each time you leave and open the shipment document or worksheet. Learn more at [Cross-Dock Items](warehouse-how-to-cross-dock-items.md).

## See related training at [Microsoft Learn](/learn/modules/ship-invoice-items-dynamics-365-business-central/).

## See also

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
