---
title: Process sales returns or cancellations
description: Describes how to create a sales credit memo to process a return, cancellation, or reimbursement for items or services you have received payment for.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: undo, credit memo, return
ms.search.form: 44, 134, 143, 6629, 6630, 6633, 6662, 9302, 9304, Report_6646
ms.date: 02/26/2024
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Process sales returns or cancellations

If a customer wants to return items or be reimbursed for items or services that you have sold and received payment for, you must create and post a sales credit memo that specifies the requested change. To include the correct sales invoice information, you can do the following tasks:  

- Create the sales credit memo directly from the posted sales invoice.
- Create a new sales credit memo with copied invoice information.

If you need more control of the sales return process, such as warehouse documents for the item handling, or a better overview when receiving items from multiple sales documents with one sales return, then you can create sales return orders. A sales return order automatically issues the related sales credit memo and other return-related documents, such as a replacement sales order, if needed. For more information, see [Process sales return orders](sales-how-process-sales-returns-orders.md).

> [!NOTE]  
> If a posted sales invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted sales invoice to reverse transactions. These functions only work for unpaid invoices, and they do not support partial returns or cancellations. For more information, see [Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md).

A return or reimbursement might relate to only some of the items or services on the original sales invoice. In that case, you must edit information on the lines on the sales credit memo or sales return order. When you post the sales credit memo or sales return order, the sales documents that are affected by the change are reversed and a refund payment can be created for the customer. For more information, see [Making Payments](payables-make-payments.md).  

The credit memo posting will also revert any item charges that were assigned to the posted document, so that the item's value entries are the same as before the item charge was assigned.

> [!NOTE]
> The bookkeeping aspects of sales returns, such as the payments to customers as reimbursement, is considered bookkeeping work and not described here. For more information, see [Managing Payables](payables-manage-payables.md).

## To create a sales credit memo from a posted sales invoice  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoices**, and then choose the related link.  
2. On the **Posted Sales Invoices** page, select the posted sales invoice that you want to reverse, choose the **Cancel** action, and then choose the **Create Corrective Credit Memo** action.

    The sales credit memo header contains some information from the posted sales invoice. You can edit this, for example, with new information that reflects the return agreement.  
3. Edit information on the lines according to the agreement, such as the number of returned items or the amount to reimburse.
4. Choose the **Prepare** action, and then choose the **Apply Entries** action.
5. On the **Apply Customer Entries** page, select the line with the posted sales document that you want to apply the sales credit memo to, and then choose the **Applies-to ID** action.

    The identifier of the sales credit memo displays in the **Applies-to ID** field.
6. In the **Amount to Apply** field, enter the amount that you want to apply if it's smaller than the original amount.  

    At the bottom of the **Apply Customer Entries** page, you can see the total amount to apply to reverse all involved entries, namely when the value in the **Balance** field is zero.
7. Choose the **OK** button. When you post the sales credit memo, it is applied to the posted sales documents.

    After you create or edit sales credit memo lines, and the single or multiple applications are specified, you can post the sales credit memo.  
8. Choose the **Posting** action, then choose the **Post and Send** action.  

The **Post and Send Confirmation** dialog box opens showing the preferred sending method for the customer. You can change the sending method by choosing the lookup button for the **Send Document** to field. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).  

The posted sales documents that you applied the credit memo to are now reversed, and a refund payment can be created for the customer. The sales credit memo is removed and replaced with a new document in the list of posted sales credit memos.

## To create a sales credit memo by copying a posted sales invoice

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty sales credit memo.
3. In the **Customer Name** field, enter the name of an existing customer.
4. Choose the **Prepare** action, then choose the **Copy Document** action.
5. On the **Copy Sales Document** page, in the **Document Type** field, select **Posted Invoice**.
6. Choose the **Document No.** field to open the **Posted Sales Invoices** page, and then select the posted sales invoice record that contains lines that you want to reverse.
7. Select the **Recalculate Lines** check box if you want the copied posted sales invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.
8. Choose the **OK** button. The copied invoice lines are inserted in the sales credit memo.
9. Complete the sales credit memo as explained in [To create a sales credit memo from a posted sales invoice](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-from-a-posted-sales-invoice).

## To create a sales allowance
You can send a customer a credit memo with a price reduction if the customer has received slightly damaged items or received the items late.  
You can post this reduced price as an item charge in a credit memo or a return order and assign it to the posted shipment. The following describes it for a sales credit memo, but the same steps apply to a sales return order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty sales credit memo.
3. Fill in the credit memo header with relevant information about the customer that you want to give the sales allowance to.  
4. On the **Lines** FastTab, in the **Type** field, select **Charge (Item)**.  
5. In the **No.** field, select the appropriate item charge value.  
     You might want to create a special item charge number to cover sales allowances.  
6. In the **Quantity** field, enter **1**.  
7. In the **Unit Price Excl. Tax** field, enter the amount of the sales allowance.  
8. Assign the sales allowance as an item charge to the items in the posted shipment. For more information, see [Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md). When you have assigned the allowance, return to the **Sales Credit Memo** page.  

When you post the sales return order, the sales allowance is added to the relevant sales entry amount. In this way, you can maintain accurate inventory valuation.

## To combine return receipts
You can combine return receipts if your customer returns several items that are covered by different sales return orders.  

When you receive the items into your warehouse, post the relevant sales return orders as received. This creates posted return receipts.  

When you're ready to invoice this customer, instead of invoicing each sales return order separately, you can create a sales credit memo and automatically copy the posted return receipt lines to this document. Then you can post the sales credit memo and conveniently invoice all the open sales return orders at once.  

To combine return receipts, the **Combine Shipments** check box must be selected on the **Customer Card** page.  

### To manually combine return receipts  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Credit Memos**, and then choose the related link.  
2. Choose the **New** action.
3. On the **General** FastTab, fill in the fields as necessary.  
4. Choose the **Get Return Receipt Lines** action.  
5. Select the return receipt lines that you want to include in the credit memo:  

    - To insert all lines, select all lines, and then choose the **OK** button.  

    - To insert specific lines, select the lines, and then choose the **OK** button.  
6.  If an incorrect shipment line was selected or you want to start over, you can simply delete the lines on the credit memo and rerun the **Get Return Receipt Lines** function.  
7.  Post the invoice.  

### To automatically combine return receipts

You can automatically combine return receipts and have the option of automatically posting the credit memos using the  **Combine Return Receipts** function.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Combine Return Receipts**, and then choose the related link.
2. On the **Combine Return Receipts** page, fill in the fields to select the relevant return receipts.
3. Select the **Post Credit Memos** check box. If not, you must manually post the resulting purchase credit memos.
4. Choose the **OK** button.  

### To remove a received and invoiced return order

When you invoice return receipts in this way, the return orders from which the return receipts were posted still exist, even if they have been fully received and invoiced.  

When return receipts are combined on a credit memo and posted, a posted sales credit memo is created for the credited lines. The **Quantity Invoiced** field on the originating sales return order is updated based on the invoiced quantity.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Sales Return Orders**, and then choose the related link.  
2. Specify in the **No.** filter field which return orders to delete.  
3. Choose the **OK** button.  

Alternatively, delete individual sales return orders manually.  

## Inventory costing

To preserve correct inventory valuation, you typically want to put returned items back in inventory at the unit cost that they were sold at, not at their current unit cost. This is referred to as exact cost reversing.

Two functions exist to assign exact cost reversing automatically:  

|Function|Description|  
|------------------|---------------------------------------|  
|**Get Posted Document Lines to Reverse** function on the **Sales Return Order** page|Copies lines of one or more posted documents to be reversed into the sales return order. For more information, see [Create a sales return order based on one or more posted sales documents](sales-how-process-sales-returns-orders.md#create-a-sales-return-order-based-on-one-or-more-posted-sales-documents).|  
|**Copy Document** function in the **Sales Credit Memo** and **Sales Return Order** pages|Copies both the header and lines of one posted document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected on the **Sales & Receivables Setup** page.|

To assign exact cost reversing manually, you must choose the **Appl.-from Item Entry** field on any type of return document line, and then select the number of the original sales entry. This links the sales credit memo or sales return order to the original sales entry and ensures that the item is valued at the original unit cost.

For more information, see [Design Details: Inventory Costing](design-details-inventory-costing.md).

## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Managing Payables](payables-manage-payables.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
