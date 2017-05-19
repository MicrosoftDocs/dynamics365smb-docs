---
title: "Assembly BOMs or Production BOMs"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "BOM, assembly"
  - "assembly BOMs, about"
  - "BOM, production"
  - "assembly, BOM"
ms.assetid: a5ad8d35-88da-49f4-b379-84c4aca06f54
caps.latest.revision: 11
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
# Assembly BOMs or Production BOMs
You use assembly orders for making end items from components in a simple process that can be performed by one or more basic resources, which are not machine or work centers, or without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and then pack them as a gift item. For more information, see [\($ N\_900 Assembly Order $\)](../WarehouseActivities/-$-n_900-assembly-order-$-.md).  
  
 The master data behind assembly items is represented by assembly BOMs.  
  
 You use production orders for making end items from components in a complex process that requires a production routing and work or machine centers, which represent production capacities. For example, a production process could be to cut steel plates in one operation, weld them in the next operation, and paint the end item in the last operation. For more information, see [\($ N\_99000831 Released Production Order $\)](../Topic/\($%20N_99000831%20Released%20Production%20Order%20$\).md).  
  
 The master data behind production items is represented by production BOMs.  
  
## Assembly BOMs  
 An assembly BOM is the master data that defines which component items go into an assembled end item and which resources are used to assemble the assembly item. For more information, see [How to: Create Assembly BOMs](../DesignAndEngineering/how-to-create-assembly-boms.md).  
  
 When you enter an assembly item and a quantity in the header of a new assembly order, then the assembly order lines are automatically filled according to the assembly BOM with one assembly order line per component or resource. For more information, see [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md).  
  
 Both assembly orders and production orders may be linked directly to sales orders. However, you can only use assembly orders to customize the end item directly for a customer request with the sales order. For more information, see [How to: Sell Items Assembled to Order](../Sales/how-to-sell-items-assembled-to-order.md).  
  
## Production BOMs  
 A production BOM is the master data that defines a production item and the components that go into it. for assembly items, the production BOM must be certified and assigned to the production item before it can be used in a production order. When you enter the production item on a production order line, either manually or by refreshing the order, then the production BOM content becomes the production order components. For more information, see [How to: Create Production BOMs](../DesignAndEngineering/how-to-create-production-boms.md).  
  
 The concept of resources in production is much more advanced than in assembly management. Work centers and machine centers function as resources, and production steps are represented by operations that are assigned to resources in production routings. For more information, see [How to: Create Routings](../DesignAndEngineering/how-to-create-routings.md).  
  
## See Also  
 [\($ N\_900 Assembly Order $\)](../WarehouseActivities/-$-n_900-assembly-order-$-.md)   
 [\($ N\_99000831 Released Production Order $\)](../Topic/\($%20N_99000831%20Released%20Production%20Order%20$\).md)   
 [How to: Create Assembly BOMs](../DesignAndEngineering/how-to-create-assembly-boms.md)   
 [\($ N\_36 Assembly BOM $\)](../Topic/\($%20N_36%20Assembly%20BOM%20$\).md)   
 [\($ N\_99000786 Production BOM $\)](../Topic/\($%20N_99000786%20Production%20BOM%20$\).md)   
 [How to: Assemble Items](../WarehouseActivities/how-to-assemble-items.md)   
 [How to: Sell Items Assembled to Order](../Sales/how-to-sell-items-assembled-to-order.md)   
 [How to: Create Production BOMs](../DesignAndEngineering/how-to-create-production-boms.md)   
 [How to: Create Routings](../DesignAndEngineering/how-to-create-routings.md)   
 [Assemble to Order or Assemble to Stock](../DesignAndEngineering/assemble-to-order-or-assemble-to-stock.md)