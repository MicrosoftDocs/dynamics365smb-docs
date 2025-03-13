---
title: Create a customer sales order and sell products
description: Describes how to create a sales order to record your agreement with a customer to sell or trade products under specific terms.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: trade, partial deliveries, customer sales order, shipping advice, partial shipments, 
ms.search.form: 42, 48, 9305
ms.date: 03/12/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Sell products with a customer sales order

This article provides guidance on when you should use a customer sales order in addition to an invoice. If your sales process requires you to only ship part of an order, perhaps because the full quantity isn't available right away, you must process that sale by making a sales order.

You must also use sales orders if you sell items that deliver directly from your vendor to your customer, in what is called a drop shipment. To learn more, go to [Make Drop Shipments](sales-how-drop-shipment.md). In all other respects, sales orders work the same way as sales invoices. To learn more, go to [Invoice Sales](sales-how-invoice-sales.md).

When you deliver the products, either fully or partially, you post the sales order as shipped or as shipped and invoiced to create the related item and customer ledger entries in your system. When you post the sales order, you can also email it as a PDF attachment. You can prefill the email body with a summary of the order and payment information, such as a link to PayPal. To learn more, go to [Ship Items](warehouse-how-ship-items.md) and [Send Documents by Email](ui-how-send-documents-email.md).

In business environments where the customer pays immediately, such as via PayPal or cash, [!INCLUDE [prod_short](includes/prod_short.md)] records the payment when you post the sales invoice. The posted sales invoice is closed as fully applied. You select the method in the **Payment Method Code** field on the sales order. For electronic payments, such as PayPal, you must also fill in the **Payment Service** field. To learn more, go to [Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md).

You can even create directly paid orders for unregistered customers by first setting up a "cash customer" card, which you point to on the sales order. To learn more, go to [Set Up Cash Customers](finance-how-to-set-up-cash-customers.md).

## Create a sales order

> [!NOTE]  
> The following procedure assumes that the customer is already set up. To learn more about setting up customers, go to [Register New Customers](sales-how-register-new-customers.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, then choose the related link.
2. Select **New** to create a new entry.
3. In the **Customer Name** field, enter the name of an existing customer.

    Other fields on the **Sales Order** page are now filled in with information about the selected customer.  

4. Fill in the remaining fields on the **Sales Order** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > If you allow the customer to pay immediately, for example, by credit card or PayPal, then fill in the **Payment Method Code** field. The payment is then recorded as soon as you post the sales order as invoiced. If you select *cash*, then the payment is recorded in a specified balancing account.

    You're now ready to fill in the sales order lines with inventory items or services you want the customer to purchase.

    If you set up recurring sales lines for the customer, such as a monthly replenishment order, you can insert these lines on the order by choosing the **Get Recurring Sales Lines** action.
5. On the **Lines** FastTab, in the **Type** field, select what type of product, charge, transaction, or comment you post to the customer on the sales line.

6. In the **No.** field, enter the number of an inventory item or service.

    Leave the **No.** field empty if the line is for a:

    * Comment. Write the comment in the **Description** field.
    * Catalog item. Choose the **Select Catalog Items** action. To learn more about catalog items, go to To learn more, go to [Work With Catalog Items](inventory-how-work-nonstock-items.md).
7. In the **Quantity** field, enter the number of items to be sold.

    > [!NOTE]  
    > For items of the *Resource* or *Service* type, the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line. To learn more, go to [Set Up Item Units of Measure](inventory-how-setup-units-of-measure.md).

    The **Line Amount** field is updated to show the value in the **Unit Price** field multiplied by the number in the **Quantity** field.

    The price and line amounts are shown with or without sales tax depending on what you selected in the **Prices Including Tax** field on the customer card.
8. In the **Line Discount %** field, enter a percentage if you want to grant the customer a discount on the product. The value in the **Line Amount** field is updated accordingly.

    If you set up special item prices on the **Sales Prices and Sales Line Discounts** FastTab on the **Customer Card** or **Item Card** pages, the price and amount values on the sales lines update automatically if the criteria are met. To learn more about prices and discounts, go to [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).
9. To add a comment about the order line, that the customer can read on the printed sales order, write a comment on an empty line in the **Description** field.  
10. Repeat steps 5 through 9 for every item you want to the customer to purchase.

    The totals fields under the lines are automatically updated as you create or modify lines to display the amounts to be posted to the ledgers.

    > [!NOTE]
    > In rare cases, the posted amounts might differ from what is displayed in the totals fields. The difference is typically due to rounding calculations in relation to value-added tax (VAT) or sales tax.
    >
    > To double-check the amounts, use the **Statistics** page, which takes into account the rounding calculations. Also, if you choose the **Release** action, the totals fields update to include rounding calculations.  

11. Optionally, in the **Inv. Discount Amount** field, enter the amount to be deducted from the value shown in the **Total Incl. Tax** field.

    If you set up invoice discounts for the customer, the **Invoice Discount %** field automatically updates if the discount criteria are met. The **Inv. Discount Amount Excl. Tax** field shows related amount. To learn more, go to [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).
12. To ship only part of the order quantity, enter that quantity in the **Qty. to Ship** field. The value automatically copies to the **Qty. to Invoice** field.

    > [!NOTE]
    > If the **Shipping Advice** field is set as **Complete** in the **Shipping and Billing** FastTab, you can't post partial shipments. Learn more at [Process Partial Shipments](sales-how-send-partial-shipments.md).
13. To invoice only part of the shipped quantity, enter that quantity in the **Qty. to Invoice** field. The quantity must be lower than the value in the **Qty. to Ship** field.  
14. When the sales order lines are completed, choose the **Post and Send** action.

[!INCLUDE [order-ship-invoice](includes/order-ship-invoice.md)]

The **Post and Send Confirmation** dialog box displays the customer's preferred method of receiving documents. You can change the sending method by choosing the lookup button for the **Send Document to** field. To learn more, go to [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

The related item and customer ledger entries are now created, and the sales order is output as a PDF document. When the sales order is fully posted, [!INCLUDE [prod_short](includes/prod_short.md)] removes it from the list of sales orders.  

## Create a new sales order based on a copy of another order

> [!TIP]
> This section describes how to copy a sales order, but the steps are the same for other sales documents.

When you're creating a sales order that's similar to a previous one, you can save time by copying the order you already have. For example, you can copy the data in the order's header, its lines, or both, to your new order. Afterward, you can update the information on the new order, if needed.

The value of some fields on an order's lines depend on what you enter in the header. For example, the values in the amount fields depend on the discounts you set up for the customer. If you don't include the header when you copy the order, you must recalculate the lines so that their values are appropriate to the header's values. The **Recalculate Lines** toggle turns on automatically if you turn off the **Include Header** toggle.

> [!NOTE]
> If the **Calc. Inv. Discount** option is selected on the **Sales & Receivables Setup** page, the invoice discount recalculates when you post the new document line. The new calculation might cause the amount on the new line to differ from the original.

> [!NOTE]
> If part of the quantity on the original lines was returned, [!INCLUDE [prod_short](includes/prod_short.md)] creates the new line with only the quantity that wasn't returned. If the full quantity was returned, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't create a new line.

### How to copy a sales order

The following steps describe how to copy a sales order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
1. Choose **New** to create a new document, and then choose the **Copy Document** action.

   > [!NOTE]
   > When you copy an order, you can choose to copy only the information in the order's lines, and not copy the order header. Skipping the header might be useful, for example, when you're selling the same items and quantities to a different customer. If you skip the header, fill in the **Customer Name** field on your new order before you use the **Copy Document** action.

1. In the **Document Type** field, choose **Order**.
1. In the **Document No.** field, choose the order to copy.

   [!INCLUDE [prod_short](includes/prod_short.md)] fills in the **Doc. NO. Occurrence**, **Version No.**, **Sell-to Customer No.**, and **Sell-to Customer Name** fields based on the order you choose.
1. To copy information in the order's header, such as the customer name and the order's due date, turn on the **Include Header** toggle.

   If you choose this option, you also copy the lines. However, you must recalculate the amounts on the lines in the new order.
1. To copy and recalculate the lines from the original order to the new, turn on the **Recalculate Lines** toggle.

   The action keeps the item numbers and item quantities, but recalculates the amounts based on the item prices and discounts for the customer on the new order.

1. Choose **OK** to create the copy.

## External document number

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## Working with amount fields

The values in fields that show amounts can be positive or negative, depending on whether the value represents a credit or a debit. This video shows how to work with fields that show amounts.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=66cfa140-9766-44a6-b024-f4dc5f204a1d]

## Related information

[Invoice Sales](sales-how-invoice-sales.md)  
[Posting Sales](ui-post-sales.md)  
[Ship Items](warehouse-how-ship-items.md)  
[Make Drop Shipments](sales-how-drop-shipment.md)  
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Print the Picking List](sales-how-print-picking-list.md)  
[Process Partial Shipments](sales-how-send-partial-shipments.md)  
[Inventory](inventory-manage-inventory.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
