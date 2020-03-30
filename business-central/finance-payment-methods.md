---
title: Set Up Payment Methods| Microsoft Docs
description: You use payment methods, for example, check, bank transfer, cash, or PayPal, to define how sales and purchase invoices will be paid.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: check, bank transfer, cash, PayPal
ms.date: 04/01/2020
ms.author: bholtorf

---
# Defining Payment Methods
Payment methods define the way you prefer for customers to pay you, and how you like to pay your vendors. The method can vary for each customer or vendor. Examples of typical payment methods are **bank**, **cash**, **check**, or **account**.

You can assign a payment method to customers and vendors so that the same method is always used on the sales and purchase documents you create for them. If needed, you can change the method on the sales or purchase document. For example, if you want to pay a particular purchase invoice in cash rather than by check. This does not change the default payment method assigned to the vendor.

The same payment methods are used for sales and purchase documents. For example, a _cash_ payment method is used both when you make payments and when you receive them. [!INCLUDE[d365fin](includes/d365fin_md.md)] knows that when you are creating a sales invoice you expect to receive payment, and the opposite for purchase invoices.

Credit memos for returns, however, are exceptions because money is flowing in the opposite directions, from you to your customer and from your vendor to you. Therefore, a default payment method is not assigned to credit memos. There is, however, a workaround if you have specified terms of payment for the customer or vendor. Though the **Calc. Pmt. Disc. on Cr. Memos** field is not intended for this, if you choose the check box on the **Payment Terms** page a default payment method will be added when you create a credit memo. <br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE476Ys?rel=0]

## To set up a payment method
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides a few payment methods that businesses often use. You can, however, add as many as you need.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Methods**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To assign a payment method to a customer or vendor
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer** or **Vendor**, and then choose the related link.
2. In the **Payment Method Code** field, choose the method to use by default for the customer or vendor.

## See Also
[Register New Customers](sales-how-register-new-customers.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
