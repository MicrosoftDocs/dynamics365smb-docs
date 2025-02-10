---
title: Set up payment methods
description: You use payment methods, for example, check, bank transfer, cash, or PayPal, to define how sales and purchase invoices are paid.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: check, bank transfer, cash, PayPal
ms.search.form: 427,
ms.date: 06/10/2024
ms.service: dynamics-365-business-central

---
# Set up payment methods

Payment methods define the way you prefer for customers to pay you, and how you like to pay your vendors. The method can vary for each customer or vendor. Examples of typical payment methods are **bank**, **cash**, **check**, or **account**.

You can assign a payment method to customers and vendors so that the same method is always used on the sales and purchase documents you create for them. If needed, you can change the method on the sales or purchase document. For example, if you want to pay a particular purchase invoice in cash rather than by check. The default payment method assigned to the vendor doesn't change.

The same payment methods are used for sales and purchase documents. For example, a _cash_ payment method is used to make payments and to receive them. [!INCLUDE[prod_short](includes/prod_short.md)] knows that when you're creating a sales invoice you expect to receive payment, and the opposite for purchase invoices.

Credit memos for returns, however, are exceptions because money is flowing in the opposite directions, from you to your customer and from your vendor to you. Therefore, a default payment method isn't assigned to credit memos. There is, however, a workaround. You can specify terms of payment for the customer or vendor. Though the **Calc. Pmt. Disc. on Cr. Memos** field isn't intended for this workaround, if you choose the checkbox on the **Payment Terms** page a default payment method is added when you create a credit memo. <br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=34d91385-2010-4135-b47d-2062660ede80]

## To set up a payment method

[!INCLUDE[prod_short](includes/prod_short.md)] provides a few payment methods that businesses often use. You can, however, add as many as you need.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Methods**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Optionally, add payment terms to your payment method. For more information, see [Set Up Payment Terms](finance-payment-terms.md).  

## To assign a payment method to a customer or vendor

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer** or **Vendor**, and then choose the related link.
2. In the **Payment Method Code** field, choose the method to use by default for the customer or vendor.

## Audit changes to payment methods

You can use the Change Log feature to capture changes users make to your payment method setup. [!INCLUDE [include-audit-what-who-when](includes/include-audit-what-who-when.md)] 

The following table lists the table for payment methods and its ID.

| Table | Table ID |
| ----- | -------- |
| Payment Method | 289 |

[!INCLUDE [include-audit-changes-to-setup-learn-more-link](includes/include-audit-changes-to-setup-learn-more-link.md)]


## See also

[Register New Customers](sales-how-register-new-customers.md)  
[Set Up Payment Terms](finance-payment-terms.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
