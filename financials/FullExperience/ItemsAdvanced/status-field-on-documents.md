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
# Status Field on Documents
When you create a quote, order or credit memo, the **Status** field on the document header contains the status **Open** by default.  
  
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
 Sales Order   
 Status   
 [How to: Release Orders](../how-to-release-orders.md)   
 [How to: Reopen Released Orders](../how-to-reopen-released-orders.md)