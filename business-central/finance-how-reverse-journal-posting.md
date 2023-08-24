---
title: Undo a Posting by Posting a Reversing Entry
description: If you find a mistake in a posted general journal, you can use the Reverse Transaction action to undo the posting with a correct audit trail.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 03/28/2023
ms.custom: bap-template
---
# Reverse Journal Postings and Undo Receipts/Shipments

Reverse journal postings are useful, for example, for correcting errors and for clearing out an old accruals entry before entering a new one. A reverse entry is the same as the original entry, but has an opposite sign in the **Amount** field. The reverse entry must have the same document number and posting date as the original entry. After you reverse an entry, you must make the correct entry.

You can only reverse entries that are posted from a general journal line. An entry can only be reversed one time.

To undo a receipt or shipment posting, before they're posted as invoiced, you can use the **Undo** function on the posted document. You can undo quantities of type **Item** and **Resource**.

If you've posted an incorrect negative quantity, such as a purchase order with the wrong number of items, as received but not invoiced, you can undo the posting.

If you've posted an incorrect positive quantity, such as a sales shipment or a purchase return shipment with the wrong number of items, as shipped but not invoiced, you can undo the posting.

## To reverse the journal posting of a general ledger entry

You can reverse entries from all **Ledger Entries** pages. The following procedure is based on the **General Ledger Entries** page.

> [!NOTE]
> The entry must originate from a journal posting.
>
> Also, you can't reverse entries that have been posted with information from a job, or which have realized gains and losses within the same transaction.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Entries**, and then choose the related link.
2. Select the entry that you want to reverse, and then choose the **Reverse Transaction** action.
3. On the **Reverse Transaction Entries** page, choose the **Reverse** action.
4. Choose **Yes** to confirm the reversal.

## To post a negative entry  

Use the **Correction** field to post a negative debit instead of a credit, or to post a negative credit instead of a debit on an account. By default, the field is available in all journals. The **Debit Amount** and **Credit Amount** fields include both the original entry, and the corrected entry. These fields have no effect on the account balance.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link  
2. In the **Batch Name** field, select the required batch name.  
3. Enter information into the relevant fields.  
4. In the journal line that you want to activate for negative entries, select the **Correction** check box.  
5. To post the journal, choose the **Post** action, and then choose the **Yes** button.

## To undo a quantity on a posted purchase receipt  

The following steps describe how to undo a posted receipt of items or resources. The steps are similar for posted shipments.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Receipts**, and then choose the related link.  
2. Open the posted receipt that you want to undo.  
3. Select the line or lines that you want to undo.  
4. Choose **Undo Receipt** action.

A corrective line is added under the selected receipt line. If the quantity was received in a warehouse receipt, then a corrective line is added on the posted warehouse receipt.  

The **Quantity Received** and **Qty. Rcd. Not Invoiced** fields on the related purchase order are set to zero.

## To undo and then redo a quantity posting on a posted return shipment

The following steps describe how to:

* Undo a posted return shipment of items or resources.
* Re-post the purchase return with a new quantity.

The steps are similar for posted return receipts.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Return Shipments**, and then choose the related link.  
2. Open the posted return shipment to undo.
3. Select the line or lines to undo.  

4. Choose the **Undo Return Shipment** action.  

    A corrective line is inserted in the posted document, and the **Return Qty. Shipped** and **Return Shpd. Not Invd.** fields on the return order are set to zero.  

    Now go back to the purchase return order to redo the posting.  

5. On the **Posted Return Shipment** page, take a note of the number in the **Return Order No.** field.  
6. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Return Orders**, and then select the related link.  
7. Open the return order in question, and then choose the **Reopen** action.  
8. Correct the entry in the **Quantity** field and post the purchase return order again.  

[!INCLUDE [rev-general-journal](includes/rev-general-journal.md)]

## See Also

[Undo Assembly Posting](assembly-how-to-undo-assembly-posting.md)  
[Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]