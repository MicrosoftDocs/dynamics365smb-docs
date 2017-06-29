---
title: "Allocation Status and Repair Status"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "allocations, status"
  - "repair status, setting up"
  - "status, repair"
  - "status, allocation"
ms.assetid: 3a93061d-ce25-4941-89c1-80494f8abcbc
caps.latest.revision: 5
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
# Allocation Status and Repair Status
The repair status of service items and the allocation status of the allocation entries for the service items have a certain relationship in Service Management. The allocation status changes when you change the repair status of the service item to **Finished** or **Partly Serviced** and when you convert a service quote to a service order. The repair status of the service item changes when you cancel the service item allocation or reallocate the service item to another resource. You can view the repair status of service items in the **Service Tasks** window and you can update the repair status in the **Repair Status Code** field in the **Service Item Worksheet** window. You can view the allocation status in the **Status** field in the **Resource Allocations** window.  
  
## Changing Repair Status  
 When you change the repair status of a service item on a service item line, there is a search for a corresponding allocation entry for this service item that has the status **Active**. If such an allocation entry is found, the status is updated in one of the following ways:  
  
-   If you change the repair status to **Finished**, the allocation status is changed from **Active** to **Finished**.  
  
-   If you change the repair status to **Partly Serviced**, that is, some of the service has been completed, or **Referred**, that is, no service has been done, the allocation status is changed from **Active** to **Reallocation Needed**.  
  
-   When a service order allocation entry is created that indicates that no resource has been allocated, the **Status** field in the **Resource Allocation** window is set to **Nonactive**.  
  
-   The allocation entry status is set to **Canceled** when you reallocate the referred service item in the service order allocation entry, which indicates that the allocated resource or resource group has not attempted the service task.  
  
 The allocation status reflects when the service process is finished, or when another resource is necessary in order to finish the service of the service item.  
  
## Converting Service Quotes to Service Orders  
 When you convert a service quote to a service order, the service order, the service items in the order and their allocation entries are updated in the following ways:  
  
-   The repair status of the service items is changed to **Initial**.  
  
-   The service order status is changed to **Pending**.  
  
-   There is a search for allocation entries for all the service items in the service order that have the status **Active**. If such allocation entries are found, their allocation status is changed from **Active** to **Reallocation Needed**.  
  
## Canceling Allocations  
 When you cancel an allocation for a service item, FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> updates the allocation status of the corresponding allocation entry in the following way:  
  
-   The allocation status is changed from **Active** to **Reallocation Needed**.  
  
 The repair status of the service item in the allocation entry is updated in the following ways:  
  
-   If the repair status is **Initial**, the repair status is changed to **Referred** \(no service has been started\).  
  
-   If the repair status is **In Process**, the repair status is changed to **Partly Serviced** \(some service has been completed\).  
  
## Reallocating  
 When you reallocate a service item in an allocation entry that is **Active**, the allocation entry is updated in the following ways:  
  
-   If service was started when the allocation was **Active** \(that is, if the repair status of the service item in the entry was changed to **In Process**\), the allocation status is changed from **Active** to **Finished**.  
  
-   If service was not started when the allocation was **Active**, the allocation status is changed from **Active** to **Canceled**.  
  
 The repair status of the service item in the allocation entry is updated in the same way as if you had canceled the allocation:  
  
-   If the repair status is **Initial**, the repair status is changed to **Referred** \(no service has been started\).  
  
-   If the repair status is **In Process**, the repair status is changed to **Partly Serviced** \(some service has been completed\).  
  
 A new allocation entry that contains the new resource is created that has the status **Active**.  
  
## Reallocating a Service Item That Needs Reallocation  
 When you reallocate a service item in an allocation entry that has the status **Reallocation Needed**, the allocation entry is updated in the following ways:  
  
-   If service was started when the allocation was **Active** \(that is, if the repair status of the service item in the entry was changed to **In Process**\), the allocation status is changed from **Reallocation Needed** to **Finished**.  
  
-   If service was not started when the allocation was **Active**, the allocation status is changed from **Reallocation Needed** to **Canceled**.  
  
 A new allocation entry that contains the new resource is created that has the status **Active**.  
  
## See Also  
 [How to: Cancel Allocations](../Service/how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../Service/how-to-reallocate-resources-by-using-the-dispatch-board.md)   
 [How to: Reallocate Resources by Using Service Orders](../Service/how-to-reallocate-resources-by-using-service-orders.md)   
 [How to: Work on Service Tasks](../Service/how-to-work-on-service-tasks.md)   
 [How to: Set Up Repair Statuses](../Service/how-to-set-up-repair-statuses.md)