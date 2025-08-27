---
title: Combine receipts on a single invoice
description: If you want to invoice more than one purchase receipt at a time, you can use the Combine Receipts function.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.search.form: 136, 145, 146, 9308
ms.date: 03/14/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Combine receipts on a single invoice

If you want to invoice more than one purchase receipt at a time, you can select multiple receipt lines on the purchase invoice.  

Before you can create a combined purchase receipt, more than one receipt from the same vendor in the same currency must be posted. In other words, you must have filled in two or more purchase orders and posted them as received, but not invoiced.  

When purchase receipts are combined on an invoice and posted, then a posted purchase invoice is created for the invoiced lines. The **Quantity Invoiced** field on the originating purchase order, or blanket purchase order, is updated based on the invoiced quantity. However, this original purchase document isn't deleted, even if it has been fully received and invoiced, and you must therefore delete the purchase document.  

> [!NOTE]
> The resulting purchase invoice cannot later be corrected or canceled. If you want to modify a purchase invoice that is created in this way, you must use purchase credit memos. For more information, see [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

## To combine receipts

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.  
2. Choose the **New** action. For more information, see [Record Purchases](purchasing-how-record-purchases.md).  
3. On the **Lines** FastTab, choose the **Get Receipt Lines** action.  
4. Select multiple receipt lines that you want to include in the invoice.  

    If an incorrect receipt line was selected or you want to start over, you can just delete the lines on the purchase invoice and then use the **Get Receipt Lines** function again.  
5. To post the invoice, choose the **Post** action.  

## To remove open purchase orders after combined receipt posting

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Delete Invoiced Purchase Orders**, and select the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
3. Choose the **OK** button.  

Alternatively, delete the individual orders manually.

Repeat steps 1 through 3 for any other affected documents, such as blanket purchase orders.

## Related information

[Purchasing](purchasing-manage-purchasing.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
