---
title: Sell Assemble-to-Order Items and Inventory Items Together
description: If a part of an assemble-to-stock item isn't available, you can create an assembly order for the remaining quantity.
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
# Sell Assemble-to-Order Items and Inventory Items Together

If the **Assembly Policy** field on the item card of an assembly item contains **Assemble-to-Stock**, the sales order process assumes that the item is already assembled and can be picked from inventory if it's available. Therefore, an assembly order isn't automatically created and linked to the sales order line. However, if some or all of the quantity isn't available, you can create an assembly order for the remaining quantity. To do that, fill in the **Qty. to Assemble to Order** field on the sales order line. This setting lets you assemble the item to order although it's set up to be assembled to stock.  

You have similar flexibility when you sell assemble-to-order items and some of the quantity is already in inventory. You'll want to deduct that quantity from the assembly order. To learn more about selling inventory items, go to [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

> [!NOTE]  
> There are rules that apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble-to-order quantities and inventory quantities. To learn more about the rules, go to [Combination scenarios](assembly-assemble-to-order-or-assemble-to-stock.md#combination-scenarios).  

> [!NOTE]  
> The following procedure doesn't include the sales order steps that you need to follow before you create an assembly order for unavailable quantities.

## To sell assemble-to-order items and inventory items together

1. On a sales order line for an assemble-to-stock item, enter a quantity in the **Quantity** field that exceeds inventory. The **Check Availability** page appears. To learn more about item availability, go to [View the Availability of Items](inventory-how-availability-overview.md).
2. In the **Qty. to Assemble to Order** field, enter the value from the **Total Quantity** field.  
3. Make any changes needed to the assembly components. Learn more at [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  
4. Release the sales order to make the items available for picking and for assembly of the unavailable items. To learn more about the standard assembly steps, go to [Assemble Items](assembly-how-to-assemble-items.md).  

> [!CAUTION]  
> The **Bin Code** field on the sales order might contain the value from the **Assemble-to-Order Shpt. Bin Code** or **From-Assembly Bin Code** fields on the location card. If it is, the **Bin Code** field on the sales order line might be incorrect for this combination of assemble-to-order and assemble-to-stock quantities. It's a good idea to double-check that the bin in the **Bin Code** field works for all quantities. Alternatively, enter the two different quantities on separate sales order lines.  

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]