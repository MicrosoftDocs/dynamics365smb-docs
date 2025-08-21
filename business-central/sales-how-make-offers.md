---
title: Make sales quotes
description: Read about how to create a sales offer to a customer or prospect to sell products.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: rfq
ms.search.form: 41, 9300
ms.date: 06/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Make sales quotes

You create a sales quote to record your offer to a customer or a prospect to sell certain products on certain delivery and payment terms. You can send the sales quote to the customer to communicate the offer. You can email the document as a PDF attachment. You can also have the email body prefilled with a summary of the quote. To learn more, go to [Send Documents by Email](ui-how-send-documents-email.md#to-send-documents-by-email).

While you negotiate with the customer or prospect, you can change and resend the sales quote as much as needed. When the customer accepts the quote, you convert the sales quote to a sales invoice or a sales order in which you process the sale. To learn more, go to [Invoice Sales](sales-how-invoice-sales.md) or [Sell Products](sales-how-sell-products.md).

In most cases, you send sales quotes to prospective customers. You often have a contact person that you negotiate with. If they then accept your offer, you turn the sales quote into an order and register the prospect as a customer in [!INCLUDE [prod_short](includes/prod_short.md)]. In the following procedure, we focus on contacts, but you can also send quotes to existing customers.  

> [!TIP]
> You can use the Sales Order Agent in [!INCLUDE [prod_short](includes/prod_short.md)] to speed up the quote-to-order workflow. The agent can automate the process for creating quotes based on requests you receive by email from customers. With the agent handling the paperwork, you're free to focus on other tasks such as generating more prospects. To learn more, go to [Process sales quotes and orders with Sales Order Agent (preview)](sales-order-agent-process.md).

## To create a sales quote

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Quotes**, and then choose the related link.
2. Specify the contact or customer that you want to send the sales quote to.

    - If the sales quote is for an existing contact, then specify the name in the **Contact No.** field.  

        If the sales quote is for an existing customer, specify the customer in the **Customer** field.
    - If the contact isn't registered, follow these steps:

        1. In the **Contact No.** field, choose the :::image type="icon" source="media/assist-edit-icon.png" border="false"::: button.
        2. In the dialog box about selecting the contact, choose the **New** action, and then fill in the relevant fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] To learn more, go to [Create Contacts](marketing-create-contact-companies.md).  
        3. After you fill in the contact card, select the new contact in the list of contacts, and then choose **OK** to return to the sales quote.

        Several fields on the sales quote are now filled with information that you specified on the new contact card.

        > [!NOTE]
        > To correctly calculate taxes and prices for a quote, you must choose the relevant customer template in the **Customer Template Code** field. The template is used to convert the contact to a customer when you convert the quote to a sales order or invoice.
    -  If the quote is for new customer, you must add the customer. To learn more, go to [Register New Customers](sales-how-register-new-customers.md).  

3. Fill in the remaining fields on the **Sales Quote** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    You're now ready to fill in the sales lines for products that you're selling or for any transaction with the customer or prospect that you want to record in a G/L account.  

    If you set up recurring sales lines for the customer, such as a monthly replenishment order, then you can insert these lines on the order by choosing the **Get Recurring Sales Lines** action.  

4. On the **Lines** FastTab, in the **Type** field, select the type of product, charge, or transaction to post for the customer with the sales line.
5. In the **No.** field, select a record to post according to the value in the **Type** field.

    You leave the **No.** field empty in the following cases:
    - If the line is for a comment. Write the comment in the **Description** field.
    - If the line is for a catalog item. Choose the **Select Catalog Items** action. To learn more, go to [Work With Catalog Items](inventory-how-work-nonstock-items.md).

6. In the **Quantity** field, enter how many units of the product, charge, or transaction that the line records for the customer.

    > [!NOTE]  
    >  If the item is of type **Service**, or the **Type** field contains **Resource**, then the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line. To learn more, go to [Set Up Item Units of Measure](inventory-how-setup-units-of-measure.md)

    The value in the **Line Amount** field is calculated as *Unit Price* x *Quantity*.  

    The price and line amounts are with or without sales tax, depending on what you selected in the **Prices Including Tax** field on the customer card.  
7. If you want to give a discount, enter a percentage in the **Line Discount %** field. The value in the **Line Amount** field updates accordingly.  

    If special item prices are set up on the **Sales Prices and Sales Line Discounts** FastTab on the customer or item card, the price and amount on the sales line automatically update if the price criterion is met. To learn more, go to [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).  
8. Repeat steps 4 through 7 for every product you want to offer the contact.

    The totals under the lines are automatically calculated as you create or modify lines.  
9. In the **Inv. Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field.

    If you set up invoice discounts for the customer, the specified percentage value is automatically inserted in the **Invoice Discount %** field if the criteria are met. The related amount is inserted in the **Inv. Discount Amount Excl. Tax** field. To learn more, go to [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).

    > [!TIP]
    > To have the **Quote Valid Until Date** filled in automatically with a number of days after quote creation, you can enter a date formula in the **Quote Validity Calculation** field on the **Sales & Receivables Setup** page. To learn more about date formulas, go to .

10. When the sales quote lines are completed, choose the **Send by Email** action.
11. On the **Send Email** page, fill in any remaining fields and review the embedded sales quote. To learn more, go to [Send Documents by Email](ui-how-send-documents-email.md#to-send-documents-by-email).
12. If the contact accepts the quote, choose the **Make Order** action.  

    Alternatively, if your organization prefers that process, choose the **Make Invoice** action.  
    > [!NOTE]
    > If you added a customer in step 2, confirm the conversion of the quote to an order.  
    >
    > If you added a contact from a prospective customer in step 2, take the following steps:
    >
    >  - Convert the contact or prospect to a customer by choosing one of contact conversion templates. To learn more, go to [To create a customer, vendor, employee, or bank account from a contact](marketing-create-contact-companies.md#to-create-a-customer-vendor-employee-or-bank-account-from-a-contact).  
    > - Confirm the conversion of the quote to an order.

The conversion removes the sales quote from the database. A sales invoice or a sales order is created based on the information in the sales quote so that you can process the sale. The **Quote No.** field on the sales invoice or sales order shows the ID of the sales quote that it was made from. To learn more, go to [Invoice Sales](sales-how-invoice-sales.md) or [Sell Products](sales-how-sell-products.md).  

## External document number

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Send Documents by Email](ui-how-send-documents-email.md#to-send-documents-by-email)  
[Archive Documents](across-how-to-archive-documents.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
