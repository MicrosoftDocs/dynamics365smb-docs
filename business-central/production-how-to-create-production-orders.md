---
title: Create production orders
description: You can create a production order manually, and the first step is to create a production order header.
author: brentholtorf
ms.topic: conceptual
ms.search.form: 9325, 99000815, 99000829, 9900083
ms.date: 02/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Create production orders

Typically, businesses use the planning engine to create production orders automatically to fulfill a known demand. To learn more, go to [Planning](production-planning.md). However, you can create a production order manually. This article describes how to create a firm planned production order. You can also create production orders with a different status.  

## To create a production order header

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Orders**, and then choose the related link.  
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