---
title: Sell Inventory Items in Assemble-to-Order Flows
description: Assemble-to-order items are assembled for sales orders through an assembly order.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.service: dynamics-365-business-central
---
# Selling Inventory Items in Assemble-to-Order Flows

If the **Assembly Policy** field on the item card of an assembly item contains **Assemble-to-Order**, the sales order process assumes that the item isn't in inventory and must be assembled for sales orders. When you add the item to a line on a sales order, [!INCLUDE [prod_short](includes/prod_short.md)] creates an assembly order that's linked to the sales order. To learn more about how to sell assemble-to-order items, go to [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md). However, if some of the sales order quantity is already available in inventory, you can decrease the assembly order quantity by changing the **Qty. to Assemble to Order** field on the sales order line.  

It's relatively rare for businesses to sell inventory items as assemble-to-order items. Assemble-to-order items typically aren't standard. They're customized to meet specific customer requirements. However, you might have quantities of assemble-to-order items in inventory due to returns or order cancellations. Those quantities should be picked and sold before new ones are assembled.  

> [!NOTE]  
> To check whether whether assemble-to-order items are already available for assembly orders, use the **Sales Line Details** FactBox on the sales order.  

You can do similar things when you're selling assembly items from inventory and some or all of the quantity isn't available. You can supply the missing quantity through an assembly order. To learn more about selling inventory and assembly items, go to [Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

> [!NOTE]  
> There are rules that apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble-to-order quantities and inventory quantities. To learn more about the rules, go to [Combination scenarios](assembly-assemble-to-order-or-assemble-to-stock.md#combination-scenarios).  

In this procedure, you replace assemble-to-order quantities with inventory quantities on a sales order line. The following steps provide an overview:

1. Determine availability.
2. Reducing that quantity from the linked assembly order.
3. Reserve the inventory quantity to make sure that it's picked and shipped for the order.  

## To sell inventory items in assemble-to-order flows

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.  
2. Create a sales order. To learn about creating sales orders, go to [Sell Products](sales-how-sell-products.md).  
3. On a sales order line that contains an assemble-to-order item, in the **Quantity** field, enter the quantity.  
4. In the **Sales Line Details** FactBox, determine whether some of all of the quantity is available.  
5. In the **Qty. to Assemble to Order** field, deduct the available quantity so that only the unavailable quantity is assembled to the order. The **Reserved Quantity** field is decreased accordingly to reflect that the order-to-order link, or reservation, only applies to the quantity to be assembled.  
6. On the **Lines** FastTab, choose **Functions**, and then choose the **Reserve** action.  
7. On the **Reservation** page, select the item ledger entry line or lines that contain the available quantities, choose the **Reserve from Current Line** action, and then choose the **OK** button.  

    On the **Sales Order** page, the **Reserved Quantity** field now shows that the full quantity for the order line is reserved. The **Qty. to Assemble to Order** field still reflects the quantity to assemble.  

8. Release the sales order to make the items available for picking and for assembly of the unavailable items. To learn more about assembling items, go to [Assemble Items](assembly-how-to-assemble-items.md).  

> [!CAUTION]  
> The **Bin Code** field on the sales order might contain the value from the **Assemble-to-Order Shpt. Bin Code** or **From-Assembly Bin Code** fields on the location card. If it does, the **Bin Code** field on the sales order line might be incorrect for this combination of assemble-to-order and assemble-to-stock quantities. It's a good idea to double-check that the bin in the **Bin Code** field works for all quantities. Alternatively, enter the two different quantities on separate sales order lines.  

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Reserve Items](inventory-how-to-reserve-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
