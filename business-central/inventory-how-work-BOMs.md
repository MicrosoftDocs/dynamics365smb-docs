---
title: Work with bills of material
description: You create an assembly BOM or production BOM to specify the components or resources required to put together the item that the BOM represents.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: bills of material, assembly BOM, production BOM,
ms.search.form: 
ms.date: 06/06/2024
ms.service: dynamics-365-business-central

---
# Work with bills of material

You use bills of materials (BOMs) to structure parent items that must be assembled from other items or produced by resources or machine centers from components.

## Assembly BOMs or production BOMs

[!INCLUDE[prod_short](includes/prod_short.md)] supports two different types of BOMs:

| BOM type | General category | Example |
| -------- | ---------------- | ------- |
| [Assembly BOMs](assembly-how-work-assembly-boms.md) | Warehouse / assembly | Items that consist of other items, assembled with basic or no resources. |
| [Production BOMs](production-how-to-create-production-boms.md) | Manufacturing / production | Items that consist of different components and subassemblies, produced at a work or machine center. |

You use assembly orders for making end items from components in a simple process that can be performed by one or more basic resources, which aren't machine or work centers, or without any resources. For example, an assembly process could be to pick two wine bottles and one coffee sack and then pack them as a gift item.  

An assembly BOM is the master data that defines which component items go into an assembled end item and which resources are used to assemble the assembly item. When you enter an assembly item and a quantity in the header of a new assembly order, the assembly order lines automatically fil in according to the assembly BOM with one assembly order line per component or resource. Learn more at [Assembly Management](assembly-assemble-items.md).

You use production orders for making end items from components in a complex process that requires a production routing and work or machine centers, which represent production capacities. For example, a production process could be to cut steel plates in one operation, weld them in the next operation, and paint the end item in the last operation. Learn more at [Manufacturing](production-manage-manufacturing.md).

A production BOM is the master data that defines a production item and the components that go into it. For assembly items, the production BOM must be certified and assigned to the production item before it can be used in a production order. When you enter the production item on a production order line, either manually or by refreshing the order, then the production BOM content becomes the production order components. Learn more at [Create Production BOMs](production-how-to-create-production-boms.md).

The concept of resources in production is much more advanced than in assembly management. Work centers and machine centers act as resources. The operations assigned to resources in production routings represent production steps. Learn more at the [Create Routings](production-how-to-create-routings.md) article.

Both assembly orders and production orders might be linked directly to sales orders. However, you can only use assembly orders to customize the end item directly for a customer request with the sales order.

## Related information

[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)    
[Create Production BOMs](production-how-to-create-production-boms.md)    
[Register New Items](inventory-how-register-new-items.md)    
[Manage Product Variants](inventory-item-variants.md)    
[Inventory](inventory-manage-inventory.md)    
[Manufacturing](production-manage-manufacturing.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
