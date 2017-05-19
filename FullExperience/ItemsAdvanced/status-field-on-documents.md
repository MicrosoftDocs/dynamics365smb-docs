---
title: "Status Field on Documents"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "status, on documents"
ms.assetid: c797e030-0917-4bd3-a3a3-832882c0a854
caps.latest.revision: 4
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
# Status Field on Documents
When you create a quote, order or credit memo, the **\($ T\_36\_120 Status $\)** field on the document header contains the status **Open** by default.  
  
 After you have filled in the document, you can release it, and the program changes the value in the **Status** field to **Released**. This status indicates that the order is ready for the next stage of processing before it is posted.  
  
## Releasing  
 You can use the release process in different ways to ease your normal work flow, for example, to follow company procedures about approvals or state of warehouse activities.  
  
### Approval Procedures  
 Your company can use the release procedure to indicate that another user has approved the document, or that an external contact can meet the specifications on the document, as shown in these examples:  
  
-   You can only release a purchase order when your vendor has indicated that they are prepared to fulfill the order.  
  
-   You create an order and a second user must approve it, perhaps for security reasons, before you are allowed to release it.  
  
-   A credit memo that you have created must be released by the manager responsible for approving all refunds.  
  
### Warehouse Activities  
 If the order status is Open, the warehouse will not begin to prepare the shipment and does not expect to receive the items on a purchase order. When you release the order, you indicate that the order is complete, and that the warehouse can include it in their activities.  
  
## Reopening a released order  
 You can make changes to a released order by reopening it. However, you can only increase the quantity of the lines already processed by the warehouse.  
  
 When you have made your changes and you release the order again, the VAT and the invoice discount are recalculated.  
  
 If you make changes to a released order, you must notify the warehouse about the changes.  
  
> [!NOTE]  
>  If you want to post a single open order or credit memo without releasing it first, the program will automatically release the document when you post it.  
>   
>  If you post your orders or credit memos by using the **Post Batch** function, you can choose only to post the orders or credit memos that you have released.  
  
## See Also  
 [\($ N\_42 Sales Order $\)](../Topic/\($%20N_42%20Sales%20Order%20$\).md)   
 [\($ T\_36\_120 Status $\)](../Topic/\($%20T_36_120%20Status%20$\).md)   
 [How to: Release Orders](../DesignAndEngineering/how-to-release-orders.md)   
 [How to: Reopen Released Orders](../DesignAndEngineering/how-to-reopen-released-orders.md)