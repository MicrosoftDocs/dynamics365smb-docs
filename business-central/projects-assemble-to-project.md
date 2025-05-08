---
title: Assemble to Project
description: Learn how to use assemble-to-order for project.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: project management, task
ms.search.form: 88, 275, 276, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1020
ms.date: 08/03/2022
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Assemble to project

Assemble to project helps you improve inventory management by assembling to order only when it's required.

When you choose an assemble-to-order item on a project planning line, [!INCLUDE [prod_short](includes/prod_short.md)] creates an assembly order. The assembly order is based on the project planning line, and its lines are based on the item's assembly bill of materials (BOM). To learn more about assembly BOMs, go to [Work with Assembly BOMs](assembly-how-work-assembly-boms.md). The quantity of components on the assembly BOM is multiplied by the order quantity. The **Assemble-to-Order Lines** page shows details about the linked assembly order lines. The details can help you customize the assembly item. As in sales, you can't directly post linked assembly orders. To learn more about assembly orders, go to [Selling Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).

Assembly orders are reserved for projects, and [!INCLUDE [prod_short](includes/prod_short.md)] synchronizes item tracking between project planning lines and assembly order.

## Integrate with warehouse management

Assemble to project integrates with warehouse management features to make assembly and shipping easier. The process also helps ensure that the flow from project assembly to delivery runs smoothly in internal warehouse processes. To learn more about internal warehouse flows for projects, go to [Flows for Production, Assembly, and Jobs](design-details-internal-warehouse-flows.md#flows-to-and-from-assembly-in-a-basic-warehouse-configuration).

The following table describes the warehouse configurations that assemble to order supports.

|Configuration  |Description  |
|---------|---------|
|**No warehouse handling**|Use a project journal to post full or partial usage. The output and consumption of components post automatically for the assembly order.         |
|**Inventory pick**|Use an inventory pick to post full or partial usage. The output and consumption of components post automatically for the assembly order.          |
|**Warehouse pick**|Create and register warehouse picks for components, and then use a project journal to post usage. [!INCLUDE [prod_short](includes/prod_short.md)] verifies whether the consumed assembly components were picked. The output and consumption of components post automatically for the assembly order.         |

## Known limitations

This section describes known limitations for assemble to project.

* The **Quantity to Assemble to Order** field isn't available for projects that are closed.
* For warehouse pick scenarios, the **Quantity to Assemble to Order** can be either zero or equal to the quantity. You can't mix assemble to order and assemble to stock on a project planning line. You must create separate project planning lines.
* Assemble to order doesn't affect billable parts of a project. An assembly is included on sales invoices, but not its components. You can't edit the **Quantity to Assemble to Order** field for billable lines.
* Order planning and the planning worksheet aren't affected because the project is the input for planning. The planning engine considers the assembly as demand.
* You can't enter a negative quantity in the **Quantity to Assemble to Order** field.
* You can't undo an assembly.

## Related information

[Project Management](projects-manage-projects.md)  
[Assembly Management](assembly-assemble-items.md)  
[Create Jobs](projects-how-create-jobs.md)
