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
# How to: Undo Quantity Postings on Posted Shipments
Sometimes, you may make an incorrect quantity posting. For example, you may have made a sales order with the incorrect number of items and then posted it as shipped, but not invoiced. In this procedure, you undo the quantity posting, make the necessary corrections, and then post the quantity posting again.  
  
### To undo a quantity posting  
  
1.  In the **Search** box, enter **Posted Sales Shipments**, and then choose the related link.  
  
2.  Open the relevant posted sales shipment, and select the line or lines you want to correct.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Undo Shipment**.  
  
     A corrective line is created in the posted document. The **Quantity Shipped** field on the sales order is decreased by the quantity that you have undone. In turn, the **Qty. to Ship** is increased by the undone quantity. On the posted shipment line, in the corrective line **Quantity** is equal to the quantity of the line being undone. The **Correction** check box is selected for the lines.  
  
     If the quantity was shipped in a warehouse shipment, a corrective line is inserted in the posted warehouse shipment. If the quantity was only partially shipped, then the **Qty. to Ship** on the warehouse shipment is updated. The **Qty. Shipped** field is decreased by the undone quantity.  
  
4.  Go back to the sales order, and on the **Process** tab, in the **Release** group, choose **Reopen** to reopen it.  
  
5.  Correct the entry in the **Quantity** field and post the order.  
  
     If the order is to be shipped through a warehouse shipment, then create and post a new warehouse shipment.  
  
> [!NOTE]  
>  If the item on the shipment was assembled to order, then the linked assembly order will automatically be reversed when you undo the shipment. For more information, see [How to: Undo Assembly Posting](../how-to-undo-assembly-posting.md).  
  
> [!NOTE]  
>  If the sales shipment is posted as a result of a drop shipment, you cannot undo the quantity posting because it is linked to a posted purchase receipt.  
  
> [!NOTE]  
>  ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> does not support undoing posted receipts if warehousing is in use. Therefore, if the sales shipment is posted that based on a warehouse inventory pick document, you cannot undo the quantity posting because it is linked to a posted receipt.  
  
## See Also  
 Posted Sales Shipment   
 Sales Order   
 Assembly Order   
 [How to: Sell Items Assembled to Order](../how-to-sell-items-assembled-to-order.md)   
 [Process Sales](../process-sales.md)