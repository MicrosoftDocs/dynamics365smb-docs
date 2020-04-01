---
    title: How to Ship Items | Microsoft Docs
    description: Depending on your warehouse configuration, you can either record shipment on the related outbound business document, such as a sales order,  directly, or you can use warehouse shipment documents that respect a workflow and integrate to various warehouse activities.
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
# Ship Items
When you ship items from a warehouse that is not set up for warehouse shipment processing, you simply record the shipment on the related business document, such as a sales order, service order, purchase return order, or outbound transfer order.

When you ship items from a warehouse that is set up warehouse shipment processing, you can ship items only on the basis of source documents that other company units have released to the warehouse for action.

> [!NOTE]
> If your warehouse uses cross-docking and bins, for each line, you can view the quantity of items that have been placed in the cross-dock bins. The application calculates these quantities automatically whenever the fields on the shipment are updated. If they are the items that apply to the shipment you are preparing, you can create a pick for all the lines and then complete the shipment. For more information, see [Cross-Dock Items](warehouse-how-to-cross-dock-items.md).

## To ship items with a sales order
The following describes how to receive items with a purchase order. The steps are similar for purchase return orders, service orders, and outbound transfer orders.  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Open an existing sales order, or create a new one. For more information, see [Sell Products](sales-how-sell-products.md).
3. In the **Qty. to Ship** field, enter the received quantity.

    The value in the **Qty. Shipped** field is updated. If this is a partial shipment, then the value is lower than the value in the **Quantity** field.
4. Choose the **Post** action.

## To ship items with a warehouse shipment
First you create a shipment document from a business source document. Then you pick the specified items for the shipment.

### To create a warehouse shipment
Typically, employee responsible for shipping creates a warehouse shipment.
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments**, and then choose the related link.  
2.  Choose the **New** action.  

    Fill in the fields on **General** FastTab. When you retrieve source document lines, some of the information is copied to each line.  

    For warehouse configuration with directed put-away and pick, if the location has a default zone and bin for shipments, the **Zone Code** and **Bin Code** fields are filled in automatically, but you can change them as appropriate.  

    > [!NOTE]  
    >  If you wish to ship items with warehouse class codes other than the class code of the bin in the **Bin Code** field on the document header, you must delete the contents of the **Bin Code** field on the header before you retrieve source document lines for the items.  
3.  Choose the **Get Source Documents** action. The **Source Documents** page opens.

    From a new or an open warehouse shipment, you can use the **Filters to Get Source Docs.** page to retrieve the released source document lines that define which items to ship.

    1. Choose the **Use Filters to Get Src. Docs.** action.  
    2. To set up a new filter, enter a descriptive code in the **Code** field, and then choose the **Modify** action.  
    3. Define the type of source document lines that you want to retrieve by filling in the relevant filter fields.  
    4. Choose the **Run** action.  

    All released source document lines that fulfill the filter criteria are now inserted in **Warehouse Shipment** page from which you activated the filter function.  

    The filter combinations that you define are saved on the **Filters to Get Source Docs.** page until the next time you need it. You can make an unlimited number of filter combinations. You can change the criteria at any time by choosing the **Modify** action.

4.  Select the source documents for which you want to ship items, and then choose the **OK** button.  

The lines of the source documents appear on the **Warehouse Shipment** page. The **Qty. to Ship** field is filled with the quantity outstanding for each line, but you can change the quantity as necessary. If you deleted the contents of the **Bin Code** field on the **General** FastTab before getting the lines, you must fill in an appropriate bin code on each shipment line.  

> [!NOTE]  
>  You cannot ship more items than the number in the **Qty. Outstanding** field on the source document line. To ship more items, retrieve another source document that contains a line for the item by using the filter function to get source documents with the item.  

When you have the lines you want to ship, you can start the process that sends the lines to warehouse employees to pick.

### To pick and ship
Typically, a warehouse worker responsible for picking creates a pick document, or opens an already created pick document.
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipments**, and then choose the related link.
2. Select the warehouse shipment that you want to pick for, and then choose the **Create Pick** action.
3. Fill in the fields in the request page, and then choose the **OK** button. The specified warehouse pick document is created.

    Alternatively, open an existing warehouse pick.
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link. Select the warehouse pick that you want to work on.

    If the warehouse is set up to use bins, then the pick lines have been converted to Take and Place action lines.

    You can sort the lines, assign an employee to the pick, set a break-bulk filter, if you are using directed put-away and pick, and print the pick instructions.

5. Perform the actual picking of items and place them in the specified shipping bin, or in the shipping area, if you do not have bins.
6. Choose the **Register Pick** action.

    The **Qty. to Ship** field and the **Document Status** field on the header of the shipment document are updated. The items you have picked are no longer available for picking for other shipments or for internal operations.
7. Print your shipping documents, prepare the shipment packages, and then post the shipment.

For more information about picking for warehouse shipments, see [Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md).

You can also use the pick worksheet to make several pick instructions into one instruction (for several shipments) and thereby improve the efficiency of picking in the warehouse. For more information, see [Plan Pick in Worksheets](warehouse-how-to-plan-picks-in-worksheets.md).

> [!NOTE]
> If you are waiting for particular items to arrive at the warehouse, and you use cross-dock functionality, then [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates on each shipment or pick worksheet line the quantity of the item that is in the cross-dock bin. It updates this field each time you leave and open the shipment document or worksheet. For more information, see [Cross-Dock Items](warehouse-how-to-cross-dock-items.md).

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
