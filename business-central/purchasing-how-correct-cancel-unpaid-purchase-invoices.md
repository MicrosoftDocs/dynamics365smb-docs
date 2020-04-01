---
title: Amend or Cancel Unpaid Purchase Invoices | Microsoft Docs
description: Explains how to correct, cancel, or undo a posted purchase invoice and automatically create a purchase credit memo.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 04/01/2020
ms.author: sgroespe

---
# Correct or Cancel Unpaid Purchase Invoices
You can correct or cancel a posted purchase invoice. This is useful if you want to correct a typing mistake, or if you want to change the purchase early in the order process.

If you have already paid for products on the posted purchase invoice, you cannot correct or cancel it from the posted purchase invoice itself. Instead, you must manually create a purchase credit memo to reverse the purchase, optionally managed with a purchase return order. For more information, see [Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md).

On the **Posted Purchase Invoice** page, you can choose the **Correct** button or the **Cancel** button. When you correct or cancel a posted purchase invoice, the corrective purchase credit memo is applied to all general ledger and inventory ledger entries that were created when the initial purchase invoice was posted. This reverses the posted purchase invoice in your financial records and leaves the corrective posted purchase credit memo for your audit trail. In the following the use of **Correct** and **Cancel** is described.
<br><br>
> [!Video https://www.microsoft.com/videoplayer/embed/RE4dhoc?rel=0]

## To correct a posted purchase invoice
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Invoices**, and then choose the related link.  
2. Select the posted purchase invoice that you want to correct.  

    > [!NOTE]  
    >   If the **Canceled** check box is selected, then you cannot correct the posted purchase invoice because it has already been corrected or canceled.
3. On the **Posted Purchase Invoice** page, choose **Correct**.

    A new purchase invoice with the same information is created where you can make the correction. For more information, see [Record Purchases](purchasing-how-record-purchases.md). The **Canceled** field on the initial posted purchase invoice is changed to **Yes**.

    A purchase credit memo is automatically created and posted to void the initial posted purchase invoice.
4. Choose **Show Corrective Credit Memo** to view the posted purchase credit memo that voids the initial posted purchase invoice.

## To cancel a posted purchase invoice
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Invoices**, and then choose the related link.  
2. Select the posted purchase invoice that you want to cancel.

    > [!NOTE]  
    >   If the **Canceled** check box is selected, then you cannot cancel the posted purchase invoice because it has already been canceled or corrected.
3. On the **Posted Purchase Invoice** page, choose **Cancel**.

    A purchase credit memo is automatically created and posted to void the initial posted purchase invoice. The **Canceled** field on the initial posted purchase invoice is changed to **Yes**.
4. Choose **Show Corrective Credit Memo** to view the posted purchase credit memo that voids the initial posted purchase invoice.

### Partial Invoice Posting also Supported
If the cancellation is related to a partial invoice posting, then the originating purchase order line is updated to reflect the canceled invoiced quantity. The **Qty. to Invoice** and **Qty. Invoiced** fields on the related purchase order line are reset to the values before the partial posting.

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
