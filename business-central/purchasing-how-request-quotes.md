---
title: Create a Purchase Quote to Request an Offer | Microsoft Docs
description: Describes how to create a sales offer or a request for proposal (RFQ) document to record your offer to a customer to sell products under certain terms.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: rfq
ms.date: 04/01/2020
ms.author: sgroespe

---
# Request Quotes
A purchase quote can be used as a preliminary draft for a purchase order, and the order can then be converted to a purchase invoice or an order.


## To create a purchase quote
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Quotes**, and then choose the related link.
2. Create a new document, in the same way as you make a purchase order. For more information, see [Record Purchases](purchasing-how-record-purchases.md).

## To convert a purchase quote to a purchase order
When you have accepted the vendor's quote, you can convert it to a purchase invoice or order to process the purchase.

1. Open a purchase quote that is ready to convert, and then choose the **Make Order** action.

The purchase quote is removed from the database. A purchase invoice or a purchase order is created based on the information in the purchase quote in which you can process the purchase. In the **Quote No.** field on the purchase invoice or purchase order, you can see the number of the purchase quote that it was made from.

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
