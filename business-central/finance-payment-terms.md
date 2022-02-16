---
title: Set Up Payment Terms
description: In the base version of Business Central, use payment terms to manage due dates and payment discounts. 
author: edupont04


ms.topic: conceptual
ms.search.form: 4
ms.date: 04/01/2021
ms.author: edupont
---
# Set Up Payment Terms

Payment terms determine how you manage due dates and payment discounts. You can set up any number of payment term codes and use date formulas to define the payment terms. When you first sign up for [!INCLUDE [prod_short](includes/prod_short.md)], the demonstration company provides a few payment methods that businesses often use. You can, however, add as many as you need.  

You can assign payment terms to customers and vendors so that the same terms are always used on the sales and purchase documents you create for them. If needed, you can change the terms on the sales or purchase document, such as if you want a particular customer to pay you within 7 days rather than the default 14 days. This does not change the default payment term assigned to the customer. The same payment terms are available for sales and purchase documents.

Then, when you post an invoice, [!INCLUDE [prod_short](includes/prod_short.md)] calculates the payment discounts based on the payment terms. The payment discount date, that is, the latest date on which the customer can pay and receive a discount on the payment, will also be calculated at that time.  

Similarly, when you post a credit memo, [!INCLUDE [prod_short](includes/prod_short.md)] calculates possible payment discounts based on the payment terms. The discount on credit memos is calculated according to the same principles as payment discounts on invoices. Where a credit memo is applied to an invoice, the possible payment discount amount for the invoice will be reduced by the payment discount amount for the credit memo.  

If you want to send your customers reminders of overdue payments, you must set up reminder levels and terms. For more information, see [Set Up Reminder Terms and Levels](finance-setup-reminders.md).  

## To set up payment terms

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Terms**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

After you set up the payment terms, you assign them to customers and vendors. Optionally, assign payment terms to your payment methods.  

> [!TIP]
> In the base version of [!INCLUDE [prod_short](includes/prod_short.md)], payment terms with partial payments are not supported. Instead, you must use the prepayments functionality. For more information, see [Set Up Prepayments](finance-set-up-prepayments.md).
>
> In certain countries, you *can* set up payment terms with partial payments. To learn if this capability is supported in your country, see the **Local Functionality** section in the navigation pane on the left side on the [Docs.microsoft.com](about-localization.md) site.

## See Also

[Set Up Payment Methods](finance-payment-methods.md)  
[Set Up Prepayments](finance-set-up-prepayments.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Register New Customers](sales-how-register-new-customers.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]