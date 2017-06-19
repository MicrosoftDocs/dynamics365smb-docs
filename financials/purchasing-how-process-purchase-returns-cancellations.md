---
title: Use Purchase Credit Memos to Process Returns or Cancellations | Microsoft Docs
description: Explains how to create and post a purchase credit memo when you want to return items to a vendor or cancel purchased services.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cancel, undo, correct
ms.date: 04/25/2017
ms.author: sgroespe

---
# How to: Process Purchase Returns or Cancellations
If you want to return items to your vendor or cancel services that you have purchased, then you can create and post a purchase credit memo that specifies the requested change with regard to the original purchase invoice. To include the correct purchase invoice information, you can create the purchase credit memo from the posted purchase invoice or use a copy function.

> [!NOTE]  
>   If a posted purchase invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted purchase invoice to automatically reverse the involved transactions. These functions only work for unpaid invoices, and they do not support partial returns or cancellations. For more information, see [How to: Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

Typically, you create a purchase credit memo in reaction to a credit memo sent to you by a vendor. The purchase credit memo functions as your internal documentation of the credit memo process for accounting purposes.

The change may relate to all the products on the original purchase invoice or only to some of the products. Accordingly, you can partially return received items or demand partial reimbursement of received services. In that case, you must edit the copied purchase invoice information.

In addition to the original posted purchase invoice, you can apply the purchase credit memo to other purchase documents, for example another posted purchase invoice, because you are also returning items delivered with that invoice.

The credit memo posting will also revert any item charges that were assigned to the posted document, so that the item’s value entries are the same as before the item charge was assigned. 

## To create a purchase credit memo from a posted purchase invoice
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Credit Memos**, and then choose the related link.  
2. In the **Posted Purchase Invoices** window, select the posted purchase invoice that you want to reverse, and then choose the **Create Corrective Credit Memo** action.

    Most fields on the purchase credit memo header are filled with the information from the posted purchase invoice. You can edit all the fields, for example with new information that reflects the return agreement.
3. Edit information on the lines according to the agreement, such as the number of items returned or the amount to be reimbursement.
4. Choose the **Apply Entries** action.
5. In the **Apply Vendor Entries** window, select the line with the posted purchase document that you want to apply the purchase credit memo to, and then choose the **Applies-to ID** action. The number of the purchase credit memo is inserted in the **Applies-to ID** field.
6. In the **Amount to Apply** field, enter the amount that you want to apply if smaller than the original amount.

    At the bottom of the **Apply Vendor Entries** window, you can see the total amount to apply to reverse all involved entries, namely when the value in the **Balance** field is zero.
7. Choose the **OK** button. When you post the purchase credit memo, it will be applied to the specified posted purchase documents.

    When you have created or edited the needed purchase credit memo lines and the single or multiple applications are specified, you can proceed to post the purchase credit memo.
8. Choose the **Post** action.

The posted purchase invoices that you apply the credit memo to are now reversed. If you have already paid the original invoice, the vendor should now refund the payment to you. If the credit memo is only for part of the product on the original invoice, you may only pay the remaining amount on the original purchase invoice to close it.

The purchase credit memo is removed and replaced with a new document in the list of posted purchase credit memos.

## To create a purchase credit memo from scratch
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Purchase Invoices**, and then choose the related link.
2. Choose the **New** action to open a new empty purchase credit memo.
3. In the **Vendor** field, enter the name of an existing vendor.
4. Choose the **Copy Document** action.
5. In the **Copy purchase Document** window, in the **Document Type** field, select **Posted Invoice**.
6. Choose the **Document No.** field to open the **Posted purchase Invoices** window, and then select the posted purchase invoice that contains lines that you want to reverse.
7. Select the **Recalculate Lines** check box if you want the copied posted purchase invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.
8. Choose the **OK** button. The copied invoice lines are inserted in the purchase credit memo.
9. Complete the purchase credit memo as explained in the "To create a purchase credit memo from a posted purchase invoice" section in this topic.

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[How to: Record Purchases](purchasing-how-record-purchases.md)  
[How to: How to: Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
