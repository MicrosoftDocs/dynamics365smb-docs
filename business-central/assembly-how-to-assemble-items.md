---
title: Assemble Items
description: Learn about assemble-to-order and assemble-to-stock processes in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 11/23/2022
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.custom: bap-template
---
# Assemble Items

If the **Replenishment System** field on the item card contains **Assembly**, the default method of supplying the item is to assemble it according to an assembly BOM, and potentially by a specific resource. Learn more at [Work with Assembly BOMs](assembly-how-work-assembly-boms.md). Learn more about how to set up an assembly item at [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).

You can set up assembly items for two assembly processes.

|Process  |Description  |
|---------|---------|
|Assemble to stock     | Items that you assemble and stock for future sales. For example, kits for an upcoming sales campaign. The items aren't related to a sales order, at least not yet. Typically, these items aren't customized for customer requests.        |
|Assemble to order     | Items that you don't want to stock. For example, because they're customized based on customer orders or to reduce the cost of on-hand inventory. |
  
This article describes the standard settings for assemble to stock. There might be other ways that are more suited for your business though. Learn more at [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md) and [Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).

> [!NOTE]  
> Assembly components are handled in a special way in basic warehouse configurations. Learn more at [Handling Assemble-to-Order Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

## To assemble an item to stock

Follow the steps in this procedure to assemble an item to stock. To learn about assemble to order, go to [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Assembly Orders**, and then choose the related link.  
2. Choose the **New** action. The **New Assembly Order** page opens.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. In the **Item No.** field, select the item that you want to assemble. You can select items that are set up for assembly and have an assembly BOM, or items without an assembly BOM. The latter is useful for unplanned assemblies or scenarios when you want to use item reclassification and track costs.  
5. In the **Quantity** field, enter how many units of the item that you want assembled.  

    > [!NOTE]  
    >  If one or more components are not available to fulfill quantity on the due date, the **Assembly Availability** page opens. The page shows how many assembly items can be assembled based on component availability. Learn more at [View the Availability of Items](inventory-how-availability-overview.md). When you close the page, the assembly order is created with availability alerts on the lines for the affected components.  

    The lines contain the contents of the assembly BOM and the specified quantities.  

    > [!NOTE]  
    >  If the **Assembly Availability** page opened when you filled in the assembly order header, each affected assembly order line contains a **Yes** in the **Avail. Warning** field with a link to detailed availability information. <!--check whether this field help is useful For more information, see Check Availability.--> You can resolve a component availability issue by:

    > * Postponing the starting date.
    > * Replacing the component with another item.
    > * Selecting an available substitution if one is defined.  

6. In the **Quantity to Assemble** field, enter how many units of the assembly item that you want to post as output the next time you post the assembly order. This quantity can be lower than the value in the **Quantity** field to reflect a partial output posting.  

    > [!NOTE]  
    >  To make sure that component consumption posting matches the assembly item output posting, the quantity fields in the assembly order lines automatically adjust to the value that you enter in the **Quantity to Assemble** field.  
7. On assembly order lines of type **Item** or **Resource**, in the **Quantity to Consume** field, specify how many units you want to post as consumed the next time that you post the assembly order.
8. When you are ready to partially or fully post, choose the **Post** action.  

    > [!NOTE]  
    >  If warnings are still present in the assembly order lines, you can't post the order. A message displays the component or components that are not in inventory.  

After posting succeeds, the assembly item is posted as output to the location code and potential bin code that are defined on the assembly order. For manually created assembly orders, the location may be copied from the **Default Location for Orders** setup field. For assemble-to-order flows, the location code may be copied from the sales order line.  

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
