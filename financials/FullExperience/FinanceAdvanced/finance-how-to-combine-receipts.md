---
    title: How to: Combine Receipts | Microsoft Docs
    description: If you want to invoice more than one purchase receipt at a time, you can use the **Combine Receipts** function.
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
# How to: Combine Receipts
If you want to invoice more than one purchase receipt at a time, you can use the **Combine Receipts** function.  
  
 Before you can create a combined purchase receipt, more than one receipt from the same vendor in the same currency must be posted. In other words, you must have filled in two or more purchase orders and posted them as received, but not invoiced.  
  
 When purchase receipts are combined on an invoice and posted, then a posted purchase invoice is created for the invoiced lines. The **Quantity Invoiced** field on the originating purchase order, or blanket purchase order, is updated based on the invoiced quantity. However, this original purchase document is not deleted, even if it has been fully received and invoiced, and you must therefore delete the purchase document.  
  
### To combine receipts  
  
1.  In the **Search** box, enter **Purchase Invoices**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Create a purchase invoice. For more information, see [How to: Record Purchases](../how-to-record-purchases.md).  
  
4.  On the **Lines** FastTab, choose, **Functions**, and then choose **Get Receipt Lines**.  
  
5.  Select multiple receipt lines that you want to include in the invoice.  
  
     If an incorrect receipt line was selected or you want to start over, you can just delete the lines on the purchase invoice and then use the **Get Receipt Lines** function again.  
  
6.  On the **Actions** tab, in the **Posting** group, choose **Post**, and then choose the **OK** button.  
  
### To remove open purchase orders after combined receipt posting  
  
1.  In the **Search** box, enter **Delete Invoiced Purchase Orders** or **Delete Invoiced Blanket Purchase Orders**, and the selected the related link.  
  
2.  Enter filters to define which orders to delete, and then choose the **OK** button.  
  
3.  Alternatively, delete the individual orders manually. On the **Home** tab, in the **Manage** group, choose **Delete**.  
  
## See Also  
 [How to: Combine Return Receipts](../how-to-combine-return-receipts.md)   
 [How to: Combine Return Receipts](../how-to-combine-return-receipts.md)   
 Purchase Order   
 Blanket Purchase Order   
 [Processing Purchase Orders](../processing-purchase-orders.md)