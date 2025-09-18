---
title: Correct or cancel a posted sales invoice
description: This article describes how to correct, undo, or cancel a posted sales invoice and apply a sales credit memo.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: undo, credit memo, return
ms.date: 06/10/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Correct or cancel unpaid sales invoices

You can correct or cancel an unpaid posted sales invoice if it isn't fully shipped. For example, if you make a mistake or if the customer requests a change before the shipment is complete. In all other scenarios, we recommend that you create a corrective sales credit memo. Learn more at [To create a sales credit memo from a posted sales invoice](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-from-a-posted-sales-invoice).  

> [!NOTE]  
> After a posted sales invoice is partially or fully paid, you can't correct or cancel it from the posted sales invoice itself. Instead, you must manually create a sales credit memo to void the sale and reimburse the customer, optionally managed with a sales return order. Learn more at [Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md).

The following table describes the difference between canceling or correcting a posted sales invoice that isn't paid or shipped.

| Action | Description |
| --- | --- |
| **Cancel** |The posted sales invoice is canceled. A corrective sales credit memo is automatically created and posted to void the initial posted sales invoice. On the initial posted sales invoice, the **Canceled** and **Paid** checkboxes are selected. |
| **Correct** |The posted sales invoice is canceled. A new sales invoice with the same information is created, unless the posted sales order was posted from a sales order. In that case, we suggest you cancel the posted sales invoice instead and then make the correction and continue the sales process from the original sales order. <br/><br/>The new sales invoice has a different number than the initial sales invoice. A corrective sales credit memo is automatically created and posted to void the initial posted sales invoice. On the initial posted sales invoice, the **Canceled** and **Paid** checkboxes are selected. |
|**Create Corrective Credit Memo**|A new sales credit memo is created with the same information. You can adjust the new sales credit memo before posting, and it applies to the original invoice when you post it. |

The sales credit memo applies to all general ledger and inventory ledger entries that were created when you posted the initial sales invoice. This application reverses the posted sales invoice in your financial records and leaves the corrective posted sales credit memo for your audit trail.  

> [!TIP]
> If you posted a prepayment invoice for a sales invoice that you correct or cancel, you must correct or cancel the prepayment as well. Learn more at [Correct Prepayments](finance-how-to-correct-prepayments.md).

## To cancel a posted sales invoice

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Sales Invoices**, and then choose the related link.  
2. Select the posted sales invoice that you want to cancel.

    > [!NOTE]  
    > If the **Canceled** field is set to **Yes**, the posted sales invoice is already corrected or canceled.
3. On the **Posted Sales Invoice** page, choose the **Cancel** action.

    A sales credit memo is automatically created and posted to void the initial posted sales invoice. The **Canceled** field on the initial posted sales invoice is set to **Yes**.
4. Choose **Show Corrective Credit Memo** to view the posted sales credit memo that voids the initial posted sales invoice.

### Partial invoice posting also supported

If the cancellation is related to a partial invoice posting, the originating sales order line is updated to reflect the canceled invoiced quantity. The **Qty. to Invoice** and **Qty. Invoiced** fields on the related sales order line reset to the values before the partial posting.

## To correct a posted sales invoice

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Posted Sales Invoices**, and then choose the related link.  
2. Select the posted sales invoice that you want to correct.

    > [!NOTE]  
    > If the **Canceled** field is set to **Yes**, the posted sales invoice is already corrected or canceled.
3. On the **Posted Sales Invoice** page, choose the **Correct** action.  

    > [!NOTE]
    > If the sales invoice was posted from a sales order, we recommend that you *cancel* this sales invoice and then process the correction from the original sales order. If the original sales order was deleted, such as if it was fully shipped, you can create a new sales order by using the **Copy Document** action. Learn more at [To create a sales credit memo by copying a posted sales invoice](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-by-copying-a-posted-sales-invoice).
4. A new sales invoice with the same information is created where you can make the correction. The **Canceled** field on the initial posted sales invoice is changed to **Yes**.

    A sales credit memo is automatically created and posted to void the initial posted sales invoice.
5. Choose the **Show Corrective Credit Memo** action to view the posted sales credit memo that voids the initial posted sales invoice.

## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
