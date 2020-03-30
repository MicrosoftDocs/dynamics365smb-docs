---
    title: Assembly Management | Microsoft Docs
    description: Support companies that supply products to their customers by combining components in simple processes without the need of manufacturing functionality but with features to assemble items that integrate with existing features, such as sales, planning, reservations, and warehousing.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: kit, kitting
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Assembly Management
To support companies that supply products to their customers by combining components in simple processes without the need of manufacturing functionality, [!INCLUDE[d365fin](includes/d365fin_md.md)] includes features to assemble items that integrate with existing features, such as sales, planning, reservations, and warehousing.  

 An assembly item is defined as a sellable item that contains an assembly BOM. For more information, see [Work with Bills of Material](inventory-how-work-BOMs.md).

 Assembly orders are internal orders, just like production orders, that are used to manage the assembly process and to connect the sales requirements with the involved warehouse activities. Assembly orders differ from other order types because they involve both output and consumption when posting. The assembly order header behaves similarly to an output journal line, and the assembly order lines behave similarly to consumption journal lines.  

 To support a just-in-time inventory strategy and the ability to customize products to customer requests, assembly orders may be automatically created and linked as soon as the sales order line is created. The link between the sales demand and the assembly supply enables sales order processors to customize the assembly item on the fly, promise delivery dates according to component availability, and to post output and shipment of the assembled item directly from their sales order interface. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

 On one sales order line, you can sell a quantity that is available and must be picked from stock together with a quantity that must be assembled to the order. Certain rules exist to govern the distribution of such quantities to ensure that assemble-to-order quantities take priority over inventory quantities in partial shipping. For more information, see the “Combination Scenarios” section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).  

 Special functionality exists to govern the shipping of assemble-to-order quantities. When an assemble-to-order quantity is ready to be shipped, the warehouse worker in charge posts an inventory pick for the sales order line(s) in question. This, in turn, creates an inventory movement for the components, posts the assembly output, and the sales order shipment. For more information, see the "Handling Assemble-to-Order Items in Inventory Picks” section in [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).

The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Learn about the difference between assembling items right before shipping sales orders and assembling items that are intended for storage.|[Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md)|
|Fill in fields on location cards and in inventory setup to define how items flow to and from the assembly department.|[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)|
|Customize an assembly item to a customer’s request during the sales process, and convert to a sale when accepted.|[Quote an Assemble-to-Order Sale](assembly-how-to-quote-an-assemble-to-order-sale.md)|
|Combine components to create an item in a simple process, to order or to stock.|[Assemble Items](assembly-how-to-assemble-items.md)|  
|Sell assembly items that are not currently available by creating a linked assembly order to supply the full or partial sales order quantity.|[Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md)|
|When some assemble-to-order items are already in inventory, deduct that quantity from the assembly order and reserve it from inventory.|[Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md)|  
|When you are selling assembly items from inventory and all items are not available, initiate an assembly order to automatically supply a part or all of the sales order quantity.|[Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md)|
|Make customized assembly items for blanket sales orders before periodically making the actual sales orders according to the blanket order agreement.|[Create Blanket Assembly Orders](assembly-how-to-create-blanket-assembly-orders.md)|
|Undo a posted assembly order, for example because the order was posted with mistakes that must be corrected.|[Undo Assembly Posting](assembly-how-to-undo-assembly-posting.md)|
|Learn about the difference between assembly BOMs and production BOMs and the involved processing differences.|[Work with Bills of Material](inventory-how-work-BOMs.md)|
|Learn how assembly consumption and output are handled when you post assembly orders and how the derived item and resource costs are processed and distributed to the general ledger.|[Design Details: Assembly Order Posting](design-details-assembly-order-posting.md)|  

## See Related Training at [Microsoft Learn](/learn/paths/assemble-items-dynamics-365-business-central/)

## See Also  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
