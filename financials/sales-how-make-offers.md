---
title: 'How to: Make Offers| Microsoft Docs'
description: 'How to: Make Offers'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/12/2016
ms.author: sgroespe

---
# How to: Make Offers
You create a sales quote to record your offer to a customer to sell certain products on certain delivery and payment terms. You can send the sales quote to the customer to communicate the offer. You can email the document as a PDF attachment. You can also have the email body prefilled with a summary of the quote. For more information, see [How to: Send Documents by Email](ui-how-send-documents-email.md).

While you negotiate with the customer, you can change and resend the sales quote as much as needed. When the customer accepts the quote, you convert the sales quote to a sales invoice or a sales order in which you process the sale. For more information, see [How to: Invoice Sales](sales-how-invoice-sales.md) or [How to: Sell Products](sales-how-sell-products.md).

Products can be both inventory items and services. For more information, see [How to: Register New Products](inventory-how-register-new-products.md). The sales quote process is the same for both product types.

**Note**: In [!INCLUDE[d365fin](includes/d365fin_md.md)], a product is referred to with the term “item”.

You can fill customer fields on the sales quote in two ways depending on whether the customer is already registered.

## To create a sales quote
1. On the Home page, choose the **Sales Quote** action.  
2. In the **Customer** field, enter the name of an existing customer.
   
    Other fields in the **Sales Quote** window are now filled with the standard information of the selected customer. If the customer is not registered, then follow these steps:
3. In the **Customer** field, enter the name of the new customer.
4. In the dialog box about registering the new customer, choose the **Yes** button.
5. In the **Select a template for a new customer** window, choose a template to base the new customer card on, and then choose the **OK** button.
6. A new customer card opens, prefilled with the information on the selected customer template. The **Name** field is prefilled with the new customer’s name that you entered on the sales invoice.
7. Proceed to fill in the remaining fields on the customer card. For more information, see [How to: Register New Customers](sales-how-register-new-customers.md).  
8. When you have completed the customer card, choose the **OK** button to return to the **Sales Quote** window.
   
    Several fields on the sales quote are now filled with information that you specified on the new customer card.
9. Fill in the remaining fields in the **Sales Quote** window as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
   
    You are now ready to fill in the sales quote lines with inventory items or services that you want to offer to the customer.
   
    **Note**: If you have set up recurring sales lines for the customer, such as a monthly replenishment order, then you can insert these lines on the quote by choosing the **Get Recurring Sales Lines** action.
10. On the **Lines** FastTab, in the **Item No.** field, enter the number of an inventory item or service.
11. In the **Quantity** field, enter the number of items to be offered.
    
    **Note**: For items of type Service, the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line.
    
    The **Line Amount** field is updated to show the value in the **Unit Price** field multiplied by the value in the **Quantity** field.
    
    The price and line amounts are shown with or without sales tax depending on what you selected in the **Prices Including Sales Tax** field on the customer card.
12. In the **Line Discount %** field, enter a percentage if you want to grant the customer a discount on the product. The value in the **Line Amount** field is updated accordingly.
    
    **Note**: If you have set up special item prices on the **Sales Prices and Sales Line Discounts** FastTab on the customer or item card, then the price and amount on the quote line are automatically updated if the agreed price criteria are met. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).
13. To add a comment about the quote line that the customer can see on the printed sales quote, write a text in the **Description** field on an empty line.  
14. Repeat steps 10 through 13 for every item that you want to offer to the customer.
    
    The totals under the lines are automatically calculated as you create or modify lines.
15. In the **Invoice Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field.
    
    **Note**: If you have set up invoice discounts for the customer, then the specified percentage value is automatically inserted in the **Invoice Discount %** field if the criteria are met, and the related amount is inserted in the **Inv. Discount Amount Excl. Tax** field. For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).
16. When the sales quote lines are completed, choose the **Email** or **Print** action.
    
    If you select the **Email** action, then a PDF file is automatically attached to an email to the customer. You can set the email up to contain a summary of the quote. For more information, see [How to: Send Documents by Email](ui-how-send-documents-email.md).
17. If the customer accepts the quote, choose the **Make Invoice** or the **Make Order** action.

The sales quote is removed from the database. A sales invoice or a sales order is created based on the information in the sales quote in which you can process the sale. In the **Quote No.** field on the sales invoice or sales order, you can see the number of the sales quote that it was made from. For more information, see [How to: Invoice Sales](sales-how-invoice-sales.md) or [How to: Sell Products](sales-how-sell-products.md).

## See Also
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[How to: Send Documents by Email](ui-how-send-documents-email.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

