---
title: Understanding Assemble to Order and Assemble to Stock
description: Learn about assembling items for sales orders or to keep in stock for future sales.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.service: dynamics-365-business-central
---
# Understanding Assemble to Order and Assemble to Stock

[!INCLUDE [prod_short](includes/prod_short.md)] lets you supply assembly items in the following ways:

* Assemble to order  
* Assemble to stock  

## Assemble to order

Use the assemble-to-order process for items that you don't want to stock. For example, for the following reasons:

* You'll customize the items for customer requirements.
* You want to minimize the cost of on-hand inventory.

The following list describes some of the benefits of the assemble-to-order process:  

* Customize assembly items when taking a sales order.  
* Overview availability of the assembly item and its components.  
* Reserve assembly components immediately to guarantee order fulfillment.  
* Determine the profitability of the customized order by rolling up price and cost.  
* Integrated with the warehouse to make assembly and shipping easier.  
* Assemble to order when you create a sales quote or a blanket sales order.  
* Combine inventory quantities with assemble-to-order quantities.  

In the assemble-to-order process, you assemble items for a sales order. There's a one-to-one link between the assembly order and the sales order.  

When you enter an assemble-to-order item on a sales order line, an assembly order is automatically created. The assembly order is based on the sales line, and its lines are based on the item's assembly BOM. The quantity of components on the assembly BOM is multiplied by the order quantity. The **Assemble-to-Order Lines** page shows details about the linked assembly order lines. The details can help you customize the assembly item. The delivery date is based on the availability of components. To learn more about assembling items for sales orders, go to [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

> [!NOTE]  
> Although it isn't part of the default process, you can sell inventory quantities and assemble-to-order quantities on the same sales order. To learn more about combining stock and assemble-to-order items, go to [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

To specify that an item is assembled-to-order, in the **Assembly Policy** field on the **Item Card** page for the item, choose **Assemble-to-Order**.  

## Assemble to stock

Use the assemble-to-stock process for items that you assemble and store for future sales. Assemble-to-stock items are standard items, such as packaged kits, that you don't customize. You can also consume these items as subassembly components. The items are picked and processed as single items and are treated as finished production items. To learn more about assembly items, go to [Assemble Items](assembly-how-to-assemble-items.md).  

When you specify an assemble-to-stock item on a sales line, the item is treated like any other item sold from inventory. For example, [!INCLUDE [prod_short](includes/prod_short.md)] checks availability only for the assembled item only, and not its components.  

> [!NOTE]  
> Although it isn't part of the default process, you can assemble an item to order even if the item is set up to be assembled to stock. Learn more at [Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

To specify that an item is assembled-to-stock, in the **Assembly Policy** field on the **Item Card** page for the item, choose **Assemble-to-Stock**.  

## Combination scenarios

When assemble-to-order and inventory quantities are combined on a sales order, assemble-to-order quantities must be shipped first.  

If an assembly order is linked to a sales order line, the value in the **Qty. to Assemble to Order** field on the sales order line is copied to the **Quantity to Assemble** field via the **Quantity** field on the assembly order. Learn more at [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

The value in the **Quantity to Assemble** field is related to the **Qty. to Ship** field on the sales order line. This relation manages how you ship partial and complete assemble-to-order quantities:

* When the full quantity on the sales order line is assembled to order
* In combination scenarios where part of the quantity is assembled to order and part is shipped from inventory.

The combination scenario allows flexibility for partial shipments. You can use the **Quantity to Assemble** field to specify the quantity to ship partially from inventory and by assembling to order.  

If the full sales line quantity must be assembled to order and shipped, the value in the **Qty. to Ship** field is copied to the **Quantity to Assemble** field on the linked assembly order when you change the quantity to ship. This update ensures that the quantity being shipped is fully supplied by the assemble-to-order quantity.  

However, in combination scenarios, the full value in the **Qty. to Ship** is not copied to the **Quantity to Assemble** field on the assembly order. Instead, a default value is inserted in the **Quantity to Assemble** field. The value is calculated from the **Qty. to Ship** field to ensure the assemble-to-order quantities ship first.

To deviate from the default, for example because you only want to assemble more or less of the quantity in the **Qty. to Ship** field, you can modify the **Quantity to Assemble** field within predefined rules, as illustrated below.  

An example of why you would modify the quantity to assemble is that you want to partially post the shipment of inventory quantities before you ship the assembly output.  

The following tables explain the rules that define the minimum and maximum values that you can enter in the **Quantity to Assemble** field to deviate from the default value in a combination scenario. The table shows a combination scenario where the **Qty. to Ship** field on the linked sales order line is changed from 7 to 4, and the **Quantity to Assemble** is therefore defaulted to 4.  

**Sales Order Line**

|                | **Quantity** | **Qty. to Ship** | **Qty. to Assemble to Order** | **Quantity Shipped** |
|----------------|--------------|------------------|-------------------------------|----------------------|
|**Initial value**| 10          | 7                | 7                             | 0                    |
|**Change**      |              | 4                |                               |                      |

**Assembly Order Header**

|                | **Quantity** | **Qty. to Ship** | **Qty. to Assemble to Order** | **Quantity Shipped** |
|----------------|--------------|------------------|-------------------------------|----------------------|
|**Initial value**| 7           | 7                | 0                             | 7                    |
|**Change**      |              | 4 (inserted by default)|                         |                      |

Based on this example, you can modify the **Quantity to Assemble** field as follows:  

* The minimum quantity you can enter is 1. You must assemble at least one unit to be able to sell the four units, assuming that the remaining three are available in inventory.  
* The maximum quantity that you can enter is 4. This limit ensures that you don't assemble more of the item than you need for the sale.  

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
