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
# How to: Create and Post Purchase Allowances
If you receive items from your vendor that are not what you wanted, for example, if they are slightly damaged, the wrong color or the wrong size, the vendor may offer you a purchase allowance.  
  
 You can post this reduced purchase cost as an item charge on a credit memo or return order and link it to the posted receipt.  
  
 The following steps describe how to post a purchase allowance from a purchase credit memo, but you can follow the same steps for a purchase return order.  
  
> [!NOTE]  
>  It is recommended that you print a test report before you post the credit memo.  
  
### To create a purchase allowance  
  
1.  In the **Search** box, enter **Purchase Credit Memos**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the credit memo header with information about the vendor who sent you the purchase allowance.  
  
4.  In the first purchase line, in the **Type** field, choose the field and select **Charge \(Item\)**.  
  
5.  In the **No.** field, select the appropriate item charge number.  
  
     You may want to create a special item charge number to cover purchase allowances.  
  
6.  In the **Quantity** field, enter **1**.  
  
7.  In the **Direct Unit Cost** field, enter the amount of the purchase allowance.  
  
8.  Assign the purchase allowance as an item charge to the items in the posted receipt. When you have assigned the allowance, return to the **Credit Memo** window.  
  
### To post a purchase allowance  
  
1.  In the **Purchase Credit Memo** window, on the **Home** tab, in the **Process** group, choose **Post**.  
  
     If you want to print the credit memo at the same time as you post it, choose **Post and Print** instead.  
  
2.  Choose the **Yes** button, or if you are posting a return order, select **Ship and Invoice** and choose **OK**.  
  
> [!NOTE]  
>  When you enter a job number in the **Job No.** field on a purchase line with an item, an item entry is not created. Only a job entry is created when the document is posted.  
  
## See Also  
 [How to: Create Purchase Return Orders](../how-to-create-purchase-return-orders.md)   
 [How to: Get Receipt Lines for Item Charges](../how-to-get-receipt-lines-for-item-charges.md)   
 [How to: Get Return Receipt Lines for Item Charges](../how-to-get-return-receipt-lines-for-item-charges.md)   
 [How to: Get Return Shipment Lines for Item Charges](../how-to-get-return-shipment-lines-for-item-charges.md)   
 [How to: Get Shipment Lines for Item Charges](../how-to-get-shipment-lines-for-item-charges.md)   
 [How to: Get Transfer Receipt Lines for Item Charges](../how-to-get-transfer-receipt-lines-for-item-charges.md)   
 [How to: Post Purchase Credit Memos](../how-to-post-purchase-credit-memos.md)   
 [How to: Suggest Item Charge Assignments on Purchase Documents](../how-to-suggest-item-charge-assignments-on-purchase-documents.md)