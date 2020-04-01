---
    title: How to Set Up Basic Warehouses with Operations Areas | Microsoft Docs
    description: If internal operation areas such as production or assembly exist in basic warehouse configurations where locations use the **Bin Mandatory** setup field and possibly the **Require Pick** and **Require Put-away** setup fields, then you use three basic warehouse documents to record your warehouse activities for internal operation areas.
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
# Set Up Basic Warehouses with Operations Areas
If internal operation areas such as production or assembly exist in basic warehouse configurations where locations use the **Bin Mandatory** setup field and possibly the **Require Pick** and **Require Put-away** setup fields, then you can use the following basic warehouse documents to record your warehouse activities for internal operation areas:  

- **Inventory Movement** page.  
- **Inventory Pick** page.  
- **Inventory Put-away** page.

> [!NOTE]
> Even though the settings are called **Require Pick** and **Require Put-away**, you can still post receipts and shipments directly from the source business documents at locations where you select these check boxes.  

To use these pages with internal operations, such as to pick and move components to production, you must make some or all the following setup steps depending on how much control you need:  

- Enable the inventory pick, move, and put-away documents.  
- Define default bin structures for components and end items flowing to and from operation resources.  
- Make to- and from- bins that are dedicated to specific operation resources to prevent the items from being picked for outbound documents.

Bin codes that are set up on location cards define a default warehouse flow for certain activities, such as components in an assembly department. Additional functionality exists to make sure that when items are placed in a certain bin, they cannot be moved or picked to other activities. For more information, see [To create dedicated component bins](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md#to-create-dedicated-component-bins).

The following procedures are based on setting up basic warehouse activities around a production area. The steps are similar for other operation areas, such as assembly, service management, and jobs.  

> [!NOTE]  
>  In the following procedure, the **Bin Mandatory** setup field on location cards is selected as a precondition because that is considered the foundation for any level of warehouse management.  

## To enable inventory documents for internal operation activities  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the location card you want to set up.  
3.  On the **Warehouse** FastTab, select the **Require Put-away** check box to indicate that, when an inbound or internal source document with a bin code is released, an inventory put-away or an inventory movement document can be created.  
4.  Select the **Require Pick** check box to indicate that when an outbound or internal source document with a bin code is created, an inventory pick or an inventory movement document must be created.  

## To define a default bin structure in the production area  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.  
3.  On the **Bins** FastTab, in the **Open Shop Floor Bin Code** field, enter the code of the bin in the production area with plenty of components that the machine operator can consume from without requesting a warehouse activity to bring them to the bin. Items that are placed in this bin are typically set up for automatic posting, or flushing. This means that the **Flushing Method** field contains **Forward** or **Backward**.  
4. In the **To-Production Bin Code** field, enter the code of the bin in the production area where components that are picked for production at this location are placed by default before they can be consumed. Items that are placed in this bin are typically set up for manual consumption posting. This means that the **Flushing Method** field contains **Manual** or **Pick + Forward** or **Pick + Backward** for warehouse picks and inventory movements.  

    > [!NOTE]  
    >  When you use inventory picks, the **Bin Code** field on a production order component line defines the *take* bin from where components are decreased when posting consumption. When you use inventory movements, the **Bin Code** field on production order component lines defines the *place* bin in the operation area where the warehouse worker must place the components.  

5. On the **Bins** FastTab, in the **From-Production Bin Code** field, enter the code of the bin in the production area where finished end items are taken from by default when the process involves a warehouse activity. In basic warehouse configurations, the activity is recorded as an inventory put-away or an inventory movement.  

Now, production order component lines with the default bin code require that forward-flushed components are placed there. However, until the components are consumed from that bin, other component demands may pick or consume from that bin because they are still considered available bin contents. To make sure that bin content is only available to component demand that uses that to-production bin, you must select the **Dedicated** field on the line for that bin code on the **Bins** page that you open from the location card.

This flow chart shows how the **Bin Code** field on production order component lines is filled according to your setup.  

![Bin flow chart](media/binflow.png "BinFlow")    

## To define a default bin structure in the assembly area
Components for assembly orders cannot be picked or posted with inventory picks. Instead, use the **Inventory Movement** page. For more information, see [Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

When picking and shipping sales line quantities that are assembled to the order, you must follow certain rules when creating the inventory pick lines. For more information, see the “Handling Assemble-to-Order Items in Inventory Picks” section in [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).

For more information, see [Assembly Management](assembly-assemble-items.md).

### To set up that an inventory movement is automatically created when the inventory pick for the assembly item is created
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly Setup**, and then choose the related link.
2. Select the **Create Movements Automatically** check box.

### To set up the bin in the assembly area where components are placed by default before they can be consumed in assembly
The value in this field is automatically inserted in the **Bin Code** field on assembly order lines when this location is entered in the **Location Code** field on the assembly order line.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.
3. Fill in the **To-Assembly Bin Code** field.

### To set up the bin in the assembly area where finished assembly items are posted to when they are assembled to stock
The value in this field is automatically inserted in the **Bin Code** field on assembly order headers when this location code is filled into the **Location Code** field on the assembly order header.

Bin codes that are set up on location cards define a default warehouse flow for specific warehouse activities, such as consumption of components in an assembly area. Additional functionality exists to make sure that when items are placed in a default bin, they cannot be moved or picked to other activities.

> [!NOTE]
> This setup is only possible for locations where the Bin Mandatory field is selected.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.
3. Fill in the **From-Assembly Bin Code** field.

### To set up the bin where finished assembly items are posted to when they are assembled to a linked sales order
From this bin, the assembly items are shipped immediately, via an inventory pick, to fulfill the sales order.

> [!NOTE]
> This field cannot be used if the location is set up to use directed pick and put-away.

The bin code is copied from the sales order line to the assembly order header to communicate to assembly workers where to place the output to ready it for shipping. It is also copied to the inventory pick line to communicate to warehouse workers where to take it from to ship it.

> [!NOTE]
> The Assemble-to-Order Shipment bin is always empty. When you post an assemble-to-order sales line, then the bin content is first positively adjusted with the assembly output. Immediately after, it is negatively adjusted with the shipped quantity.

The value in this field is automatically inserted in the Bin Code field on sales order lines that contain a quantity in the **Qty. to Assemble to Order** field or if the item to be sold has **Assemble-to-Order** in the **Replenishment System** field.

If the **Asm.-to-Order Shpt. Bin Code** is blank, then the **From-Assembly Bin Code** field is used instead. If both setup fields are blank, then the last used bin with content is used in the **Bin Code** field on sales order lines.

The same bin code is in turn copied to the **Bin Code** field on the inventory pick line that manages the shipment of the assemble-to-order quantity. For more information, see the “Handling Assemble-to-Order Items in Inventory Picks” section in [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.
3. Fill in the **Asm.-to-Order Shpt. Bin Code** field.

## To create dedicated component bins
You can specify that quantities in a bin are protected from being picked for other demands than demand from their current purpose.

Quantities in dedicated bins can still be reserved. Accordingly, the quantities in dedicated bins are included in the **Total Available Quantity** field on the **Reservation** page.

For example, is a work center is set up with a bin code in the **To-Production Bin Code** field. Production order component lines with that bin code require that forward-flushed components are placed there. However, until the components are consumed from that bin, other component demands may pick or consume from that bin because they are still considered available bin contents. To make sure that bin content is only available to component demand that uses that to-production bin, you must select the **Dedicated** field on the line for that bin code on the **Bins** page that you open from the location card.

Making a bin dedicated provides similar functionality to using bin types, which is only available in advanced warehousing. For more information, see [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).

> [!Caution]
> Items in dedicated bins are not protected when they are picked and consumed as production components with the Inventory Pick page.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link. Select the location that you want to update.  
2.  Choose the **Bins** action.  
3.  Select the **Dedicated** field for each bin that you want to use exclusively for certain internal operations and where you want quantities to be reserved for that internal operation once placed there.  

> [!NOTE]  
>  The bin must be empty before you can select or clear the **Dedicated** field.

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
