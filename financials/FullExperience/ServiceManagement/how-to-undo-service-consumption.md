---
title: "How to: Undo Service Consumption"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting, service consumptions"
  - "undoing, service consumption"
  - "service consumptions, undoing"
  - "consumption, canceling service"
ms.assetid: 03ad4b50-a957-4688-a743-75696e59b850
caps.latest.revision: 6
ms.author: "edupont"
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