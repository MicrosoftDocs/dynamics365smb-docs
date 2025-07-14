---
title: Use the manufacturing batch units of measure
description: This article gives an overview of how to work with manufacturing batch units of measure in Business Central. 
author: brentholtorf
ms.topic: how-to
ms.search.keywords:
ms.date: 07/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Work with manufacturing batch units of measure

If an item is stocked in one unit of measure but produced in another, a production order is created that uses a manufacturing batch unit of measure to calculate the correct quantity of the components when you run the **Refresh Production Order** batch job. An example of a manufacturing batch unit of measure calculation is when a manufactured item is stocked in pieces but produced in tons.  

## To create a production BOM using a batch unit of measure

1. The manufacturing batch unit of measure is set up as an alternative unit of measure on the **Item Units of Measure** page on the item to be produced. The batch unit of measure doesn't replace the base unit of measure on the item.  
2. Create a production BOM for the item set up with the manufacturing batch unit of measure. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).  
3. In the **Unit of Measure Code** field, select the manufacturing batch unit of measure.  
4. For each production BOM line, in the **Quantity Per** field, enter the quantity of this component item that is required to create this batch unit of measure.
5. Change status of production BOM to **Certified**.

## To calculate a manufacturing batch unit of measure on a production order

Because production order headers don't allow you to specify a unit of measure, specify it in production order line.

1. Create a production order header using an item that has a manufacturing batch unit of measure.  
2. In the **Item No.** field in the production order line, type the same item number used in the header.  
3. In the **Quantity** field, enter the same quantity used in the header.  
4. In the **Unit of Measure Code** field, select the manufacturing batch unit of measure code.  
5. Choose the **Refresh** action.
6. On the **Calculate** FastTab, clear the **Lines** checkbox.  
7. Choose the **OK** button.  
8. On the **Lines** FastTab, choose the **Line** action, and then choose the **Components** action to view the result. The correct quantity of the components needed to satisfy the production BOM is calculated based on the manufacturing batch unit of measure.  

## Related information

[Create Routings](production-how-to-create-routings.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
