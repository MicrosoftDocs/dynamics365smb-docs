---
title: "How to: Undo Quantity Postings on Posted Shipments"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "undoing, shipments"
ms.assetid: b0ebaa46-4f34-4eb8-9636-917ae9fc328e
caps.latest.revision: 11
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Undo Quantity Postings on Posted Shipments
Sometimes, you may make an incorrect quantity posting. For example, you may have made a sales order with the incorrect number of items and then posted it as shipped, but not invoiced. In this procedure, you undo the quantity posting, make the necessary corrections, and then post the quantity posting again.  
  
### To undo a quantity posting  
  
1.  In the **Search** box, enter **Posted Sales Shipments**, and then choose the related link.  
  
2.  Open the relevant posted sales shipment, and select the line or lines you want to correct.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Functions**, and then choose **Undo Shipment**.  
  
     A corrective line is created in the posted document. The **\($ T\_37\_60 Quantity Shipped $\)** field on the sales order is decreased by the quantity that you have undone. In turn, the **\($ T\_37\_18 Qty. to Ship $\)** is increased by the undone quantity. On the posted shipment line, in the corrective line **\($ T\_111\_15 Quantity $\)** is equal to the quantity of the line being undone. The **\($ T\_111\_5817 Correction $\)** check box is selected for the lines.  
  
     If the quantity was shipped in a warehouse shipment, a corrective line is inserted in the posted warehouse shipment. If the quantity was only partially shipped, then the **\($ T\_7321\_21 Qty. to Ship $\)** on the warehouse shipment is updated. The **\($ T\_7321\_25 Qty. Shipped $\)** field is decreased by the undone quantity.  
  
4.  Go back to the sales order, and on the **Process** tab, in the **Release** group, choose **Reopen** to reopen it.  
  
5.  Correct the entry in the **Quantity** field and post the order.  
  
     If the order is to be shipped through a warehouse shipment, then create and post a new warehouse shipment.  
  
> [!NOTE]  
>  If the item on the shipment was assembled to order, then the linked assembly order will automatically be reversed when you undo the shipment. For more information, see [How to: Undo Assembly Posting](../Sales/how-to-undo-assembly-posting.md).  
  
> [!NOTE]  
>  If the sales shipment is posted as a result of a drop shipment, you cannot undo the quantity posting because it is linked to a posted purchase receipt.  
  
> [!NOTE]  
>  [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] does not support undoing posted receipts if warehousing is in use. Therefore, if the sales shipment is posted that based on a warehouse inventory pick document, you cannot undo the quantity posting because it is linked to a posted receipt.  
  
## See Also  
 [\($ N\_130 Posted Sales Shipment $\)](../Topic/\($%20N_130%20Posted%20Sales%20Shipment%20$\).md)   
 [\($ N\_42 Sales Order $\)](../Topic/\($%20N_42%20Sales%20Order%20$\).md)   
 [\($ N\_900 Assembly Order $\)](../WarehouseActivities/-$-n_900-assembly-order-$-.md)   
 [How to: Sell Items Assembled to Order](../Sales/how-to-sell-items-assembled-to-order.md)   
 [Process Sales](../Sales/process-sales.md)