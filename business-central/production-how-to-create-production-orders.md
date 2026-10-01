---
title: Create production orders
description: Learn how to manually create a firm planned production order that brings together items, quantities, dates, components, operations, and capacity.
author: brentholtorf
ms.topic: how-to
ms.search.form: 9325, 99000815, 99000829, 9900083
ms.date: 09/04/2026
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

## Create a production order by copying lines

Instead of entering the source and lines manually, you can create a production order and copy lines from an existing order.

1. Open the **Simulated Production Orders**, **Planned Production Orders**, **Firm Planned Production Orders**, or **Released Production Orders** page, depending on the status of the order that you want to create.
2. Select the **New** action, and then fill in the **No.** field.
3. Select the **Copy Prod. Order Document** action.
4. In the **Status** field, enter the status of the production order that you want to copy from.
5. In the **Document No.** field, select the source production order.
6. Turn on **Include Header** to copy selected values from the source order header, and then select **OK**.

The action copies production order lines, including their production BOM and routing references. It doesn't copy component or routing-operation records. To generate those records from the references on the copied lines, select the **Refresh Production Order** action. On the request page, turn off **Lines** so that the copied lines aren't replaced, and leave **Routings** and **Component Need** turned on.

If the destination order already has lines, the copied lines are added after them.

## Related information

[Manufacturing](production-manage-manufacturing.md)
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
