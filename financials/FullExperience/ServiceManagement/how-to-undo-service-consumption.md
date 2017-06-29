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
# How to: Undo Service Consumption
You may need to cancel the consumption on the service order because it was posted by mistake.  
  
### To undo posted consumption  
  
1.  In the **Search** box, enter **Posted Service Shipments**, and then choose the related link.  
  
2.  Open the posted service shipment for which the erroneous consumption was posted.  
  
3.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Shipment**, and then choose **Service Shipment Lines**.  
  
4.  In the **Posted Service Shipment Lines** window, select the lines containing the incorrect consumption. On the **Actions** tab, in the **Functions** group, choose **Undo Consumption**.  
  
 A balancing service shipment line is inserted with negative values in the quantity fields for the selected lines.  
  
> [!NOTE]  
>  You will not be able to undo the service consumption if the service order has already been closed. It is also impossible to undo consumption that has been posted to the Jobs area, meaning there are job ledger entries linked to this consumption.  
  
## See Also  
 [How to: Undo Service Shipments](../Service/how-to-undo-service-shipments.md)   
 [How to: Register Service Operations](../Service/how-to-register-service-operations.md)