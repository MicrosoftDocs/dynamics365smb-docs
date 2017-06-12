---
title: "How to: Cancel Allocations"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "allocations, canceling"
ms.assetid: 660f6de2-2d1f-4a81-8a8e-487be3df19bf
caps.latest.revision: 8
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
# How to: Cancel Allocations
If you need to cancel allocations of resources, for example, technicians, to service tasks without reallocating the tasks directly, you can cancel the allocations.  
  
### To cancel an allocation  
  
1.  In the **Search** box, enter **Dispatch Board**, and then choose the related link.  
  
2.  Browse to the relevant service order. On the **Navigate** tab, in the **Planning** group, choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
3.  Select the allocation entry with the service task that you want to cancel allocation for.  
  
4.  On the **Actions** tab, in the **Functions** group, choose **Cancel Allocation**.  
  
5.  A dialog box opens. In the **Reason Code** field, select the appropriate reason code.  
  
6.  Choose the **Yes** button to confirm the cancellation.  
  
     In the **Status** field, the **Reallocation Needed** option is automatically selected. If the repair status of the service item in the entry is **Initial**, the repair status is changed to **Referred**, that is, no service has been started. If the repair status is **In Process**, it is changed to **Partly Serviced**, that is, some service has been completed.  
  
 Repeat these steps for each service task that you want to cancel allocation for.  
  
## See Also  
 [How to: Reallocate Resources by Using the Dispatch Board](../Service/how-to-reallocate-resources-by-using-the-dispatch-board.md)   
 [Allocation Status and Repair Status](../Service/allocation-status-and-repair-status.md)