---
title: "How to: Reallocate Resources by Using Service Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service orders, allocating on service orders"
  - "resources, allocating on service orders"
ms.assetid: c74e0d0e-bf2b-4669-a7b4-7cdda96165c9
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
# How to: Reallocate Resources by Using Service Orders
You can reallocate resources directly from a service order or service quote when you are working with it.  
  
### To reallocate resources using a service order  
  
1.  In the **Search** box, enter **Service Orders**, and then choose the related link.  
  
2.  Open the relevant service order.  
  
3.  Select the service item line corresponding to the service task you want to allocate a resource to.  Choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Line**, and then choose **Resource Allocations**. The **Resource Allocations** window opens.  
  
4.  In the **Resource Allocations** window, select an allocation entry with the service task you want to reallocate the resource to. In the **Resource No.** field, select the relevant resource. This overwrites the resource number already in the field.  
  
5.  Press the Enter key. A dialog box opens, asking whether you want to reallocate this entry. Fill in the **Reason Code** field if appropriate and choose the **Yes** button to confirm the reallocation.  
  
6.  Fill in the **Allocation Date** and **Allocated Hours** fields. The entry now contains the new resource and its status is **Active**.  
  
    > [!NOTE]  
    >  The old entry still exists but its status is updated as follows:  
    >   
    >  -   If service was started while the allocation was **Active**, that is, if the repair status of the service item in the entry was changed to **In Process**, the allocation status changes from **Reallocation Needed** to **Finished**.  
    > -   If service was not started while the allocation was **Active**, allocation status changes from **Reallocation Needed** to **Canceled**.  
    > -   If you are reallocating a service order that you have converted from a quote, the status of the allocation entries registered for the quote always changes to **Finished** when you reallocate the service items in the service order.  
  
7.  Repeat these steps for each service task you want to reallocate.  
  
## See Also  
 [Allocation Status and Repair Status](../Service/allocation-status-and-repair-status.md)   
 [How to: Allocate Resources by Using Service Orders](../Service/how-to-allocate-resources-by-using-service-orders.md)   
 [How to: Allocate Resources by Using the Dispatch Board](../Service/how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Cancel Allocations](../Service/how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../Service/how-to-reallocate-resources-by-using-the-dispatch-board.md)