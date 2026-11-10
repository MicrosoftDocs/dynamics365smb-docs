---
title: Enter External Document Numbers
description: Enter customer and vendor document numbers on sales and purchase documents so you can find related entries and avoid duplicate purchase invoices.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: external document numbers, vendor invoice numbers, purchase order, sales order
ms.date: 11/10/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Enter external document numbers

You can enter external document numbers for customers and vendors in all sales and purchase orders, invoices, and credit memos. You can use these numbers to search for posted sales and purchase lines later.  

> [!NOTE]
> Use the document number assigned by your customer or vendor. When you post a purchase invoice or credit memo with an external document number, [!INCLUDE [prod_short](includes/prod_short.md)] checks vendor ledger entries for the same external document number, document type, and pay-to vendor. A matching entry that isn't reversed prevents posting.

The following procedure explains how to specify an external document number on a sales order, but similar steps apply to other sales and purchase documents.

## To enter external document numbers in a sales order  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.  
1. Select the relevant sales order, and then choose the **Edit** action.
1. On the **General** FastTab, in the **External Document No.** field, enter the customer's document number, such as their purchase order number.

    For a purchase invoice, use the **Vendor Invoice No.** field. For a purchase credit memo, use the **Vendor Cr. Memo No.** field.
1. Fill in any other required fields.

## Related information

[External Document Numbers on Purchase Documents](purchasing-ext-doc-no.md)  
[External Document Numbers on Sales Documents](sales-how-invoice-sales.md#external-document-numbers)  
[Sell Products](sales-how-sell-products.md)  
[Purchasing](purchasing-manage-purchasing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
