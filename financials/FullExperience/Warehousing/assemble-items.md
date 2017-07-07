---
    title: Assemble Items | Microsoft Docs
    description: To support companies that supply products to their customers by combining components in simple processes without the need of manufacturing functionality, ADD INCLUDE<!--[!INCLUDE[navnowlong](../../includes/navnowlong_md.md)]--> includes features to assemble items that integrate with existing features, such as sales, planning, reservations, and warehousing.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Assemble Items
To support companies that supply products to their customers by combining components in simple processes without the need of manufacturing functionality, ADD INCLUDE<!--[!INCLUDE[navnowlong](../../includes/navnowlong_md.md)]--> includes features to assemble items that integrate with existing features, such as sales, planning, reservations, and warehousing.  

 An assembly item is defined as a sellable item that contains an assembly BOM. For more information, see [How to: Create Assembly BOMs](assemble-to-order-or-assemble-to-stock.md).  

 Assembly orders are internal orders, just like production orders, that are used to manage the assembly process and to connect the sales requirements with the involved warehouse activities. Assembly orders differ from other order types because they involve both output and consumption when posting. The assembly order header behaves similarly to a sales order line, and the assembly order lines behave similarly to consumption journal lines. For more information, see Assembly Order.  

 To support a just-in-time inventory strategy and the ability to customize products to customer requests, assembly orders may be automatically created and linked as soon as the sales order line is created. The link between the sales demand and the assembly supply enables sales order processors to customize the assembly item on the fly, promise delivery dates according to component availability, and to post output and shipment of the assembled item directly from their sales order interface. For more information, see [How to: Sell Items Assembled to Order](how-to-sell-items-assembled-to-order.md).  

 On one sales order line, you can sell a quantity that is available and must be picked from stock together with a quantity that must be assembled to the order. Certain rules exist to govern the distribution of such quantities to ensure that assemble-to-order quantities take priority over inventory quantities in partial shipping. For more information, see the “Combination Scenarios” section in [Assemble to Order or Assemble to Stock](assemble-to-order-or-assemble-to-stock.md).  

 Special functionality exists to govern the shipping of assemble-to-order quantities. When an assemble-to-order quantity is ready to be shipped, the warehouse worker in charge posts an inventory pick for the sales order line(s) in question. This, in turn, creates an inventory movement for the components, posts the assembly output, and the sales order shipment. For more information, see “Handling Assemble-to-Order Items in Inventory Picks” in Inventory Pick.  

 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  

|**To**|**See**|  
|------------|-------------|  
|Specify which and how many items to assemble and which items or resources go into the assembly item.|Assembly Order|  
|Learn about the difference between assembly BOMs and production BOMs and the involved processing differences.|[Assembly BOMs or Production BOMs](assembly-boms-or-production-boms.md)|  
|Learn about the difference between assembling items right before shipping sales orders and assembling items that are intended for storage.|[Assemble to Order or Assemble to Stock](assemble-to-order-or-assemble-to-stock.md)|  
|Combine components to create an item in a simple process.|[How to: Assemble Items](how-to-assemble-items.md)|  
|Sell kits that are not currently available by instantaneously creating an assembly order to supply the full or partial sales order quantity, while supporting potential customization of the kit.|[How to: Sell Items Assembled to Order](how-to-sell-items-assembled-to-order.md)|  
|Learn how assembly consumption and output are handled when you post assembly orders and how the derived item and resource costs are processed and distributed to the general ledger.|[Design Details: Assembly Order Posting](design-details-assembly-order-posting.md)|  

## See Also  
 [Perform Warehouse Activities](perform-warehouse-activities.md)   
 [Define Material and Process Structure](define-material-and-process-structure.md)   
 [Design Details: Warehouse Management](design-details-warehouse-management.md)
