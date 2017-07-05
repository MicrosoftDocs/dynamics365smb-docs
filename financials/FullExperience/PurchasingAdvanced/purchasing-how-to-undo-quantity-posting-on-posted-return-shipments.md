---
    title: How to: Undo Quantity Posting on Posted Return Shipments | Microsoft Docs
    description: If you have made an incorrect quantity posting, that is if you have made a return order with, for example, the wrong number of items and posted it as shipped but not invoiced, then you can undo the posting.
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
# How to: Undo Quantity Posting on Posted Return Shipments
If you have made an incorrect quantity posting, that is if you have made a return order with, for example, the wrong number of items and posted it as shipped but not invoiced, then you can undo the posting.  
  
### To undo a quantity posting  
  
1.  In the **Search** box, enter **Posted Return Shipments**, and then choose the related link.  
  
2.  Open the relevant Posted Return Shipment and select the line or lines you want to correct.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Undo Return Shipment.**  
  
     A corrective line is inserted in the posted document, and the **Return Qty. Shipped** and **Return Shpd. Not Invd.** fields on the return order are set to zero.  
  
     Now go back to the purchase return order to redo the posting.  
  
4.  On the header of the **Posted Return Shipment** window, take a note of the number in the **Return order No.** field.  
  
5.  In the **Search** box, enter **Purchase Return Orders**, and then select the related link.  
  
6.  Open the return order in question, and then, on the **Actions** tab, in the **Release** group, choose **Reopen** to reopen it.  
  
7.  Correct the entry in the **Quantity** field and post the order.  
  
## See Also  
 Purchase Return Order   
 [Manage Purchase Returns](../manage-purchase-returns.md)   
 [How to: Undo Quantity Postings on Posted Shipments](../how-to-undo-quantity-postings-on-posted-shipments.md)