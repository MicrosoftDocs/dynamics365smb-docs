---
    title: Understanding Assemble to Order and Assemble to Stock | Microsoft Docs
    description: Assembly items can be supplied either by assembling them when they are ordered or by assembling them to be kept in inventory until they are need on a sales order.
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
# Understanding Assemble to Order and Assemble to Stock
Assembly items can be supplied in the following two processes:  

-   Assemble to order.  
-   Assemble to stock.  

## Assemble to Order  
You typically use *assemble to order* for items that you do not want to stock because you expect to customize them to customer requests or because you want to minimize the inventory carrying cost. The supporting functionality includes:  

-   Ability to customize assembly items when taking a sales order.  
-   Overview of availability of the assembly item and its components.  
-   Ability to reserve assembly components immediately to guarantee order fulfillment.  
-   Function to determine profitability of the customized order by rolling up price and cost.  
-   Integration to the warehouse to make assembly and shipping easier.  
-   Ability to assemble to order at the point of making a sales quote or a blanket sales order.  
-   Ability to combine inventory quantities with assemble-to-order quantities.  

In the assemble-to-order process, the item is assembled in response to a sales order and with a one-to-one link between the assembly order and the sales order.  

When you enter an assemble-to-order item on a sales line, an assembly order is automatically created with a header that is based on the sales line and with lines that are based on the item’s assembly BOM multiplied by the order quantity. You can use the **Assemble-to-Order Lines** page to see the linked assembly order lines to support you in customizing the assembly item and in a delivery date that is based on component availability information. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

> [!NOTE]  
>  Although it is not part of the default process, you can sell inventory quantities with the assemble-to-order quantities. For more information, see [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

 To enable this process, the **Assembly Policy** field on the item card must be **Assemble-to-Order**.  

## Assemble to Stock  
 You typically use *assemble to stock* for items that you want to assemble ahead of sales, such as to prepare for a kit campaign, and keep in stock until they are ordered. These items are usually standard items such as packaged kits that you do not offer to customize to customer requests.  

 In the assemble-to-stock process, the item is assembled without an immediate sales demand and is stocked in the warehouse as an inventory item for later sale or consumption as a subassembly. For more information, see [Assemble Items](assembly-how-to-assemble-items.md). From this point, the item is picked and processed as a single item and is treated like a finished production item.  

 When you enter an assemble-to-stock item on a sales line, the line like any other item sold from inventory. For example, availability is checked for the assembly item only.  

> [!NOTE]  
>  Although it is not part of the default process, you can assemble an item to order even if it is set up to be assembled to stock. For more information, see [Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

 To enable this process, the **Assembly Policy** field on the item card must be **Assemble-to-Stock**.  

## Combination Scenarios  
 A general principle in Assembly Management is that when combined on a sales order line, assemble-to-order quantities must be shipped before inventory quantities.  

 If an assembly order is linked to a sales order line, then the value in the **Qty. to Assemble to Order** field on the sales order line is copied to the **Quantity to Assemble** field, via the **Quantity** field on the assembly order header. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

 In addition, the value in the **Quantity to Assemble** field is related to the **Qty. to Ship** field on the sales order line, and this relation manages the shipping of assemble-to-order quantities, both partially and completely. This is true both when the full sales line quantity is assembled to order and in combination scenarios where one part of the sales line quantity is assembled to order and another part is shipped from inventory. However, in the combination scenario, you have additional flexibility when shipping partially in that you can modify the **Quantity to Assemble** field, within predefined rules, to specify how many units to ship partially from inventory and how many to ship partially by assembling to order.  

 If the full sales line quantity must be assembled to order and shipped, then the value in the **Qty. to Ship** field is copied to **Quantity to Assemble** field on the linked assembly order when you change the quantity to ship. This ensures that the quantity being shipped is fully supplied by the assemble-to-order quantity.  

 However, in combination scenarios, the full value in the **Qty. to Ship** is not copied to the **Quantity to Assemble** field on the assembly order header. Instead, a default value is inserted in the **Quantity to Assemble** field that is calculated from the **Qty. to Ship** field according to a predefined rule that ensures shipment of assemble-to-order quantities first.  

 If you want to deviate from this default, for example because you only want to assemble more or less of the quantity in the **Qty. to Ship** field, then you can modify the **Quantity to Assemble** field, but only within predefined rules, as illustrated below  

 An example why you would want to modify the quantity to assemble is that you want to partially post shipment of inventory quantities before the assembly output can be shipped.  

 The following explains the rules that define the minimum and maximum values that you can enter manually in the **Quantity to Assemble** to deviate from the default value in a combination scenario. The table shows a combination scenario where the **Qty. to Ship** field on the linked sales order line is changed from 7 to 4, and the **Quantity to Assemble** is therefore defaulted to 4.  

||Sales Order Line|Assembly Order Hheader|  
|-|----------------------|---------------------------|  
||**Quantity**|**Qty. to Ship**|**Qty. to Assemble to Order**|**Quantity Shipped**|**Quantity**|**Quantity to Assemble**|**Assembled Quantity**|**Remaining Quantity**|  
|Initial|10|7|7|0|7|7|0|7|  
|Change||4||||4 (inserted by default)|||  

 Based on the above situation, you can only modify the **Quantity to Assemble** field as follows:  

-   The minimum quantity that you can enter is 1. This is because you must at least assemble one unit to be able to sell the four units, assuming that the remaining three are available in the inventory.  
-   The maximum quantity that you can enter is 4. This is to ensure that you do not assemble more of this assemble-to-order item than what is needed on the sale.  

## See Also  
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
