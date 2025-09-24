---
title: Process sales return orders
description: Describes how to create a sales return order to process a return, cancellation, or reimbursement for items or services you have been received payment for.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: undo, credit memo, return, order
ms.search.form: 44, 134, 144, 6629, 6630, 6633, 6662, 9302, 9304, Report_6646
ms.date: 03/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Process sales return orders  

If you need more control of the sales return process, such as warehouse documents for the item handling, or a better overview when receiving items from multiple sales documents with one sales return, then you can create sales return orders. A sales return order automatically issues the related sales credit memo and other return-related documents, such as a replacement sales order, if needed.

In addition to the original posted sales invoice, you can apply the sales credit memo or sales return order to other sales documents, for example another posted sales invoice because the customer is also returning items delivered with that invoice.

## Create a sales return order based on one or more posted sales documents  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Return Orders**, and then choose the related link.
2. Choose the **New** action.  
3. Fill in the fields on the **General** FastTab as necessary.
4. On the **Lines** FastTab, fill the lines manually, or copy information from other documents to fill the lines automatically:

    - Use the **Get Posted Document Lines to Reverse** function to copy one or more posted document lines from one or more posted documents. This function always exactly reverses the costs from the posted document line. This function is described in the following steps.    
    - Use the **Copy from Document** function to copy an existing document to the return order. Use this function to copy the entire document. It can be either a posted document or a document that isn't yet posted. This function only enables exact cost reversing when the **Exact Cost Reversing Mandatory** check box is selected on the **Sales & Receivables Setup** page.  

5. Choose the **Process** action, then choose the **Get Posted Document Lines to Reverse** action.
6. At the top of the **Posted Sales Document Lines** page, select the **Show Reversible Lines Only** check box if you want to see only lines that have quantities that haven't yet been returned. For example, if a posted sales invoice quantity has already been returned, you might not want to return that quantity on a new sales return document.

    > [!NOTE]  
    >  This field only works for posted shipments and posted invoice lines, not for posted return or posted credit memo lines.

    At the left side of the page, the different document types are listed, and the number in brackets shows the number of documents available of each document type.

7. In the **Document Type Filter** field, select the type of posted document lines you would like to use.  
8. Select the lines that you would like to copy to the new document.  

    > [!NOTE]  
    >  If you use <kbd>Ctrl</kbd>+<kbd>A</kbd> to select all lines, all lines within the filter you have set are copied, but the **Show Reversible Quantity Only** filter is ignored. For example, suppose you have filtered the lines to a particular document number with two lines, one of which has already been returned. Even if the **Show Reversible Quantity Only** field is selected, if you select <kbd>Ctrl</kbd>+<kbd>A</kbd> to copy all lines, both lines are copied, instead of only the one that has not yet been reversed.  

9. Choose the **OK** button to copy the lines to the new document.  

    The following processes occur:  

    -   For posted document lines of the type **Item**, a new document line is created that is a copy of the posted document line, with the quantity that hasn't yet been reversed. The **Appl.-from Item Entry** field is filled in as appropriate with the number of the item ledger entry of the posted document line.  

    -   For posted document lines that aren't of the type **Item**, such as item charges, a new document line is created that is a copy of the original posted document line.  

    -   Calculates the **Unit Cost (LCY)** field on the new line from the costs on the corresponding item ledger entries.  

    -   If the copied document is a posted shipment, posted receipt, posted return receipt, or posted return shipment, the unit price is calculated automatically from the item card.  

    -   If the copied document is a posted invoice or credit memo, the unit price, invoice discounts, and line discounts from the posted document line are copied.  

    -   If the posted document line contains item tracking lines, the **Appl.-from Item Entry** field on the item tracking lines is filled with the appropriate item ledger entry numbers from the posted item tracking lines.  

     When you copy from a posted invoice or posted credit memo, application copies any relevant invoice discounts and line discounts as valid at the time of posting that document from the posted document line to the new document line. Be aware, however, that if the **Calc. Inv. Discount** option is activated on the **Sales & Receivables Setup** page, then the invoice discount will be newly calculated when you post the new document line. The line amount for the new line might therefore be different than the line amount for the posted document line, depending on the new calculation of the invoice discount.  

     > [!NOTE]  
     >  If part of the quantity of the posted document line has already been reversed or sold or consumed, a line is created for only the quantity that remains in inventory or that has not been returned. If the full quantity of the posted document line has already been reversed, a new document line is not created.  
     >   
     >  If the flow of goods in the posted document is the same as the flow of goods in the new document, a copy of the original posted document line in the new document is created. The **Appl.-from Item Entry** field is not filled in because, in this case, exact cost reversing is not possible. For example, if you use the **Get Posted Document Lines to Reverse** function to get a posted sales credit memo line for a new sales credit memo, only the original posted credit memo line is copied to the new credit memo.  

10. On the **Sales Return Order** page, in the **Return Reason Code** field on each line, select the reason for the return.
11. Choose the **post** action.

## To create a replacement sales order from a sales return order
You might decide to compensate a customer for an item that you have sold them by replacing the item. You can make a replacement with the same item or a different item. This situation could occur if you mistakenly shipped the wrong item to the customer, for example.  

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
You might decide to charge your customer a restock fee to cover the physical handling costs of returning an item. This could occur if the customer mistakenly ordered the wrong item or changed their mind after receiving the item you sold them, for example.

You can post this increased cost as an item charge in a credit memo or a return order and assign it to the posted shipment. The following describes this for a sales return order, but the same steps apply to a sales credit memo.

1. Open the **Sales Return Order** page for an active return process.
2. On a new line, in the **Type** field, select **Charge (Item)**.  
3. Fill in the fields as for any item charge line. For more information, see [Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md).  

When you post the sales return order, the restock charge is added to the relevant sales entry amount. In this way, you can maintain accurate inventory valuation.  

## Related information

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Managing Payables](payables-manage-payables.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
