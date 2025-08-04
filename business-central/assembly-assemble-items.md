---
title: Assembly Management
description: Learn how to supply products to customers by combining components in simple processes without using manufacturing features.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 06/10/2025
ms.custom: bap-template
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.service: dynamics-365-business-central
---
# Assembly Management

Companies can supply products to customers by combining components without using manufacturing features. Features for assembling items integrate with related features such as sales, planning, reservations, and warehousing.  

An assembly item is a sellable item that contains an assembly BOM. To learn more about assembly BOMs, go to [Work with Assembly BOMs](assembly-how-work-assembly-boms.md).

Assembly orders are internal orders, just like production orders. Use assembly orders to manage the assembly process and to connect sales requirements with warehouse activities. Assembly orders involve both output and consumption when posting. Assembly order headers are similar to output journal lines. Assembly order lines are similar to consumption journal lines.  

You can use a just-in-time inventory strategy and customize products to meet customer requests. Assembly orders can be automatically created and linked when you create a sales order line. The link between the sales demand and assembly supply opens up for several opportunities when you process sales orders:

* Customize assembly items on the fly.
* Promise delivery dates according to component availability.
* Post output and shipment of the assembled item directly from their sales orders.

To learn more about selling assembly items, go to [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

Lines on sales orders can contain items to pick from stock and items to assemble for the order. The assemble-to-order quantities take priority over inventory quantities in partial shipping. To learn more about selling stock and assembly items, go to [Combination Scenarios](assembly-assemble-to-order-or-assemble-to-stock.md#combination-scenarios).  

When an assemble-to-order quantity is ready to ship, a warehouse employee can post an inventory pick for the sales order lines. Posting an inventory pick does a couple of things:

* Create an inventory movement for the components
* Post the assembly output and the sales order shipment.

To learn more about assemble-to-order items and inventory picks, go to [Handling Assemble-to-Order Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

The following table describes a sequence of tasks, with links to the articles that describe them.

|To...|Go to...|  
|------------|-------------|  
|Learn about assembling items for sales orders and storage.|[Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md)|
|Use location cards and your inventory setup to define how items flow to and from assembly.|[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)|
| Explore built-in assembly reports. | [Assembly report overview](assembly-reports.md) |
|Quote a custom assembly item, and then convert the quote to a sale when the customer accepts it.|[Quote an Assemble-to-Order Sale](assembly-how-to-quote-an-assemble-to-order-sale.md)|
|Combine components to create an item to order or to stock.|[Assemble Items](assembly-how-to-assemble-items.md)|  
|Sell assembly items that aren't currently available by creating a linked assembly order to supply the full or partial sales order quantity.|[Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md)|
|When assemble-to-order items are already in inventory, deduct the quantity from the assembly order and reserve it from inventory.|[Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md)|  
|When assembly items aren't in inventory, use an assembly order to supply some or all of the quantity.|[Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md)|
|Make custom assembly items for blanket sales orders before you create the sales orders.|[Create Blanket Assembly Orders](assembly-how-to-create-blanket-assembly-orders.md)|
|Undo a posted assembly order, for example because the order was posted with mistakes.|[Undo Assembly Posting](assembly-how-to-undo-assembly-posting.md)|
|Learn how to work with assembly BOMs and how they differ from production BOMs.|[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)|
|Learn about posting assembly consumption and output, and how [!INCLUDE [prod_short](includes/prod_short.md)] distributes item and resource costs to the general ledger.|[Design Details: Assembly Order Posting](design-details-assembly-order-posting.md)|  

## Related information

[Assembly report overview](assembly-reports.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Design Details: Supply Planning](design-details-supply-planning.md)  
<!-- [Walkthrough: Planning Supplies Manually](walkthrough-planning-supplies-manually.md)   -->
<!-- [Walkthrough: Selling, Assembling, and Shipping Kits](walkthrough-selling-assembling-and-shipping-kits.md)   -->
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
