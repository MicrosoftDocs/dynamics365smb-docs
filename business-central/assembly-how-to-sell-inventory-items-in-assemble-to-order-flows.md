---
    title: How to Sell Inventory Items in Assemble-to-Order Flows | Microsoft Docs
    description: If the item is set up for card of assemble-to-order, then the default sales order process assumes that the item is not in inventory and must be assembled for that specific sales order. Therefore, a linked assembly order is automatically created when you add the item to a sales order line.
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
# Sell Inventory Items in Assemble-to-Order Flows
If the **Assembly Policy** field on the item card of an assembly item contains **Assemble-to-Order**, then the default sales order process assumes that the item is not in inventory and must be assembled for that specific sales order. Therefore, a linked assembly order is automatically created when you add the item to a sales order line. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md). However, if a part of the sales order quantity is already available in inventory, then you can decrease the assembly order quantity by changing the **Qty. to Assemble to Order** field on the sales order line.  

This scenario is rare because assemble-to-order items are expected to always be customized, and the chance that they are in inventory in the configuration that is requested by another customer is low. However, if a company does have assemble-to-order quantities in inventory because of returns or order cancellations, then these quantities should be picked and sold before new ones are assembled.  

> [!NOTE]  
>  No functionality exists on sales orders that automatically alerts or helps you deduct assembly order quantities that are already available. Instead, you must monitor availability information, such as in the **Sales Line Details** FactBox.  

Similar functionality is available when you are selling assembly items from inventory and a part or all of the quantity is unavailable and can be supplied by an assembly order. For more information, see [Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

> [!NOTE]  
>  Certain rules apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble-to-order quantities and inventory quantities. For more information, see the Combination Scenarios section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).  

In this procedure, you replace assemble-to-order quantities with inventory quantities on a sales order line. The steps include detecting that availability exists, deducting that quantity from the linked assembly order, and then reserving the inventory quantity to make sure that it is picked and shipped for the order.  

## To sell inventory items in assemble-to-order flows  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Create a sales order. For more information, see [Sell Products](sales-how-sell-products.md).  
3.  On a sales order line for an assemble-to-order item, in the **Quantity** field, enter the demanded quantity.  
4.  In the **Sales Line Details** FactBox, determine if all or some of the demanded quantity is available.  
5.  In the **Qty. to Assemble to Order** field, deduct the available quantity so that only the unavailable quantity is assembled to the order. The **Reserved Quantity** field is decreased accordingly to reflect that the order-to-order link, or reservation, only applies to the quantity to be assembled.  
6.  On the **Lines** FastTab, choose **Functions**, and then choose the **Reserve** action.  
7.  On the **Reservation** page, select the item ledger entry line or lines that contain the available quantities, choose the **Reserve from Current Line** action, and then choose the **OK** button.  

    On the **Sales Order** page, the **Reserved Quantity** field now shows that the whole order line quantity is reserved. The **Qty. to Assemble to Order** field still reflects the subquantity that has to be assembled.  

8.  Release the sales order for picking of the inventory items and for assembly of the unavailable items. For more information, see [Assemble Items](assembly-how-to-assemble-items.md).  

> [!CAUTION]  
>  The **Bin Code** field on the sales order may be prefilled according to the **Assemble-to-Order Shpt. Bin Code** or the **From-Assembly Bin Code** field on the location card. In that case, the **Bin Code** field on the sales order line may be incorrect in this combination of assemble-to-order and assemble-to-stock quantities. It is a good idea to look in the **Bin Code** field and ensure that the placement works for all quantities. Alternatively, enter the two different quantities on separate sales order lines.  

## See Also  
[Assembly Management](assembly-assemble-items.md)  
[Reserve Items](inventory-how-to-reserve-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
