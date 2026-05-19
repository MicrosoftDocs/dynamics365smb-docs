---
title: Combine receipts or PO lines on a single invoice
description: Use the Combine Receipts function to invoice multiple purchase receipts from the same vendor on a single purchase invoice.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: combine receipts, single invoice, purchase invoice, purchase receipt, purchase order, blanket purchase order, post purchase invoice, get receipt lines
ms.search.form: 136, 145, 146, 9308
ms.date: 03/23/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Combine receipts or purchase order lines on a single invoice

If you work with purchase orders and invoices, you might experience that:

- A vendor invoice arrives before you receive the goods they're billing you for.
- A vendor invoice covers multiple receipts or purchase order lines.

To handle situations like these, you can use the **Get Receipt Lines** or **Get Order Lines** actions on the **Purchase Invoices** page. This article describes these actions.

## Use the Get Receipt Lines action

If you want to invoice more than one purchase receipt at a time, you can select multiple receipt lines on the purchase invoice. Before you can create a combined purchase receipt, you must post more than one receipt from the same vendor in the same currency. In other words, you must create two or more purchase orders and post them as received but not invoiced.  

When you combine and post purchase receipts on an invoice, a posted purchase invoice is created for the invoiced lines. The **Quantity Invoiced** field on the originating purchase order or blanket purchase order updates based on the invoiced quantity. However, the original purchase document isn't deleted, even if it was fully received and invoiced. If needed, you can manually delete the purchase document.

> [!NOTE]
> You can't change or cancel the resulting purchase invoice, for example, to correct a mistake. If you want to modify a purchase invoice that you created in this way, you must use a purchase credit memo. Learn more in [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

To att lines from receipts, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.  
2. Choose the **New** action. Learn more in [Record Purchases](purchasing-how-record-purchases.md).  
3. On the **Lines** FastTab, choose the **Get Receipt Lines** action.  
4. Select multiple receipt lines that you want to include in the invoice.  

    If you chose an incorrect receipt line or you want to start over, you can just delete the lines on the purchase invoice and then use the **Get Receipt Lines** action again.  
5. To post the invoice, choose the **Post** action.  

### Remove open purchase orders after combined receipt posting

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Delete Invoiced Purchase Orders**, and select the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
3. Choose the **OK** button.  

Alternatively, delete the individual orders manually.

Repeat steps 1 through 3 for any other affected documents, such as blanket purchase orders.

## Use the Get Order Lines action

The **Get Order Lines** action on the **Purchase Invoice** page opens a list of order lines that are received but not invoiced, or order lines that aren't received. You can match each invoice line to any number of purchase order lines, regardless of whether receipts exist. When receipts exist, they display with the relevant details. When receipts don't exist, you can match the invoice line directly to the purchase order lines and decide later whether to receive manually or to use the autoreceipt capability.

From each invoice line, you can open the **Matched Order Lines** page to review and adjust the order lines that you'll invoice with that invoice line. You can edit quantities, add more purchase order lines or posted receipt lines, and review discrepancies such as price or amount differences. You can also open the **Matched Order Lines** page on the invoice header to review and correct matching across the entire document.

On purchase orders, the **Matched Invoice Lines** field shows the quantity matched through invoice lines to each order line. 

When you turn on the **Receipt on Invoice** toggle on the order, posting the linked invoice automatically creates the required receipts. However, you can't enable this option for orders that use advanced warehouse operations or item tracking, or are already partially received.

To add lines from purchase orders, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.  
2. Choose the **New** action. Learn more in [Record Purchases](purchasing-how-record-purchases.md).  
3. On the **Lines** FastTab, choose the **Get Order Lines** action.  
4. Select the orders that you want to include in the invoice.  

    If you chose an incorrect order or you want to start over, you can just delete the lines on the purchase invoice and then use the **Get Order Lines** action again.  
5. To post the invoice, choose the **Post** action.

### Known limitations for the Get Order Lines action

This feature has a few limitations to be aware of:
 
- It doesn’t work with orders that have prepayments, or lines of the **Item Charges** type.
- You can’t use it with orders linked to projects, subcontracting, blanket orders, or intercompany transactions.
- You can’t use autoreceive with partially received lines, or locations that use directed put-away and pick (in warehouse management).

## Related information

[Purchasing](purchasing-manage-purchasing.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
