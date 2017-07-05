---
    title: How to: Create and Post Sales Allowances | Microsoft Docs
    description: You can send a customer a credit memo with a price reduction if the customer has received slightly damaged items or received the items late.
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
# How to: Create and Post Sales Allowances
You can send a customer a credit memo with a price reduction if the customer has received slightly damaged items or received the items late.  
  
 You can post this reduced price as an item charge in a credit memo or a return order and assign it to the posted shipment.  
  
 The following procedure describes how to post a sales allowance from a sales credit memo. You can also follow the same procedure to post a sales allowance from a sales return order.  
  
### To create a sales allowance  
  
1.  In the **Search** box, enter **Credit Memos**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the credit memo header with relevant information about the customer that you want to give the sales allowance to.  
  
4.  On the **Lines** FastTab, in the **Type** field, select **Charge (Item)**.  
  
5.  In the **No.** field, select the appropriate item charge value.  
  
     You may want to create a special item charge number to cover sales allowances.  
  
6.  In the **Quantity** field, enter **1**.  
  
7.  In the **Unit Price** field, enter the amount of the sales allowance.  
  
8.  Assign the sales allowance as an item charge to the items in the posted shipment. For more information, see [How to: Assign Item Charges to Sales Documents](../how-to-assign-item-charges-to-sales-documents.md). When you have assigned the allowance, return to the credit memo window.  
  
### To post a sales allowance  
  
1.  In the **Sales Credit Memo** window, on the **Actions** tab, in the **Posting** group, choose **Post**.  
  
     If you want to print the credit memo at the same time as you post, choose   **Post and Print** instead.  
  
2.  Choose the **Yes** button, or if you are posting a return order, select **Receive and Invoice**, and then choose the **OK** button.  
  
## See Also  
 [How to: Create Sales Return Orders](../how-to-create-sales-return-orders.md)   
 [How to: Get Return Receipt Lines for Item Charges](../how-to-get-return-receipt-lines-for-item-charges.md)   
 [How to: Get Shipment Lines for Item Charges](../how-to-get-shipment-lines-for-item-charges.md)   
 [How to: Post Sales Returns](../how-to-post-sales-returns.md)   
 [How to: Suggest Item Charge Assignments on Sales Documents](../how-to-suggest-item-charge-assignments-on-sales-documents.md)