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
# How to: Undo Quantity Posting on Posted Receipts
If you have made an incorrect quantity posting, that is, if you have made a purchase order with, for example, the wrong number of items and posted it as received but not invoiced, you can undo the posting.  
  
### To undo a quantity posting on a posted receipt  
  
1.  In the **Search** box, enter **Posted Purchase Receipts**, and then choose the related link.  
  
2.  Open the posted receipt that you want to undo.  
  
3.  Select the posted receipt line that you want to undo.  
  
4.  On the **Lines** FastTab, choose **Functions**, and then choose **Undo Receipt**.  
  
     A corrective line is inserted under the selected receipt line.  
  
     If the quantity was received in a warehouse receipt, then a corrective line is inserted in the posted warehouse receipt.  
  
     The **Quantity Received** and **Qty. Rcd. Not Invoiced** fields on the related purchase order are set to zero.  
  
## See Also  
 [How to: Undo Quantity Posting on Posted Return Receipts](../how-to-undo-quantity-posting-on-posted-return-receipts.md)   
 Qty. Rcd. Not Invoiced   
 Quantity Received