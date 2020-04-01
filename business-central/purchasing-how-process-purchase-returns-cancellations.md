---
title: Process Returns or Cancellations | Microsoft Docs
description: Explains how to create and post a purchase credit memo when you want to return items to a vendor or cancel purchased services.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cancel, undo, correct
ms.date: 04/01/2020
ms.author: sgroespe

---
# Process Purchase Returns or Cancellations
If you want to return items to your vendor or cancel services that you have purchased, then you can create and post a purchase credit memo that specifies the requested change with regard to the original purchase invoice. To include the correct purchase invoice information, you can create the purchase credit memo directly from the posted purchase invoice or you can create a new purchase credit memo with copied invoice information.

If you need more control of the purchase return process, such as warehouse documents for the item handling or better overview when shipping back items from multiple purchase documents with one purchase return, then you can create purchase return orders. A purchase return order automatically issues the related purchase credit memo. For more information, see [To create a purchase return order based on one or more a posted purchase documents](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice).

> [!NOTE]  
>   If a posted purchase invoice has not yet been paid, then you can use the **Correct** or **Cancel** functions on the posted purchase invoice to automatically reverse the involved transactions. These functions only work for unpaid invoices, and they do not support partial returns or cancellations. For more information, see [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

Typically, you create a purchase credit memo or purchase return order in reaction to a credit memo sent to you by a vendor. The purchase credit memo or purchase return order functions as your internal documentation of the credit memo process for accounting purposes or to control the shipping of the involved items.

The change may relate to all the products on the original purchase invoice or only to some of the products. Accordingly, you can partially return received items or demand partial reimbursement of received services. In that case, you must edit the information on the purchase credit memo or purchase return order.

In addition to the original posted purchase invoice, you can apply the purchase credit memo or purchase return order to other purchase documents, for example another posted purchase invoice because you are also returning items delivered with that invoice.

The credit memo posting will also revert any item charges that were assigned to the posted document, so that the item’s value entries are the same as before the item charge was assigned.

## Inventory Costing
To preserve correct inventory valuation, you typically want to pick return items from inventory at the unit cost that they were purchased at, not at their current unit cost. This is referred to as exact cost reversing.

Two functions exist to assign exact cost reversing automatically.  

|Function|Description|  
|------------------|---------------------------------------|  
|**Get Posted Document Lines to Reverse** function on the **Purchase Return Order** page|Copies lines of one or more posted documents to be reversed into the purchase return order. For more information, see [To create a purchase return order based on one or more posted purchase documents](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-return-order-based-on-one-or-more-posted-purchase-documents).|  
|**Copy from Document** function in the **Purchase Credit Memo** and **Purchase Return Order** pages|Copies both the header and lines of one posted document to be reversed.<br /><br /> Requires that the **Exact Cost Reversing Mandatory** check box is selected on the **Purchases & Payables Setup** page.|

To assign exact cost reversing manually, you must choose the **Appl.-from Item Entry** field on any type of return document line, and then select the number of the original purchase entry. This links the purchase credit memo or purchase return order to the original purchase sales entry and ensures that the item is valued at the original unit cost.

For more information, see [Design Details: Inventory Costing](design-details-inventory-costing.md).

## To create a purchase credit memo from a posted purchase invoice
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Invoices**, and then choose the related link.  
2. On the **Posted Purchase Invoices** page, select the posted purchase invoice that you want to reverse, and then choose the **Create Corrective Credit Memo** action.

    Most fields on the purchase credit memo header are filled with the information from the posted purchase invoice. You can edit all the fields, for example with new information that reflects the return agreement.
3. Edit information on the lines according to the agreement, such as the number of items returned or the amount to be reimbursement.
4. Choose the **Apply Entries** action.
5. On the **Apply Vendor Entries** page, select the line with the posted purchase document that you want to apply the purchase credit memo to, and then choose the **Applies-to ID** action. The number of the purchase credit memo is inserted in the **Applies-to ID** field.
6. In the **Amount to Apply** field, enter the amount that you want to apply if smaller than the original amount.

    At the bottom of the **Apply Vendor Entries** page, you can see the total amount to apply to reverse all involved entries, namely when the value in the **Balance** field is zero.
7. Choose the **OK** button. When you post the purchase credit memo, it will be applied to the specified posted purchase documents.

    When you have created or edited the needed purchase credit memo lines and the single or multiple applications are specified, you can proceed to post the purchase credit memo.
8. Choose the **Post** action.

The posted purchase invoices that you apply the credit memo to are now reversed. If you have already paid the original invoice, the vendor should now refund the payment to you. If the credit memo is only for part of the product on the original invoice, you may only pay the remaining amount on the original purchase invoice to close it.

The purchase credit memo is removed and replaced with a new document in the list of posted purchase credit memos.

## To create a purchase credit memo by copying a posted purchase invoice
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty purchase credit memo.
3. In the **Vendor** field, enter the name of an existing vendor.
4. Choose the **Copy from Document** action.
5. On the **Copy Purchase Document** page, in the **Document Type** field, select **Posted Invoice**.
6. Choose the **Document No.** field to open the **Posted Purchase Invoices** page, and then select the posted purchase invoice that contains lines that you want to reverse.
7. Select the **Recalculate Lines** check box if you want the copied posted purchase invoice lines to be updated with any changes in item price and unit cost since the invoice was posted.
8. Choose the **OK** button. The copied invoice lines are inserted in the purchase credit memo.
9. Complete the purchase credit memo as explained in [To create a purchase credit memo from a posted purchase invoice](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice).

## To create a purchase return order based on one or more posted purchase documents
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Return Orders**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields on the **General** FastTab as necessary.
4. On the **Lines** FastTab, fill the lines manually, or copy information from other documents to fill the lines automatically:

    - Use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents. This function always exactly reverses the costs from the posted document line. This function is described in the following steps.    
    - Use the **Copy from Document** function to copy an existing document to the return order. Use this function to copy the entire document. It can be either a posted document or a document that is not yet posted. This function only enables exact cost reversing when the **Exact Cost Reversing Mandatory** check box is selected on the **Sales and Receivables Setup** page.  

4. Choose the **Get Posted Document Lines to Reverse** action.
5. At the top of the **Posted Purchase Document Lines** page, select the **Show Reversible Lines Only** check box if you want to see only lines that have quantities that have not yet been returned. For example, if a posted purchase invoice quantity has already been returned, you may not want to include that quantity on a new purchase return document.

    > [!NOTE]  
    >  This field only works for posted receipts and posted invoice lines, not for posted return or posted credit memo lines.  

    At the left side of the page, the different document types are listed, and the number in brackets shows the number of documents available of each document type.

6. In the **Document Type Filter** field, select the type of posted document lines you would like to use.  
7. Select the lines that you would like to copy to the new document.  

    > [!NOTE]  
    >  If you use Ctrl+A to select all lines, all lines within the filter you have set are copied, but the **Show Reversible Quantity Only** filter is ignored. For example, suppose you have filtered the lines to a particular document number with two lines, one of which has already been returned. Even if the **Show Reversible Quantity Only** field is selected, if you press Ctrl+A to copy all lines, both lines are copied, instead of only the one that has not yet been reversed.  

8. Choose the **OK** button to copy the lines to the new document.  

    The following processes occur:  

    -   For posted document lines of the type **Item**, a new document line is created that is a copy of the posted document line, with the quantity that has not yet been reversed. The **Appl.-to Item Entry** field is filled in as appropriate with the number of the item ledger entry of the posted document line.  

    -   For posted document lines that are not of the type **Item**, such as item charges, a new document line is created that is a copy of the original posted document line.  

    -   Calculates the **Unit Cost (LCY)** field on the new line from the costs on the corresponding item ledger entries.  

    -   If the copied document is a posted shipment, posted receipt, posted return receipt, or posted return shipment, the unit price is calculated automatically from the item card.  

    -   If the copied document is a posted invoice or credit memo, the unit price, invoice discounts, and line discounts from the posted document line are copied.  

    -   If the posted document line contains item tracking lines, the **Appl.-to Item Entry** field on the item tracking lines is filled with the appropriate item ledger entry numbers from the posted item tracking lines.  

     When you copy from a posted invoice or posted credit memo, application copies any relevant invoice discounts and line discounts as valid at the time of posting that document from the posted document line to the new document line. Be aware, however, that if the **Calc. Inv. Discount** option is activated on the **Purchases & Payables Setup** page, then the invoice discount will be newly calculated when you post the new document line. The line amount for the new line may therefore be different than the line amount for the posted document line, depending on the new calculation of the invoice discount.  

    > [!NOTE]  
    >  If part of the quantity of the posted document line has already been reversed or sold or consumed, a line is created for only the quantity that remains in inventory or that has not been returned. If the full quantity of the posted document line has already been reversed, a new document line is not created.  
    >   
    >  If the flow of goods in the posted document is the same as the flow of goods in the new document, a copy of the original posted document line in the new document is created. The **Appl.-from Item Entry** field is not filled in because, in this case, exact cost reversing is not possible. For example, if you use the **Get Posted Document Lines to Reverse** function to get a posted purchase credit memo line for a new purchase credit memo, only the original posted credit memo line is copied to the new credit memo.  

8. On the **Purchase Return Order** page, in the **Return Reason Code** field on each line, select the reason for the return.
9. Choose the **Post** action.

## To create a replacement purchase order from a purchase return order
You may agree with your vendor that they compensate you for a purchased item by replacing the item. The replacement item can be the same or it can be different. This situation could occur if the vendor mistakenly shipped the wrong item.  
1.  On the **Purchase Return Order** page for an active return process, on an empty line, make a negative entry for the replacement item by inserting a negative amount in the **Quantity** field.  
2. Choose the **Move Negative Lines** action.  
3. On the **Move Negative Purchase Lines** page, fill in the fields as necessary.
4. Choose the **OK** button. The negative line is deleted from the purchase return order, and a new purchase order is created. For more information, see [Record Purchases](purchasing-how-record-purchases.md).  

## To create a purchase allowance  
If you receive items from your vendor that are not what you wanted, for example, if they are slightly damaged, the wrong color or the wrong size, the vendor may offer you a purchase allowance.  

You can post this reduced purchase cost as an item charge on a credit memo or return order and link it to the posted receipt. The following describes it for a purchase return order, but the same steps apply to a purchase credit memo.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memos**, and then choose the related link.
2. Choose the **New** action to open a new empty purchase credit memo.  
3.  Fill in the credit memo header with information about the vendor who sent you the purchase allowance.  
4. On the **Lines** FastTab, in the **Type** field, select **Charge (Item)**.  
5.  In the **No.** field, select the appropriate item charge value.  

    You may want to create a special item charge number to cover purchase allowances.  
6.  In the **Quantity** field, enter **1**.  
7.  In the **Direct Unit Cost** field, enter the amount of the purchase allowance.  
8.  Assign the purchase allowance as an item charge to the items in the posted receipt. For more information, see [Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md). When you have assigned the allowance, return to the **Purchase Credit Memo** page.

When you post the purchase return order, the purchase allowance is added to the relevant purchase entry amount. In this way, you can maintain accurate inventory valuation.  

## To combine return shipments  
If you want to return items covered by different purchase return orders to the same vendor, then you can use the **Combine Return Shipments** function.  

When you ship the items, you post the related purchase return orders as shipped and this creates posted purchase return shipments.  

When you are ready to invoice these items, instead of invoicing each purchase return order separately, you can create a purchase credit memo and automatically copy the posted purchase return shipment lines to this document. Then you can post the purchase credit memo and conveniently invoice all the open purchase return orders at the same time.  

When return shipments are combined on a credit memo and posted, then a posted purchase credit memo is created for the invoiced lines. The **Quantity Invoiced** field on the originating purchase return order is updated based on the invoiced quantity. However, this original purchase return order is not deleted, even if it has been fully received and invoiced, and you must therefore delete the purchase return order manually.

> [!NOTE]  
> The following procedure assumes that there are several purchase return orders for the vendor, and that they have been posted as shipped.     

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memos**, and then choose the related link.  
2.  Choose the **New** action.  
3. On the **General** FastTab, fill in the fields as necessary.  
4. Choose the **Get Return Shipment Lines** action.  
5.  Select multiple return shipment lines that you want to include in the invoice.  

    If an incorrect return shipment line was selected or you want to start over, you can just delete the lines on the purchase credit memo and then use the **Get Return Shipment Lines** function again.  
6.  Choose the **Post** action.  

### To remove open purchase return orders after combined return shipment posting  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Purchase Return Orders**, and then choose the related link.  
2.  Fill in the fields as necessary, and then choose the **OK** button.  
3.  Alternatively, delete the individual purchase return orders manually.

## See Related Training at [Microsoft Learn](/learn/paths/return-items-dynamics-365-business-central/)

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
