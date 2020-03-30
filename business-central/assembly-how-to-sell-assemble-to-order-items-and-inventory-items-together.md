---
    title: Sell Assemble-to-Order Items and Inventory Items Together | Microsoft Docs
    description: If an assembly item is set up for assemble-to-stock, then the default sales order process assumes that the item is already assembled and can be picked from inventory, if it is available. But if a part (or all) of the quantity is not available, then you have the flexibility to create an assembly order for the remaining quantity on the fly.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: kit, kitting
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Sell Assemble-to-Order Items and Inventory Items Together
If the **Assembly Policy** field on the item card of an assembly item contains **Assemble-to-Stock**, then the default sales order process assumes that the item is already assembled and can be picked from inventory, if it is available. Therefore, no assembly order is automatically created and linked to the sales order line. However, if a part (or all) of the quantity is not available, then you have the flexibility to create an assembly order for the remaining quantity by filling in the **Qty. to Assemble to Order** field on the sales order line. In this manner, you can assemble the item to order although it is set up to be assembled to stock by default.  

Similar flexibility exists when you are selling items to be assembled to the order and a part of the quantity is in inventory, which you want to deduct from the assembly order. For more information, see [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

> [!NOTE]  
>  Certain rules apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble-to-order quantities and inventory quantities. For more information, see the Combination Scenarios section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).  

> [!NOTE]  
>  The following procedure does not include the standard sales order steps that you need to follow before you create an assembly order for unavailable quantities.

## To sell assemble-to-order items and inventory items together  
1.  On a sales order line for an item that is set up to be assembled to stock, enter a quantity in the **Quantity** field that exceeds inventory. The **Check Availability** page appears. For more information, see [View the Availability of Items](inventory-how-availability-overview.md).
2.  Note the **Total Quantity** field (a negative value), which you will enter in the next step.  
3.  In the **Qty. to Assemble to Order** field, enter the value from the previous step.  
4.  Perform any changes to the assembly components. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  
5.  Proceed to release the sales order, to prepare it for picking of the inventory items and for assembly of the unavailable items. For more information about these standard assembly steps, see [Assemble Items](assembly-how-to-assemble-items.md).  

> [!CAUTION]  
>  The **Bin Code** field on the sales order may be prefilled according to the **Assemble-to-Order Shpt. Bin Code** field or the **From-Assembly Bin Code** field on the location card. In that case, the **Bin Code** field on the sales order line may be incorrect in this combination of assemble-to-order and assemble-to-stock quantities. It is a good idea to examine the **Bin Code** field and make sure that the placement works for all quantities. Alternatively, enter the two different quantities on separate sales order lines.  

## See Also  
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
