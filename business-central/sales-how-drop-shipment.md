---
title: Make drop shipments
description: Describes how to create a sales order linked to a purchase order to enable shipment directly from the vendor to the customer.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: direct shipment
ms.date: 03/05/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Make drop shipments

A drop shipment is the shipment of items from one of your vendors directly to one of your customers.

When a sales order is marked for drop shipment, and you create a purchase order specifying the customer in the **Ship-to** field, **Customer Address**, you can link the two documents to instruct the vendor to ship directly to the customer.
<br><br>  
  
> [!Video https://learn-video.azurefd.net/vod/player?id=58c81aa9-7190-476a-9fd9-75a9841549f7]

## Create a sales order for a drop shipment

To prepare a drop shipment, you create a sales order for an item and indicate on the sales line that the sale requires drop shipment.

1. Create a sales order for an item. Learn more at [Sell Products](sales-how-sell-products.md).
2. On the sales order line for the drop shipment, select the **Drop Shipment** checkbox. Alternatively, in the **Purchasing Code** field, select a purchasing code that has the **Drop Shipment** field selected.

> [!TIP]
> By default, the Drop Shipment checkbox and Purchasing Code field aren't available on the lines. If they aren't, you can add them by personalizing the section of page that contains the lines. Learn more at [Personalize Your Workspace](ui-personalization-user.md).

## Create purchase orders directly from sales orders

You can create purchase orders directly from sales orders that are set up for drop shipment by choosing the **Create Purchase Orders** action.

To create a purchase order from a sales order, follow these steps:

1.  Open a sales order that has lines marked as **Drop Shipment**.
2.  Choose the **Create Purchase Orders** action.
3.  On the **Create Purchase Orders** page, review the suggested lines. The vendor is added based on information from the **Item Card** or the **Stockkeeping Unit Card** pages. You can change the vendor if needed.

## Create a purchase order for a drop shipment

1. In the **Ship-to** field, select **Customer Address**.
2. In the **Customer** field, select the customer that you're selling to.
3. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
4. On the **Sales List** page, select the sales order that you prepared in [To create a sales order for drop shipment](#create-a-sales-order-for-a-drop-shipment).
5. Choose the **OK** button.

The line information from the sales order is inserted on the purchase order lines.

You can now tell your vendor to ship the items directly to the customer. For example, you might send them the order by email.

If your vendor provides additional information, such as a tracking number, you can add that information as a comment on a purchase order line. To add a comment on a line, in the **Type** field, choose **Comment**, and then enter the information in the **Description** field.  

## Create multiple purchase orders for drop shipments

You can also use a requisition worksheet or planning worksheet to create purchase orders. The advantage of using a worksheet is that it can create purchase orders for all outstanding drop shipments. You don't have to create each order individually.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Requisition Worksheets** or **Planning Worksheets**, and then choose the related link.
2. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
3. If needed, enter filter criteria for the orders you wan to get, and then choose the **OK** button.
4. Review the purchase order lines, and in the **Vendor No.** field, select the vendor that supplies the goods.
5. Choose the **Carry Out Action Message** action to convert the lines to a purchase order.

## Create purchase orders for drop shipments from the Order Planning page

Drop shipment orders are taken into consideration by the Order Planning page, so drop shipment lines are included when calculating plans.

- On the **Order Planning page**, use the **Calculate Plan** action. Drop shipment lines are included.

To learn more about order planning, go to [Plan for New Demand Order by Order](production-how-to-plan-for-new-demand.md).


## Access the linked purchase order from the sales order

Select the drop-shipment sales order line, choose the **Order** action, choose the **Drop Shipment** action, and then choose the **Purchase Order** action.

## Post a drop shipment

After the vendor ships the items, you can post the sales order as shipped. You can also post the purchase order, but only with the **Receive** option until you invoice the sales order.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.
2. Open the sales order.
3. In the **Qty. to Ship** field, specify how many of the order quantity to ship, the full or a partial order quantity.
4. Choose the **Post** or **Post and Send** action.
5. Choose either the **Ship** option to invoice later, or the **Ship and Invoice** option to invoice immediately. Because the sales order is linked to the purchase, when you post the shipment automatically posts the receipt on the purchase order.

> [!TIP]
> You can also start the process from purchase side. You can either post the receipt, receive and invoice, or use the **Get order lines** action in a separate invoice to post the invoice and shipment.

## Reverse a drop shipment

You can reverse posted drop shipments when both the sales shipment and the related purchase receipt aren't yet invoiced. You can undo a sales shipment that originates from a drop shipment. [!INCLUDE [prod_short](includes/prod_short.md)] reverts the linked purchase receipt, creates correction entries, and reapplies the purchase and sales entries to their reversal entries.

To reverse a drop shipment, open a posted sales shipment for it, and choose **Undo Shipment**.

## Related information

[Create Special Orders](sales-how-to-create-special-orders.md)  
[Purchase Items for a Sale](purchasing-how-purchase-products-sale.md)  
[Sell Products](sales-how-sell-products.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Sales](sales-manage-sales.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
