---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# Assembly BOMs or Production BOMs
You use assembly orders for making end items from components in a simple process that can be performed by one or more basic resources, which are not machine or work centers, or without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and then pack them as a gift item. For more information, see Assembly Order.  
  
 The master data behind assembly items is represented by assembly BOMs.  
  
 You use production orders for making end items from components in a complex process that requires a production routing and work or machine centers, which represent production capacities. For example, a production process could be to cut steel plates in one operation, weld them in the next operation, and paint the end item in the last operation. For more information, see Released Production Order.  
  
 The master data behind production items is represented by production BOMs.  
  
## Assembly BOMs  
 An assembly BOM is the master data that defines which component items go into an assembled end item and which resources are used to assemble the assembly item. For more information, see [How to: Create Assembly BOMs](../FullExperience/how-to-create-assembly-boms.md).  
  
 When you enter an assembly item and a quantity in the header of a new assembly order, then the assembly order lines are automatically filled according to the assembly BOM with one assembly order line per component or resource. For more information, see [How to: Assemble Items](../FullExperience/how-to-assemble-items.md).  
  
 Both assembly orders and production orders may be linked directly to sales orders. However, you can only use assembly orders to customize the end item directly for a customer request with the sales order. For more information, see [How to: Sell Items Assembled to Order](../FullExperience/how-to-sell-items-assembled-to-order.md).  
  
## Production BOMs  
 A production BOM is the master data that defines a production item and the components that go into it. for assembly items, the production BOM must be certified and assigned to the production item before it can be used in a production order. When you enter the production item on a production order line, either manually or by refreshing the order, then the production BOM content becomes the production order components. For more information, see [How to: Create Production BOMs](../FullExperience/how-to-create-production-boms.md).  
  
 The concept of resources in production is much more advanced than in assembly management. Work centers and machine centers function as resources, and production steps are represented by operations that are assigned to resources in production routings. For more information, see [How to: Create Routings](../FullExperience/how-to-create-routings.md).  
  
## See Also  
 Assembly Order   
 Released Production Order   
 [How to: Create Assembly BOMs](../FullExperience/how-to-create-assembly-boms.md)   
 Assembly BOM   
 Production BOM   
 [How to: Assemble Items](../FullExperience/how-to-assemble-items.md)   
 [How to: Sell Items Assembled to Order](../FullExperience/how-to-sell-items-assembled-to-order.md)   
 [How to: Create Production BOMs](../FullExperience/how-to-create-production-boms.md)   
 [How to: Create Routings](../FullExperience/how-to-create-routings.md)   
 [Assemble to Order or Assemble to Stock](../FullExperience/assemble-to-order-or-assemble-to-stock.md)