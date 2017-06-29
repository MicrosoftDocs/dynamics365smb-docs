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
# How to: Release Orders
You can release sales and purchase orders to the next stage of processing before it is posted. When an order is released it will be included in all availability calculations from the expected receipt date of the items.  
  
### To release an order  
  
1.  Open the document you want to release.  
  
2.  On the **Actions** tab, in the **Functions** group, choose **Release**. The **Status** field has now changed to **Released**.  
  
> [!NOTE]  
>  You can make changes to a released order by reopening it. However, you can only change lines already processed by the warehouse by increasing the quantity.  
  
## See Also  
 [How to: Reopen Released Orders](../DesignAndEngineering/how-to-reopen-released-orders.md)   
 [Status Field on Documents](../DesignAndEngineering/status-field-on-documents.md)