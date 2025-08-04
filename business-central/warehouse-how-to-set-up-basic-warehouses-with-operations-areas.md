---
title: Set up basic warehouses with operations areas
description: Set up warehouse operations areas and use inventory movements, picks, and put-aways to move goods between them.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 6774, 6775, 6776
ms.date: 03/04/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Set up basic warehouses with operations areas

If you have internal operation areas, such as production or assembly areas, you can use the following basic warehouse documents to record your warehouse activities:  

- **Inventory Movement** page.  
- **Inventory Pick** page.  
- **Inventory Put-away** page.

To use these documents, you must set up one or more of the following fields on the the **Location Card** page for the location:

- The **Bin Mandatory** field.
- The **Inventory Pick/Movement** option in the **Prod. Consumption Whse. Handling** field.
- The **Inventory Movement** option in the **Asm. Consumption Whse. Handling** field.
- The **Inventory Put-Away** in the **Prod. Output Whse. Handling** field.

> [!NOTE]
> You can still post output and consumption directly from the source documents and journals.  

To use these pages with internal operations such as to pick and move components to production, depending on how much control you need you must do some or all the following steps:  

- Enable the inventory pick, move, and put-away documents.  
- Define default bin structures for components and end items flowing to and from operation resources.  
- Make to- and from- bins that are dedicated to specific operation resources. Dedicated bins prevent the items from being picked for outbound documents.

Bin codes that are set up on location cards define a default warehouse flow for certain activities, such as components in an assembly department. Other functionality exists to make sure that when items are placed in a certain bin, they can't be moved or picked to other activities. To learn more, go to [To create dedicated component bins](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md#to-create-dedicated-component-bins).

The following procedures are based on setting up basic warehouse activities around a production area. The steps are similar for other operation areas, such as assembly, service management, and jobs.  

> [!NOTE]  
> The following procedures assume that the **Bin Mandatory** toggle is turned on for the location.  

## To enable inventory documents for internal operation activities

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the location card you want to set up.  
3. On the **Warehouse** FastTab, select **Inventory Put-Away** in the **Prod. Output Whse. Handling** field to indicate that when someone releases an internal source document with a bin code, an inventory put-away or movement document can be created.  
4. To require that an inventory pick or an inventory movement document when you create an outbound or internal source document with a bin code, fill in the following fields:

   - In the **Prod. Consumption Whse. Handling field**, choose **Inventory Pick/Movement**.
   - In the **Asm. Consumption Whse. Handling** field, choose **Inventory Movement**.  

## To define a default bin structure in the production area

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.  
3. On the **Bins** FastTab, in the **Open Shop Floor Bin Code** field, enter the code of the bin in the production area with plenty of components that the machine operator can consume from without requesting a warehouse activity to bring them to the bin. Items that are placed in this bin are typically set up for automatic posting, or flushing. This setup means that the **Flushing Method** field contains **Forward**, **Backward**, or **Manual**.  

   > [!TIP]
   > You can also record flushing without requiring a pick. For example, skipping the pick might be useful for components which, due to their nature, you store in the shop floor zone so there's no need to pick. However, you might still have to manually post consumption, for example, because the consumed quantity can vary or require item tracking. To flush without picking, the item must use the **Pick + Manual** flushing method. To learn more, go to [Flushing methods](production-how-to-flush-components-according-to-operation-output.md#flushing-methods).

4. In the **To-Production Bin Code** field, enter the code of the bin in the production area where components that are picked for production at this location are placed by default before they can be consumed. Items that are placed in this bin are typically set up for manual picking. The **Flushing Method** field contains **Pick + Forward**, **Pick + Backward**, or **Pick + Manual** for warehouse picks and inventory movements.  

    > [!NOTE]  
    > When you use inventory picks, the **Bin Code** field on a production order component line defines the *take* bin from where components are decreased when posting consumption. When you use inventory movements, the **Bin Code** field on production order component lines defines the *place* bin in the operation area where the warehouse worker must place the components.  

5. On the **Bins** FastTab, in the **From-Production Bin Code** field, enter the code of the bin in the production area where finished end items are taken from by default when the process involves a warehouse activity. In basic warehouse configurations, the activity is recorded as an inventory put-away or an inventory movement.  

Now, production order component lines with the default bin code require that forward-flushed components are placed there. However, until the components are consumed from that bin, other component demands might pick or consume from that bin because they're still considered available bin contents. To make sure that bin content is only available to component demand that uses that to-production bin, you must select the **Dedicated** field on the line for that bin code on the **Bins** page that you open from the location card.

This flow chart shows how the **Bin Code** field on production order component lines is filled according to your setup.  

![Bin flow chart.](media/binflow.png "BinFlow")

## To define a default bin structure in the assembly area

Components for assembly orders can't be picked or posted with inventory picks. Instead, use the **Inventory Movement** page. To learn more, go to [Pick or move for Production, Assembly, or Jobs in Basic Warehouse](warehouse-how-to-pick-for-production.md).

When picking and shipping sales line quantities that are assembled to the order, you must follow certain rules when creating the inventory pick lines. To learn more, go to [Handling assemble-to-order items with inventory picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

To learn more, go to [Assembly Management](assembly-assemble-items.md).

### To set up that an inventory movement is automatically created when the inventory pick for the assembly item is created

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly Setup**, and then choose the related link.
2. Select the **Create Movements Automatically** checkbox.

### To set up the bin in the assembly area where components are placed by default before they can be consumed in assembly

The value in this field is automatically inserted in the **Bin Code** field on assembly order lines when this location is entered in the **Location Code** field on the assembly order line.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.
3. Fill in the **To-Assembly Bin Code** field.

### To set up the bin in the assembly area where finished assembly items are posted to when they're assembled to stock

The value in this field is automatically inserted in the **Bin Code** field on assembly order headers when this location code is filled into the **Location Code** field on the assembly order header.

Bin codes that are set up on location cards define a default warehouse flow for specific warehouse activities, such as consumption of components in an assembly area. Other functionality exists to make sure that when items are placed in a default bin, they can't be moved or picked to other activities.

> [!NOTE]
> This setup is only possible for locations where the **Bin Mandatory** field is selected.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.
3. Fill in the **From-Assembly Bin Code** field.

### To set up the bin where finished assembly items are posted to when they're assembled to a linked sales order

From this bin, the assembly items are shipped immediately, via an inventory pick, to fulfill the sales order.

> [!NOTE]
> You can't use this field if the location is set up to use directed pick and put-away.

The bin code is copied from the sales order line to the assembly order header to communicate to assembly workers where to place the output to ready it for shipping. It's also copied to the inventory pick line to communicate to warehouse workers where to take it from to ship it.

> [!NOTE]
> The Assemble-to-Order Shipment bin is always empty. When you post an assemble-to-order sales line, then the bin content is first positively adjusted with the assembly output. Immediately after, it's negatively adjusted with the shipped quantity.

The value in this field is automatically inserted in the Bin Code field on sales order lines that contain a quantity in the **Qty. to Assemble to Order** field or if the item to be sold has **Assemble-to-Order** in the **Replenishment System** field.

If the **Asm.-to-Order Shpt. Bin Code** is blank, then the **From-Assembly Bin Code** field is used instead. If both setup fields are blank, then the last used bin with content is used in the **Bin Code** field on sales order lines.

The same bin code is in turn copied to the **Bin Code** field on the inventory pick line that manages the shipment of the assemble-to-order quantity. To learn more, go to [Handling assemble-to-order items with inventory picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Open the Location you want to set up.
3. Fill in the **Asm.-to-Order Shpt. Bin Code** field.

## To create dedicated component bins

You can specify that quantities in a bin are protected from being picked for other demands than demand from their current purpose.

Quantities in dedicated bins can still be reserved. Accordingly, the quantities in dedicated bins are included in the **Total Available Quantity** field on the **Reservation** page.

For example, is a work center is set up with a bin code in the **To-Production Bin Code** field. Production order component lines with that bin code require that forward-flushed components are placed there. However, until the components are consumed from that bin, other component demands might pick or consume from that bin because they're still considered available bin contents. To make sure that bin content is only available to component demand that uses that to-production bin, you must select the **Dedicated** field on the line for that bin code on the **Bins** page that you open from the location card.

Making a bin dedicated provides similar functionality to using bin types, which is only available in advanced warehousing. To learn more, go to [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).

> [!CAUTION]
> Items in dedicated bins are not protected when they are picked and consumed as production components with the Inventory Pick page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link. Select the location that you want to update.  
2. Choose the **Bins** action.  
3. Select the **Dedicated** field for each bin that you want to use exclusively for certain internal operations and where you want quantities to be reserved for that internal operation once placed there.  

> [!NOTE]  
> The bin must be empty before you can select or clear the **Dedicated** field.

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
