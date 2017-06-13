---
title: "Assemble Items"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "assemble"
  - "kit"
ms.assetid: 4decca19-d1af-4357-af25-83e71f122c4d
caps.latest.revision: 3
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
To support companies that supply products to their customers by combining components in simple processes without the need of manufacturing functionality, [!INCLUDE[navnowlong](../Token/navnowlong_md.md)] includes features to assemble items that integrate with existing features, such as sales, planning, reservations, and warehousing.  
  
 An assembly item is defined as a sellable item that contains an assembly BOM. For more information, see [How to: Create Assembly BOMs](../Topic/How%20to:%20Create%20Assembly%20BOMs.md). You can set up assembly items to be assembled to order or assembled to stock. This typically depends on how much customization that is required to fulfill a customer’s order for the item. For more information, see [Assemble to Order or Assemble to Stock](../Topic/Assemble%20to%20Order%20or%20Assemble%20to%20Stock.md).  
  
 Assembly orders are internal orders, just like production orders, that are used to manage the assembly process and to connect the sales requirements with the involved warehouse activities. Assembly orders differ from other order types because they involve both output and consumption when posting. The assembly order header behaves similarly to a sales order line, and the assembly order lines behave similarly to consumption journal lines. For more information, see [Assembly Order](../Topic/\($%20N_900%20Assembly%20Order%20$\).md).  
  
 To support a just\-in\-time inventory strategy and the ability to customize products to customer requests, assembly orders may be automatically created and linked as soon as the sales order line is created. The link between the sales demand and the assembly supply enables sales order processors to customize the assembly item on the fly, promise delivery dates according to component availability, and to post output and shipment of the assembled item directly from their sales order interface. For more information, see [How to: Sell Items Assembled to Order](../Topic/How%20to:%20Sell%20Items%20Assembled%20to%20Order.md).  
  
 On one sales order line, you can sell a quantity that is available and must be picked from stock together with a quantity that must be assembled to the order. Certain rules exist to govern the distribution of such quantities to ensure that assemble\-to\-order quantities take priority over inventory quantities in partial shipping. For more information, see the “Combination Scenarios” section in [Assemble to Order or Assemble to Stock](../Topic/Assemble%20to%20Order%20or%20Assemble%20to%20Stock.md).  
  
 Special functionality exists to govern the shipping of assemble\-to\-order quantities. When an assemble\-to\-order quantity is ready to be shipped, the warehouse worker in charge posts an inventory pick for the sales order line\(s\) in question. This, in turn, creates an inventory movement for the components, posts the assembly output, and the sales order shipment. For more information, see “Handling Assemble\-to\-Order Items in Inventory Picks” in [Inventory Pick](../Topic/\($%20N_7377%20Inventory%20Pick%20$\).md).  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Specify which and how many items to assemble and which items or resources go into the assembly item.|[Assembly Order](../Topic/\($%20N_900%20Assembly%20Order%20$\).md)|  
|Learn about the difference between assembly BOMs and production BOMs and the involved processing differences.|[Assembly BOMs or Production BOMs](../Topic/Assembly%20BOMs%20or%20Production%20BOMs.md)|  
|Learn about the difference between assembling items right before shipping sales orders and assembling items that are intended for storage.|[Assemble to Order or Assemble to Stock](../Topic/Assemble%20to%20Order%20or%20Assemble%20to%20Stock.md)|  
|Combine components to create an item in a simple process.|[How to: Assemble Items](../Topic/How%20to:%20Assemble%20Items.md)|  
|Sell kits that are not currently available by instantaneously creating an assembly order to supply the full or partial sales order quantity, while supporting potential customization of the kit.|[How to: Sell Items Assembled to Order](../Topic/How%20to:%20Sell%20Items%20Assembled%20to%20Order.md)|  
|Learn how assembly consumption and output are handled when you post assembly orders and how the derived item and resource costs are processed and distributed to the general ledger.|[Design Details: Assembly Order Posting](../Topic/Design%20Details:%20Assembly%20Order%20Posting.md)|  
  
## See Also  
 [Perform Warehouse Activities](../Topic/Perform%20Warehouse%20Activities.md)   
 [Define Material and Process Structure](../Topic/Define%20Material%20and%20Process%20Structure.md)   
 [Design Details: Warehouse Management](../Topic/Design%20Details:%20Warehouse%20Management.md)