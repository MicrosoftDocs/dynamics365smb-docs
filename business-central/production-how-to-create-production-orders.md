---
title: Create production orders
description: Learn how to manually create a firm planned production order that brings together items, quantities, dates, components, operations, and capacity.
author: brentholtorf
ms.topic: how-to
ms.search.form: 9325, 99000815, 99000829, 9900083
ms.date: 07/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Create production orders

Production orders specify which items to produce, in what quantities, and by which dates. They bring together the item's production BOM, routing, components, operations, and capacity requirements. Planning can create production orders automatically from demand, or you can create them manually for a specific production need. This article explains how to create a firm planned production order manually. To learn more about automatic creation, go to [Planning](production-planning.md).

## To create a production order header

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Firm Planned Prod. Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **No.** field, add the next number in the number series you use for production orders.  
4. In the **Source Type** field, select the source of the production order:

   - **Item**: Standard items that you produce for inventory.
   - **Family**: A predefined family of items that you produce for inventory. To learn more, go to [Work With Production Families](production-how-work-family.md).
   - Sales header: Items are produced for the sales order that you specify in the **Source No.** field.
5. In the **Source No.** field, select the item number, family, or sales header for which to create the production order.  
6. Fill in the **Quantity** and **Due Date** fields according to your specifications.  
7. On the **Lines** FastTab, in the **Item No.** field, specify the item to produce.
8. In the **Due Date** field, specify when the item is needed. For example, for a sales order.

> [!NOTE]
> The **Starting Date-Time** and **Ending Date-Time** fields are automatically filled in based on the item's routing and the value that you enter in the **Due Date** field.

9. In the **Quantity** field, specify how many units to produce on the line.

When production requirements change, such as components or operations, you can quickly replan the production order. To learn more, go to [Replan or Refresh Production Orders Directly](production-how-to-replan-refresh-production-orders.md).  

## Related information

[Manufacturing](production-manage-manufacturing.md)
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
