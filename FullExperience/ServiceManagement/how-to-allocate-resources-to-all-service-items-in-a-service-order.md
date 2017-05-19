---
title: "How to: Allocate Resources to All Service Items in a Service Order"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "service items, allocating in a service order"
  - "service orders, allocating to all service items"
ms.assetid: c950c8de-fe06-4ce2-a443-43f17ac487fb
caps.latest.revision: 7
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
# How to: Allocate Resources to All Service Items in a Service Order
You can allocate the same resource, for example, a technician, or resource group to all the service items in a service order by using the **Resource Allocations** window.  
  
 Before you can allocate to all service items in the order, you need to allocate the resource or resource group to one service item in the order.  
  
### To allocate a resource to all service items in a service order  
  
1.  In the **Search** box, enter **\($ N\_6000 Dispatch Board $\)**, and choose the related link.  
  
2.  Browse to the relevant service order.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Resource Allocation**. The **Resource Allocations** window opens.  
  
4.  Select the allocation entry with the resource or resource group you have already allocated. The hours allocated in the **Allocated Hours** field will be divided between the allocation entries for all the service items in the order.  
  
5.  On the **Actions** tab, in the **Functions** group, choose **Allocate to All Service Items**.  
  
 Allocation entries are created for the other service items in the order with the same resource number and allocation date as the line you allocated. The allocated hours are the hours you allocated divided by the number of service items in the order. The **Status** field is automatically set to **Active** for all the entries that were created.  
  
## See Also  
 [How to: Allocate Resources by Using the Dispatch Board](../Service/how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Allocate Resource Groups](../Service/how-to-allocate-resource-groups.md)   
 [How to: Allocate Resources by Using Resource Availability](../Service/how-to-allocate-resources-by-using-resource-availability.md)