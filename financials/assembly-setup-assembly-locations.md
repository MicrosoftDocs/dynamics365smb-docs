---
    title: How to: Set Up Assembly Locations| Microsoft Docs
    description:
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/21/2017
    ms.author: sgroespe

---
# How to: Set Up Assembly Locations
Components for assembly orders cannot be picked or posted with inventory picks. Instead, use the **Inventory Movement** window. For more information, see [How to: Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

When picking and shipping sales line quantities that are assembled to the order, you must follow certain rules when creating the inventory pick lines. For more information, see the “Handling Assemble-to-Order Items in Inventory Picks” section in [How to: Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).

## To set up that an inventory movement is automatically created when the inventory pick for the assembly item is created
1. To enable this, you must select the **Create Movements Automatically** field in the **Assembly Setup** window.
2.

## To set up the bin bin in the assembly area where components are placed by default before they can be consumed in assembly
The value in this field is automatically inserted in the Bin Code field on assembly order lines when this location is entered in the Location Code field on the assembly order line.

Bin codes that are set up on location cards define a default warehouse flow for certain activities, such as components in an assembly department. Additional functionality exists to make sure that when items are placed in a certain bin, they cannot be moved or picked to other activities. For more information, see how to use the Dedicated field in the Bins window.

1. location card
2. To-Assembly Bin Code field

## To set up the bin in the assembly area where finished assembly items are posted to when they are assembled to stock
The value in this field is automatically inserted in the Bin Code field on assembly order headers when this location code is filled into the Location Code field on the assembly order header.

Assembly items that are assembled to sales orders must be shipped immediately instead of going to storage. For more information about how to set the location up for this flow, see the Asm.-to-Order Shpt. Bin Code field.

Bin codes that are set up on location cards define a default warehouse flow for specific warehouse activities, such as consumption of components in an assembly area. Additional functionality exists to make sure that when items are placed in a default bin, they cannot be moved or picked to other activities. For more information, see how to use the Dedicated field in the Bins window.

This setup is only possible for locations where the Bin Mandatory field is selected.

1. location cards
2. From-Assembly Bin Code field

## To set up the bin where finished assembly items are posted to when they are assembled to a linked sales order
From this bin, the assembly items are shipped immediately, via an inventory pick, to fulfill the sales order.

Note  
This field cannot be used if the location is set up to use directed pick and put-away.

The bin code is copied from the sales order line to the assembly order header to communicate to assembly workers where to place the output to ready it for shipping. It is also copied to the inventory pick line to communicate to warehouse workers where to take it from to ship it.

Note  
The Assemble-to-Order Shipment bin is always empty. When you post an assemble-to-order sales line, then the bin content is first positively adjusted with the assembly output. Immediately after, it is negatively adjusted with the shipped quantity.

The value in this field is automatically inserted in the Bin Code field on sales order lines that contain a quantity in the Qty. to Assemble to Order field or if the item to be sold has Assemble-to-Order in the Replenishment System field.

If the Asm.-to-Order Shpt. Bin Code is blank, then the From-Assembly Bin Code is used instead. If both setup fields are blank, then the last used bin with content is used in the Bin Code field on sales order lines.

The same bin code is in turn copied to the Bin Code field on the inventory pick line that manages the shipment of the assemble-to-order quantity. For more information, see “Handling Assemble-to-Order Items in Inventory Picks” in Inventory Pick.

Bin codes that are set up on location cards define a default warehouse flow for specific warehouse activities, such as consumption of components in an assembly area. Additional functionality exists to make sure that when items are placed in a default bin, they cannot be moved or picked to other activities. For more information, see Dedicated.

1. location cards
2. Asm.-to-Order Shpt. Bin Code Field

## See Also  
[How to: Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
