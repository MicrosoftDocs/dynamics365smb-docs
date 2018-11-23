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
ms.date: 11/22/2018
ms.author: bholtorf

---
# Defining Payment Methods
Payment methods define how you prefer customers to pay you, and how your vendors prefer for you to pay them. Examples of typical payment methods are **bank**, **cash**, **check**, or **account**. After you assign a payment method to customers and vendors, the method will be added by default to the sales and purchase documents that you create for them. If needed, you can change the method on the sales or purchase document. For example, if you want to pay a purchase invoice in cash rather than by check. This does not change the default payment method assigned to the vendor.

The same payment methods are used for sales and purchase documents. For example, a cash payment method is used both when you make payments and when you receive them. [!INCLUDE[d365fin](includes/d365fin_md.md)] knows that when you are creating a sales invoice you expect to receive payment, and the opposite for purchase invoices.

Credit memos, however, are an exception because money is flowing in the opposite directions, from you to your customer and from your vendor to you. Therefore a default payment method is not assigned by default to credit memos. For example, if you need to return money to your customer you will probably want to use a bank transfer payment method and not direct debit. There is, however, a workaround. Though the **Calc. Pmt. Disc. on Cr. Memos** field is not intended for this, if you choose the check box for a payment method it will be added by default when you create credit memos.

## To set up a payment method
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides a few payment methods that businesses often use. You can, however, add as many as you need.

## To set up a payment methods
Several typical payment methods are already defined in [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can define new payment methods on the **Payment Methods** page, which you can find with the search function or open from the **Payment Method** field on an a vendor or customer card.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Methods**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To assign a payment method to a customer or vendor
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer** or **Vendor**, and then choose the related link.
2. In the **Payment Method** field, choose the method to use by default for the customer or vendor.

## See Also
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
