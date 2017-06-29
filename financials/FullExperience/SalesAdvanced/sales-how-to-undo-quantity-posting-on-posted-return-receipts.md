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
# How to: Undo Quantity Posting on Posted Return Receipts
If you have made an incorrect quantity posting, that is if you have made a return order with, for example, the wrong number of items and posted it as received but not invoiced, you can undo the posting.  
  
### To undo a quantity posting  
  
1.  In the **Search** box, enter **Posted Return Receipts**, and then choose the related link.  
  
2.  Open the relevant posted return receipt, and select the line or lines you want to correct.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Undo Return Receipt**.  
  
     A corrective line is inserted in the posted document and the **Returned Qty. Received** and **Return Qty. Rcd. Not Invd.** fields on the return order are set to zero. If the quantity was received in a warehouse receipt, a corrective line is inserted in the posted warehouse receipt and, if the quantity was only partially received, the **Qty. to Receive** is updated on the warehouse receipt.  
  
4.  Go back to the return order, and on the **Actions** tab, in the **Release** group, choose **Reopen** to reopen it.  
  
5.  Correct the entry in the **Quantity** field and post the order.  
  
## See Also  
 [Manage Sales Returns](../manage-sales-returns.md)   
 [How to: Undo Quantity Posting on Posted Receipts](../how-to-undo-quantity-posting-on-posted-receipts.md)