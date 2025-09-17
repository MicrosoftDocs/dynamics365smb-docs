---
title: Invoice sales
description: Learn how to create a sales invoice or sales order to record a sale to a customer.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: bill, sale, invoice, order
ms.search.form: 43, 48, 9301
ms.date: 05/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Invoice sales

You can usually create either a sales order or sales invoice to record your agreement with a customer to sell certain products on certain delivery and payment terms.  

However, you must use a sales order instead of a sales invoice if you:  

* Need to ship only part of an order quantity, for example, because the full quantity isn't on hand.  
* Ship products after you post the corresponding sales invoices.
* Sell items your vendor delivers directly to your customer, known as drop shipment. Learn more at [Make Drop Shipments](sales-how-drop-shipment.md).  

In all other situations, sales orders and sales invoices work in the same way. Learn more about how to use sales orders at [Sell Products](sales-how-sell-products.md).

You can negotiate with the customer by first creating a sales quote, which you can convert to a sales invoice when you agree on the sale. Learn more at [Make Sales Quotes](sales-how-make-offers.md).

## Create sales invoices

If the customer decides to buy, you post the sales invoice to create the related quantity and value entries. When you post the sales invoice, you can also email it as a PDF attachment. You can prefill the email body with a summary of the invoice and payment information, such as providing a link to PayPal. Learn more at [Send Documents by Email](ui-how-send-documents-email.md#to-send-documents-by-email). When the customer pays the invoice, you can register that payment in different ways, depending on the size and preferred workflows of your organization. Learn more at [Registering Payments](#register-payments) section.  

Item cards can be of the **Inventory**, **Service**, or **Non-Inventory** type to specify if the item is a physical inventory unit, a labor time unit, or a physical unit not kept on inventory, respectively. Learn more at [Register New Items](inventory-how-register-new-items.md). The sales invoice process is the same for all three item types.

You can fill customer fields on the sales invoice in one of two ways, depending on whether the customer is already registered. See step 2 in the following procedure.

### To create a sales invoice

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Invoices**, and then choose the related link.  
2. In the **Customer Name** field, enter the name of an existing customer. If, however, the customer is new and therefore not registered, follow these steps to populate standard customer information on the **Sales Invoice** page:

    1. In the **Customer Name** field, enter the name of the new customer.
    2. In the dialog box about registering the new customer, choose **OK**.
    3. On the **Select a template for a new customer** page, choose a template to base the new customer card on, then choose **OK**.
    4. A new customer card displays the information on the selected customer template. Fill in the remaining fields. Learn more at [Register New Customers](sales-how-register-new-customers.md).  
    5. When you complete the customer card, choose **Close** to return to the **Sales Invoice** page.

   Several fields on the sales invoice are now filled with information that you specified on the new customer card.  
3. Fill in the remaining fields on the **Sales Invoice** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > If you allow the customer to pay immediately, for example, by cash or PayPal, then fill in the **Payment Method Code** field. The payment is then recorded as soon as you post the sales invoice. If you select *Cash*, then the payment is recorded in a specified balancing account.

    You're now ready to fill in the **Lines** FastTab with products you're selling to the customer or for any transaction with the customer you want to record in a general ledger (G/L) account.

4. On the **Lines** FastTab, in the **Type** field, select the type of product, charge, or transaction you post for the customer on the sales line.
   > [!TIP]
   > If you set up recurring sales lines for the customer, such as a monthly replenishment order, you can reflect that in the order by choosing the **Get Recurring Sales Lines** action.
5. In the **No.** field, select a record to post according to the value in the **Type** field.

    You leave the **No.** field blank in the following cases:

    * If the line is for a comment. Write the comment in the **Description** field.
    * If the line is for a catalog item. Choose the **Select Catalog Items** action. Learn more at [Work With Catalog Items](inventory-how-work-nonstock-items.md).

6. In the **Quantity** field, enter how many units of the product, charge, or transaction the line should record for the customer.  

    > [!NOTE]  
    > If the item is of the **Service** type, or the **Type** field contains **Resource**, then the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line. Learn more at [Set Up Item Units of Measure](inventory-how-setup-units-of-measure.md)

    The value in the **Line Amount** field is calculated as *Unit Price* × *Quantity*.  

    The price and line amounts are with or without sales tax, depending on what you selected in the **Prices Including Tax** field on the customer card.  
7. If you want to give a discount, enter a percentage in the **Line Discount %** field. The value in the **Line Amount** field updates accordingly.  

    If special item prices are set up on the **Sales Prices and Sales Line Discounts** FastTab on the customer or item card, upon meeting the price criteria the price and amount on the sales line automatically update. Learn more at [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).  
8. Repeat steps 4 through 7 for every product or charge that you want to invoice the customer for.

    The totals fields under the lines are automatically updated, as you create or modify lines, to display the amounts posted to the ledgers.

    > [!NOTE]
    > In rare cases, the posted amounts might differ from what displays in the totals fields. The difference is typically due to rounding calculations for VAT or sales tax.<br /><br />To verify the amounts before you post, use the **Customer Statistics** FactBox. Also, when you choose the **Release** action, the values in the totals fields update to include rounding calculations.

9. In the **Inv. Discount Amount Excl. Tax** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field.

    If you set up invoice discounts for the customer, then the specified percentage value is automatically inserted in the **Invoice Discount %** field if the discount criteria are met, and the related amount is inserted in the **Inv. Discount Amount Excl. Tax** field. Learn more at [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).

10. When the sales invoice lines are completed, choose the **Post and Send** action.  

The **Post and Send Confirmation** dialog box displays the customer's preferred method of receiving documents. You can change the sending method by choosing the lookup button for the **Send Document to** field. Learn more at [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

The related item and customer ledger entries are now created in your system, and the sales invoice is output as a PDF document. The sales invoice is removed from the list of sales invoices and replaced with a new document in the list of posted sales invoices.  

### Calculate invoice discounts on sales

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Posted invoices

[!INCLUDE [posted-invoices](includes/posted-invoices.md)]

You can easily correct or cancel a posted sales invoice before the final payment. For example, you might want to correct a typing mistake, or the customer requests a change. Learn more at [Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md). If the posted sales invoice is paid, you must create a sales credit memo to reverse the sale. Learn more at [Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md).  

[Open the **Posted Sales Invoices** list](https://businesscentral.dynamics.com/?page=143) in [!INCLUDE [prod_short](includes/prod_short.md)].

## Register payments

Depending on your business needs, you can get paid and register a payment in different ways: manually, automatically, and through payment services.  

You can process the payments straight from the customer card. Use the **Register Customer Payments** action to get an overview of unpaid invoices for that customer. Then, mark the invoice as paid partially or in full. This payment reconciliation processes your customer payments by matching amounts received in your bank account with the related unpaid sales invoices, and then posts the payments. Learn more in the [To reconcile payments individually](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-register-customer-payments-individually) section.  

In business environments where the customer pays after delivery. According to the payment terms, a posted sales invoice remains open (unpaid) until someone verifies the payment and applies it to the posted sales invoice. You can apply payments manually or automatically. Learn more at [Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries](receivables-how-apply-sales-transactions-manually.md) and [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).  

In business environments where customers pay immediately, such as via PayPal or cash, payment is recorded immediately when you post the sales invoice. Also, the posted sales invoice is closed as fully applied. You select the relevant method in the **Payment Method Code** field on the sales order. For electronic payments, such as PayPal, you must also fill in the **Payment Service** field. Learn more at [Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md).

You can even create directly paid invoices for unregistered customers by setting up a "cash customer" card for them, which you point to on the sales invoice. Learn more at [Set Up Cash Customers](finance-how-to-set-up-cash-customers.md).  

> [!TIP]
> If you want to send your customers reminders of overdue payments, you need to first set up reminder levels and terms. Learn more at [Set Up Reminder Terms and Levels](finance-setup-reminders.md).  

## External document numbers

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Print the Picking List](sales-how-print-picking-list.md)  
[Inventory](inventory-manage-inventory.md)  
[Send Documents by Email](ui-how-send-documents-email.md#to-send-documents-by-email)  
[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Bulk Invoicing from Microsoft Bookings in Business Central](finance-bookings.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
