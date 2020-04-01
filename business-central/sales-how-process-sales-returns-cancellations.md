---
title: Process Sales Returns or Cancellations | Microsoft Docs
description: Describes how to create a sales credit memo, directly or through a sales return order, to process a return, cancellation, or reimbursement for items or services you have been received payment for.
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
# Process Sales Returns or Cancellations
If a customer wants to return items or be reimbursed for items or services that you have sold and received payment for, you must create and post a sales credit memo that specifies the requested change. To include the correct sales invoice information, you can create the sales credit memo directly from the posted sales invoice or you can create a new sales credit memo with copied invoice information.

If you need more control of the sales return process, such as warehouse documents for the item handling or better overview when receiving items from multiple sales documents with one sales return, then you can create sales return orders. A sales return order automatically issues the related sales credit memo and other return-related documents, such as a replacement sales order, if needed. For more information, see [To create a sales return order based on one or more posted sales documents](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-return-order-based-on-one-or-more-posted-sales-documents).

> [!NOTE]  
>   If a posted sales invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted sales invoice to reverse transactions. These functions work only for unpaid invoices, and they do not support partial returns or cancellations. For more information, see [Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md).

A return or reimbursement may relate to only some of the items or services on the original sales invoice. In that case, you must edit information on the lines on the sales credit memo or sales return order. When you post the sales credit memo or sales return order, the sales documents that are affected by the change are reversed and a refund payment can be created for the customer. For more information, see [Making Payments](payables-make-payments.md).  

In addition to the original posted sales invoice, you can apply the sales credit memo or sales return order to other sales documents, for example another posted sales invoice because the customer is also returning items delivered with that invoice.

You can send the posted sales credit memo to the customer to confirm the return or cancellation and communicate that the related value will be reimbursed, for example when the items are returned.

The credit memo posting will also revert any item charges that were assigned to the posted document, so that the item’s value entries are the same as before the item charge was assigned.

> [!NOTE]
> The bookkeeping aspects of sales returns, such as the payments to customers as reimbursement, is considered bookkeeping work and not described here. For more information, see [Managing Payables](payables-manage-payables.md).

## Inventory Costing
To preserve correct inventory valuation, you typically want to put returned items back in inventory at the unit cost that they were sold at, not at their current unit cost. This is referred to as exact cost reversing.

Two functions exist to assign exact cost reversing automatically.   

|Function|Description|  
|------------------|---------------------------------------|  
|**Get Posted Document Lines to Reverse** function on the **Sales Return Order** page|Copies lines of one or more posted documents to be reversed into the sales return order. For more information, see [To create a sales return order based on one or more posted sales documents](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-return-order-based-on-one-or-more-posted-sales-documents).|  
|**Copy from Document** function in the **Sales Credit Memo** and **Sales Return Order** pages|Copies both the header and lines of one posted document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected on the **Sales & Receivables Setup** page.|

To assign exact cost reversing manually, you must choose the **Appl.-from Item Entry** field on any type of return document line, and then select the number of the original sales entry. This links the sales credit memo or sales return order to the original sales entry and ensures that the item is valued at the original unit cost.

For more information, see [Design Details: Inventory Costing](design-details-inventory-costing.md).

## To create a sales credit memo from a posted sales invoice
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and the choose the related link.  
2. On the **Posted Sales Invoices** page, select the posted sales invoice that you want to reverse, and then choose the **Create Corrective Credit Memo** action.

    The sales credit memo header contains some information from the posted sales invoice. You can edit this, for example, with new information that reflects the return agreement.  
3. Edit information on the lines according to the agreement, such as the number of returned items or the amount to reimburse.
4. Choose the **Apply Entries** action.
5. On the **Apply Customer Entries** page, select the line with the posted sales document that you want to apply the sales credit memo to, and then choose the **Applies-to ID** action.

    The identifier of the sales credit memo displays in the **Applies-to ID** field.
6. In the **Amount to Apply** field, enter the amount that you want to apply if it's smaller than the original amount.  

    At the bottom of the **Apply Customer Entries** page, you can see the total amount to apply to reverse all involved entries, namely when the value in the **Balance** field is zero.
7. Choose the **OK** button. When you post the sales credit memo, it is applied to the posted sales documents.

    After you create or edit sales credit memo lines, and the single or multiple applications are specified, you can post the sales credit memo.   
8. Choose the **Post and Send** action.  

The **Post and Send Confirmation** dialog box opens showing the preferred sending method for the customer. You can change the sending method by choosing the lookup button for the **Send Document** to field. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).  

The posted sales documents that you applied the credit memo to are now reversed, and a refund payment can be created for the customer. The sales credit memo is removed and replaced with a new document in the list of posted sales credit memos.

## To create a sales credit memo by copying a posted sales invoice
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty sales credit memo.
3. In the **Customer** field, enter the name of an existing customer.
4. Choose the **Copy from Document** action.
5. On the **Copy Sales Document** page, in the **Document Type** field, select **Posted Invoice**.
6. Choose the **Document No.** field to open the **Posted Sales Invoices** page, and then select the posted sales invoice that contains lines that you want to reverse.
7. Select the **Recalculate Lines** check box if you want the copied posted sales invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.
8. Choose the **OK** button. The copied invoice lines are inserted in the sales credit memo.
9. Complete the sales credit memo as explained in [To create a sales credit memo from a posted sales invoice](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-from-a-posted-sales-invoice).

## To create a sales return order based on one or more posted sales documents
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Return Orders**, and then choose the related link.
2. Choose the **New** action.  
3. Fill in the fields on the **General** FastTab as necessary.
4. On the **Lines** FastTab, fill the lines manually, or copy information from other documents to fill the lines automatically:

    - Use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents. This function always exactly reverses the costs from the posted document line. This function is described in the following steps.    
    - Use the **Copy from Document** function to copy an existing document to the return order. Use this function to copy the entire document. It can be either a posted document or a document that is not yet posted. This function only enables exact cost reversing when the **Exact Cost Reversing Mandatory** check box is selected on the **Sales and Receivables Setup** page.  

5. Choose the **Get Posted Document Lines to Reverse** action.
6. At the top of the **Posted Sales Document Lines** page, select the **Show Reversible Lines Only** check box if you want to see only lines that have quantities that have not yet been returned. For example, if a posted sales invoice quantity has already been returned, you may not want to return that quantity on a new sales return document.

    > [!NOTE]  
    >  This field only works for posted shipments and posted invoice lines, not for posted return or posted credit memo lines.

    At the left side of the page, the different document types are listed, and the number in brackets shows the number of documents available of each document type.

7. In the **Document Type Filter** field, select the type of posted document lines you would like to use.  
8. Select the lines that you would like to copy to the new document.  

    > [!NOTE]  
    >  If you use Ctrl+A to select all lines, all lines within the filter you have set are copied, but the **Show Reversible Quantity Only** filter is ignored. For example, suppose you have filtered the lines to a particular document number with two lines, one of which has already been returned. Even if the **Show Reversible Quantity Only** field is selected, if you press Ctrl+A to copy all lines, both lines are copied, instead of only the one that has not yet been reversed.  

9. Choose the **OK** button to copy the lines to the new document.  

    The following processes occur:  

    -   For posted document lines of the type **Item**, a new document line is created that is a copy of the posted document line, with the quantity that has not yet been reversed. The **Appl.-from Item Entry** field is filled in as appropriate with the number of the item ledger entry of the posted document line.  

    -   For posted document lines that are not of the type **Item**, such as item charges, a new document line is created that is a copy of the original posted document line.  

    -   Calculates the **Unit Cost (LCY)** field on the new line from the costs on the corresponding item ledger entries.  

    -   If the copied document is a posted shipment, posted receipt, posted return receipt, or posted return shipment, the unit price is calculated automatically from the item card.  

    -   If the copied document is a posted invoice or credit memo, the unit price, invoice discounts, and line discounts from the posted document line are copied.  

    -   If the posted document line contains item tracking lines, the **Appl.-from Item Entry** field on the item tracking lines is filled with the appropriate item ledger entry numbers from the posted item tracking lines.  

     When you copy from a posted invoice or posted credit memo, application copies any relevant invoice discounts and line discounts as valid at the time of posting that document from the posted document line to the new document line. Be aware, however, that if the **Calc. Inv. Discount** option is activated on the **Sales & Receivables Setup** page, then the invoice discount will be newly calculated when you post the new document line. The line amount for the new line may therefore be different than the line amount for the posted document line, depending on the new calculation of the invoice discount.  

     > [!NOTE]  
     >  If part of the quantity of the posted document line has already been reversed or sold or consumed, a line is created for only the quantity that remains in inventory or that has not been returned. If the full quantity of the posted document line has already been reversed, a new document line is not created.  
     >   
     >  If the flow of goods in the posted document is the same as the flow of goods in the new document, a copy of the original posted document line in the new document is created. The **Appl.-from Item Entry** field is not filled in because, in this case, exact cost reversing is not possible. For example, if you use the **Get Posted Document Lines to Reverse** function to get a posted sales credit memo line for a new sales credit memo, only the original posted credit memo line is copied to the new credit memo.  

10. On the **Sales Return Order** page, in the **Return Reason Code** field on each line, select the reason for the return.
11. Choose the **post** action.

## To create a replacement sales order from a sales return order
You may decide to compensate a customer for an item that you have sold them by replacing the item. You can make a replacement with the same item or a different item. This situation could occur if you mistakenly shipped the wrong item to the customer, for example.  

1. On the **Sales Return Order** page for an active return process, on an empty line, make a negative entry for the replacement item by inserting a negative amount in the **Quantity** field.  
2. Choose the **Move Negative Lines** action.
3. On the **Move Negative Sales Lines** page, fill in the fields as necessary.
4. Choose the **OK** button. The negative line for the replacement item is deleted from the sales return order and inserted in a new **Sales Order** page. For more information, see [Sell Products](sales-how-sell-products.md).

## To create return-related documents from a sales return order
You can have replacement sales orders, purchase return orders, and replacement purchase orders created automatically during the sales return process. This is useful, for example, in situations where you want to handle items with warranties provided by vendors.

1. On the **Sales Return Order** page for an active return process, choose the **Create Return-Related Documents** action.
2. In the **Vendor No.** field, enter the number of a vendor if you want to create vendor documents automatically.
3. If a returned item must be returned to the vendor, select the **Create Purch. Ret. Order** check box.
4. If a returned item must be ordered from the vendor, select the **Create Purchase Order** check box.
5. If a replacement sales order must be created, select the **Create Sales Order** check box.

## To create a restock charge
You may decide to charge your customer a restock fee to cover the physical handling costs of returning an item. This could occur if the customer mistakenly ordered the wrong item or changed their mind after receiving the item you sold them, for example.

You can post this increased cost as an item charge in a credit memo or a return order and assign it to the posted shipment. The following describes it for a sales return order, but the same steps apply to a sales credit memo.

1. Open the **Sales Return Order** page for an active return process.
2. On a new line, in the **Type** field, select **Charge (Item)**.  
3. Fill in the fields as for any item charge line. For more information, see [Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md).  

When you post the sales return order, the restock charge is added to the relevant sales entry amount. In this way, you can maintain accurate inventory valuation.  

## To create a sales allowance
You can send a customer a credit memo with a price reduction if the customer has received slightly damaged items or received the items late.  
You can post this reduced price as an item charge in a credit memo or a return order and assign it to the posted shipment. The following describes it for a sales credit memo, but the same steps apply to a sales return order.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty sales credit memo.
3. Fill in the credit memo header with relevant information about the customer that you want to give the sales allowance to.  
4. On the **Lines** FastTab, in the **Type** field, select **Charge (Item)**.  
5.  In the **No.** field, select the appropriate item charge value.  
     You may want to create a special item charge number to cover sales allowances.  
6.  In the **Quantity** field, enter **1**.  
7.  In the **Unit Price** field, enter the amount of the sales allowance.  
8.  Assign the sales allowance as an item charge to the items in the posted shipment. For more information, see [Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md). When you have assigned the allowance, return to the **Sales Credit Memo** page.  

When you post the sales return order, the sales allowance is added to the relevant sales entry amount. In this way, you can maintain accurate inventory valuation.

## To combine return receipts
You can combine return receipts if your customer returns several items that are covered by different sales return orders.  

When you receive the items into your warehouse, post the relevant sales return orders as received. This creates posted return receipts.  

When you are ready to invoice this customer, instead of invoicing each sales return order separately, you can create a sales credit memo and automatically copy the posted return receipt lines to this document. Then you can post the sales credit memo and conveniently invoice all the open sales return orders at once.  

To combine return receipts, the **Combine Shipments** check box must be selected on the **Customer Card** page.  

### To manually combine return receipts  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Credit Memo**, and then choose the related link.  
2. Choose the **New** action.
3. On the **General** FastTab, fill in the fields as necessary.  
4. Choose the **Get Return Receipt Lines** action.  
5. Select the return receipt lines that you want to include in the credit memo:  

    -   To insert all lines, select all lines, and then choose the **OK** button.  

    -   To insert specific lines, select the lines, and then choose the **OK** button.  

6.  If an incorrect shipment line was selected or you want to start over, you can simply delete the lines on the credit memo and re-run the **Get Return Receipt Lines** function.  
7.  Post the invoice.  

### To automatically combine return receipts  
You can automatically combine return receipts and have the option of automatically posting the credit memos using the  **Combine Return Receipts** function.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Combine Return Receipts**, and then choose the related link.
2. On the **Combine Return Receipts** page, fill in the fields to select the relevant return receipts.
3. Select the **Post Credit Memos** check box. If not, you must manually post the resulting purchase credit memos.
4.  Choose the **OK** button.  

### To remove a received and invoiced return order  
When you invoice return receipts in this way, the return orders from which the return receipts were posted still exist, even if they have been fully received and invoiced.  

When return receipts are combined on a credit memo and posted, a posted sales credit memo is created for the credited lines. The **Quantity Invoiced** field on the originating sales return order is updated based on the invoiced quantity.   
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Sales Return Orders**, and then select the link.  
2.  Specify in the **No.** filter field which return orders to delete.  
3.  Choose the **OK** button.  

Alternatively, delete individual sales return orders manually.   

## See Related Training at [Microsoft Learn](/learn/paths/return-items-dynamics-365-business-central/)

## See Also
[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Managing Payables](payables-manage-payables.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
