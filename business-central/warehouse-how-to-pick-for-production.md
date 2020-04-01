---
    title: How to Pick for Production in Basic Warehouse Configurations | Microsoft Docs
    description: When your warehouse location requires pick processing but does not require shipment processing, use the **Inventory Pick** page to organize and record the picking of components.
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
# Pick for Production or Assembly in Basic Warehouse Configurations
How you put away your pick components for production or assembly orders depends on how your warehouse is set up as a location. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

In basic warehouse configurations where the location requires pick processing but not shipment processing, you use the **Inventory Pick** page to organize and record the picking of components.  

In basic warehouse configurations, you must pick for assembly orders with the **Inventory Movement** page. For more information, see [Handling Assemble-to-Order Item with Inventory Picks](warehouse-how-to-pick-for-production.md#handling-assemble-to-order-items-with-inventory-picks).  

In advanced warehouse configurations where locations require both picks and shipments, you use the **Warehouse Pick** page to bring components to production or assembly orders. For more information, see [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

> [!NOTE]  
>  The following important differences exist between inventory picks and inventory movements:  
>   
>  -   When you register an inventory pick for an internal operation, such as production, the consumption of the picked components is posted at the same time. When you register an inventory movement for an internal operation, you only record the physical movement of the required components to a bin in the operation area without posting the consumption.  
> -   When you use inventory picks, the **Bin Code** field on a production order component line defines the *take* bin from where components are decreased when posting consumption. When you use inventory movements, the **Bin Code** field on production order component lines defines the *place* bin in the operation area where the warehouse worker must place the components.  

A system precondition for picking, or moving, components for source documents is that an outbound warehouse request exists to notify the warehouse area of the component need. The outbound warehouse request is created whenever the production order status is changed to Released or when a released production order is created.  

## To pick components in basic warehouse configurations
In basic warehouse configurations where the location is set up to use picking only, you can pick components for production activities with the **Inventory Pick** page. For more information, see [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.  
2.  To access the production order components, choose the **Get Source Documents** action, and then select the released production order.  
3.  Perform the pick, and then record the actual picking information in the **Qty. Picked** field.  
4.  When the lines are ready for posting, choose the **Post** action. The posting creates the necessary warehouse entries and posts the consumption of the items.  

You can also create an **Inventory Pick** directly from the released production order. Choose the **Create Inventory Put-away/Pick** action, select the **Create Invt. Pick** check box, and then choose the **OK** button.

Alternatively, you can use the **Inventory Movement** page to move items between bins ad hoc, meaning without reference to a source document.
For more information, see [Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

### Handling Assemble-to-Order Items with Inventory Picks
The **Inventory Pick** page is also used to pick and ship for sales where items must be assembled before they can be shipped. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).

Items to be shipped are not physically present in a bin until they are assembled and posted as output to a bin in the assembly area. This means that picking assemble-to-order items for shipment follows a special flow. From a bin, warehouse workers take the assembly items to the shipping dock and then post the inventory pick. The posted inventory pick then posts the assembly output, the component consumption, and the sales shipment.

You can set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to automatically create an inventory movement when the inventory pick for the assembly item is created. To enable this, you must select the **Create Movements Automatically** field on the **Assembly Setup** page. For more information, see [Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

Inventory pick lines for sales items are created in different ways depending on whether none, some, or all of the sales line quantities are assembled to order.

In regular sales where you use inventory picks to post shipment of inventory quantities, one inventory pick line, or several if the item is placed in different bins, is created for each sales order line. This pick line is based on the quantity in the **Qty. to Ship** field.

In assemble-to-order sales where the full quantity on the sales order line is assembled to order, one inventory pick line is created for that quantity. This means that the value in the Quantity to Assemble field is the same as the value in the **Qty. to Ship** field. The **Assemble to Order** field is selected on the line.

If an assembly output flow is set up for the location, then the value in the **Asm.-to-Order Shpt. Bin Code** field or the value in the **From-Assembly Bin Code** field, in that order, is inserted in the **Bin Code** field on the inventory pick line.

If no bin code is specified on the sales order line, and no assembly output flow is set up for the location, then the **Bin Code** field on the inventory pick line is empty. The warehouse worker must open the **Bin Contents** page and select the bin where the assembly items are assembled.

In combination scenarios, where a part of the quantity must first be assembled and another must be picked from inventory, a minimum of two inventory pick lines are created. One pick line is for the assemble-to-order quantity. The other pick line depends on which bins can fulfill the remaining quantity from inventory. Bin codes on the two lines are filled in different ways as described for the two different sales types respectively. For more information, see the “Combination Scenarios” section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## Filling the Consumption Bin
This flow chart shows how the **Bin Code** field on production order component lines is filled according to your location setup.

![Bin flow chart](media/binflow.png "BinFlow")

## See Also
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
