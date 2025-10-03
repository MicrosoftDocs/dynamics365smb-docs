---
title: Create a purchase quote to request an offer
description: Describes how to create a sales offer or a request for quote (RFQ) document to record your offer to a customer to sell products under certain terms.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: rfq
ms.search.form: 49, 97, 9306, 9346
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Request quotes

A purchase quote can be used as a preliminary draft for a purchase order, which can then be converted to a purchase invoice.

## Create a purchase quote

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Quotes**, then choose the related link.
2. Create a new document, in the same way as you make a purchase order. Learn more in [Record Purchases](purchasing-how-record-purchases.md).

## Convert a purchase quote to a purchase order

When you accept the vendor's quote, you can convert it to a purchase order to process the purchase.

1. Open the purchase quote you want to convert, then choose the **Make Order** action.

The purchase quote is removed from the database. A purchase order is created based on the information in the purchase quote, which you can use to process the purchase, and then post a purchase invoice. In the **Quote No.** field on both the purchase order and purchase invoice you can see the number of the purchase quote they were made from.

> [!NOTE]
> It isn't possible to convert a purchase quote to a purchase invoice directly. But it's possible with sales quotes. Learn more in [Record Purchases with Purchase Invoices](purchasing-how-record-purchases.md) for details on how to create a purchase invoice.

## Related information

- [Purchasing](purchasing-manage-purchasing.md)  
- [Setting Up Purchasing](purchasing-setup-purchasing.md)  
- [Send Documents by Email](ui-how-send-documents-email.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
