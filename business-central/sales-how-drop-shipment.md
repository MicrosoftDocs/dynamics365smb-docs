---
title: Make drop shipments
description: Describes how to create a sales order linked to a purchase order to enable shipment directly from the vendor to the customer.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: direct shipment
ms.date: 05/28/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Make drop shipments

A drop shipment is the shipment of items from one of your vendors directly to one of your customers.

When a sales order is marked for drop shipment, and you create a purchase order specifying the customer in the **Ship-to** field, **Customer Address**, you can link the two documents to instruct the vendor to ship directly to the customer.
<br><br>  
  
> [!Video https://learn-video.azurefd.net/vod/player?id=58c81aa9-7190-476a-9fd9-75a9841549f7]

## To create a sales order for drop shipment

To prepare a drop shipment, you create a sales order for an item and indicate on the sales line that the sale requires drop shipment.

1. Create a sales order for an item. For more information, see [Sell Products](sales-how-sell-products.md).
2. On the sales order line for the drop shipment, select the **Drop Shipment** checkbox. Alternatively, in the **Purchasing Code** field, select a purchasing code that has the **Drop Shipment** field selected.

> [!TIP]
> By default, the Drop Shipment checkbox and Purchasing Code field aren't available on the lines. If they aren't, you can add them by personalizing the section of page that contains the lines. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

## To create the purchase order for drop shipment

To prepare a drop shipment, you indicate on the purchase order that it must be shipped to your customer, not to yourself.

1. Create a purchase order. Don't fill any fields on the lines. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
2. In the **Ship-to** field, select **Customer Address**.
3. In the **Customer** field, select the customer that you're selling to.
4. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
5. On the **Sales List** page, select the sales order that you prepared in [To create a sales order for drop shipment](#to-create-a-sales-order-for-drop-shipment).
6. Choose the **OK** button.

The line information from the sales order is inserted on the purchase order line(s).

You can now tell your vendor to ship the items directly to the customer. For example, you might send them the order by email.

If your vendor provides additional information, such as a tracking number, you can add that information as a comment on a purchase order line. To add a comment on a line, in the **Type** field, choose **Comment**, and then enter the information in the **Description** field.  

## To create multiple purchase orders for drop shipments

You can also use the requisition worksheet to create purchase orders. The advantage of using the requisition worksheet is that it can create purchase orders for all outstanding drop shipments. That means you won't have to create each order individually.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Requisition Worksheets**, and then choose the related link.
2. Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.
3. If needed, enter filter criteria for the orders you wan to get, and then choose the **OK** button.
4. Review the purchase order lines, and in the **Vendor No.** field, select the vendor that supplies the goods.
5. Choose the **Carry Out Action Message** action to convert the lines to a purchase order.

## To view the linked purchase order from the sales order

Select the drop-shipment sales order line, choose the **Order** action, choose the **Drop Shipment** action, and then choose the **Purchase Order** action.

## To post a drop shipment

After the vendor ships the items, you can post the sales order as shipped. You can also post the purchase order, but only with the **Receive** option until the sales order has been invoiced.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Open the sales order that you created in [To create a sales order for drop shipment](#to-create-a-sales-order-for-drop-shipment).
3. In the **Qty. to Ship** field, specify how many of the order quantity to ship, the full or a partial order quantity.
4. Choose the **Post** or **Post and Send** action.
5. Choose either the **Ship** option to invoice later, or the **Ship and Invoice** option to invoice immediately.

> [!TIP]
> Don't forget that you need to post the purchase order invoice.

## Related information

[Create Special Orders](sales-how-to-create-special-orders.md)  
[Purchase Items for a Sale](purchasing-how-purchase-products-sale.md)  
[Sell Products](sales-how-sell-products.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Sales](sales-manage-sales.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
