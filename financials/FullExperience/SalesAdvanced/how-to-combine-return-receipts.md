---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Combine Return Receipts
You can combine return receipts if your customer returns several items that are covered by different sales return orders.  
  
 When you receive the items into your warehouse, post the relevant sales return orders as received, thus creating posted return receipts.  
  
 When you are ready to invoice this customer, instead of invoicing each sales return order separately, you can create a sales credit memo and automatically copy the posted return receipt lines to this document. Then you can post the sales credit memo and conveniently invoice all the open sales return orders at once.  
  
 To combine return receipts, the **Combine Shipments** check box must be selected on the **Shipping** FastTab of the **Customer** card.  
  
### To manually combine return receipts  
  
1.  In the **Search** box, enter **Sales Credit Memo**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the **No.** field.  
  
4.  In the **Sell-to Customer No.** field, select the customer who will receive the credit memo for the returned items.  
  
5.  Choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Get Return Receipt Lines**.  
  
6.  Select the return receipt lines that you want to include in the credit memo:  
  
    -   To insert all lines, select all lines and choose the **OK** button.  
  
    -   To insert specific lines, select the lines and choose the **OK** button. You can use the Ctrl key to select multiple nonsequential lines.  
  
7.  If an incorrect shipment line was selected or you want to start over, you can simply delete the lines on the credit memo and re-run the **Get Return Receipt Lines** function.  
  
8.  Post the invoice.  
  
## Automatically Combining Return Receipts  
 You can automatically combine return receipts and have the option of automatically posting the credit memos using the  **Combine Return Receipts** batch job.  
  
#### To create combined return receipts automatically  
  
1.  In the **Search** box, enter **Combine Return Receipts**, and then choose the related link. The batch job request window opens.  
  
2.  Fill in the fields to select the relevant return receipts. Select the **Post Credit Memos** field.  
  
3.  Choose the **OK** button.  
  
> [!NOTE]  
>  You will need to manually post the credit memos if the **Post Credit Memos** check box was not selected on the batch job.  
  
## Removing Received and Invoiced Return Orders  
 When you invoice return receipts in this way, the return orders from which the return receipts were posted still exist, even if they have been fully received and invoiced.  
  
 When return receipts are combined on a credit memo and posted, a posted sales credit memo is created for the credited lines. The **Quantity Invoiced** field on the originating sales return order is updated based on the invoiced quantity.  
  
#### To remove a received and invoiced return order  
  
1.  In the **Search** box, enter **Delete Invoiced Sales Return Orders**, and then select the link.  
  
2.  Specify in the **No.** filter field which return orders to delete.  
  
3.  Choose the **OK** button.  
  
 Alternatively, delete individual sales return orders manually.  
  
## See Also  
 [How to: Combine Receipts](../how-to-combine-receipts.md)   
 [How to: Combine Return Shipments](../how-to-combine-return-shipments.md)   
 [How to: Combine Shipments on a Single Invoice](../how-to-combine-shipments-on-a-single-invoice.md)   
 [How to: Get Return Receipt Lines for Item Charges](../how-to-get-return-receipt-lines-for-item-charges.md)   
 [How to: Process Sales Returns](../how-to-process-sales-returns.md)   
 [How to: Undo Quantity Posting on Posted Return Receipts](../how-to-undo-quantity-posting-on-posted-return-receipts.md)