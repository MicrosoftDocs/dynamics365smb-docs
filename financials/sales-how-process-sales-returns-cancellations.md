---
title: Using a Sales Credit Memo to Process Sales Returns or Cancellations | Microsoft Docs
description: Describes how to create a sales credit memo to process a return, cancellation, or reimbursement for items or services you have been received payment for.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 06/21/2016
ms.author: sgroespe

---
# How to: Process Sales Returns or Cancellations
If a customer wants to return or be reimbursed for items or services that you have sold and received payment for, you must create and post a sales credit memo that specifies the requested change. To include the correct sales invoice information, you can create the sales credit memo from the posted sales invoice, or use a copy function.  

> [!NOTE]  
>   If a posted sales invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted sales invoice to reverse transactions. These functions work only for unpaid invoices, and they do not support partial returns or cancellations. For more information, see [How to: Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md).

In addition to the original posted sales invoice, you can apply the sales credit memo to other sales documents, for example another posted sales invoice, because the customer is also returning items delivered with that invoice.

A return or reimbursement may relate to only some of the items or services on the original sales invoice. In that case, you must edit information on the lines on the sales credit memo. When you post the sales credit memo, the sales documents that are affected by the change are reversed and a refund payment can be created for the customer.  

You can send the posted sales credit memo to the customer to confirm the return or cancellation and communicate that the related value will be reimbursed, for example when the items are returned.

The credit memo posting will also revert any item charges that were assigned to the posted document, so that the item’s value entries are the same as before the item charge was assigned.

## To create a sales credit memo from a posted sales invoice
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Sales Invoices**, and the choose the related link.  
2. In the **Posted Sales Invoices** window, select the posted sales invoice that you want to reverse, and then choose the **Create Corrective Credit Memo** action.

    The sales credit memo header contains some information from the posted sales invoice. You can edit this, for example, with new information that reflects the return agreement.  
3. Edit information on the lines according to the agreement, such as the number of returned items or the amount to reimburse.
4. Choose the **Apply Entries** action.
5. In the **Apply Customer Entries** window, select the line with the posted sales document that you want to apply the sales credit memo to, and then choose the **Applies-to ID** action.

    The identifier of the sales credit memo displays in the **Applies-to ID** field.
6. In the **Amount to Apply** field, enter the amount that you want to apply if it's smaller than the original amount.  

    At the bottom of the **Apply Customer Entries** window, you can see the total amount to apply to reverse all involved entries, namely when the value in the **Balance** field is zero.
7. Choose the **OK** button. When you post the sales credit memo, it is applied to the posted sales documents.

    After you create or edit sales credit memo lines, and the single or multiple applications are specified, you can post the sales credit memo.   
8. Choose the **Post and Send** action.  

The **Post and Send Confirmation** dialog box opens showing the preferred sending method for the customer. You can change the sending method by choosing the lookup button for the **Send Document** to field. For more information, see [How to: Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).  

The posted sales documents that you applied the credit memo to are now reversed, and a refund payment can be created for the customer. The sales credit memo is removed and replaced with a new document in the list of posted sales credit memos.

## To create a sales credit memo from scratch
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty sales credit memo.
3. In the **Customer** field, enter the name of an existing customer.
4. Choose the **Copy Document** action.
5. In the **Copy Sales Document** window, in the **Document Type** field, select **Posted Invoice**.
6. Choose the **Document No.** field to open the **Posted Sales Invoices** window, and then select the posted sales invoice that contains lines that you want to reverse.
7. Select the **Recalculate Lines** check box if you want the copied posted sales invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.
8. Choose the **OK** button. The copied invoice lines are inserted in the sales credit memo.
9. Complete the sales credit memo as explained in the "To create a sales credit memo from a posted sales invoice" section in this topic.

## See Also
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[How to: Send Documents by Email](ui-how-send-documents-email.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
