---
title: Allocation Status and Repair Status | Microsoft Docs
description: Learn about the relationship between the repair status of service items and the allocation status of the allocation entries for them.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: resources, allocation, status, repairs
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Allocation status and repair status of service items

The repair status of service items and the allocation status of the allocation entries for the service items have a certain relationship in Service Management. The allocation status changes when you change the repair status of the service item to **Finished** or **Partly Serviced** and when you convert a service quote to a service order. The repair status of the service item changes when you cancel the service item allocation or reallocate the service item to another resource. You can view the repair status of service items on the **Service Tasks** page and you can update the repair status in the **Repair Status Code** field on the **Service Item Worksheet** page. You can view the allocation status in the **Status** field on the **Resource Allocations** page.  
  
## Changing repair status

When you change the repair status of a service item on a service item line, there's a search for a corresponding allocation entry for this service item that has the status **Active**. If such an allocation entry is found, the status is updated in one of the following ways:  
  
* If you change the repair status to **Finished**, the allocation status is changed from **Active** to **Finished**.  
* If you change the repair status to **Partly Serviced**, that is, some of the services are completed, or **Referred**, that is, no service has been done, the allocation status is changed from **Active** to **Reallocation Needed**.  
* When a service order allocation entry is created that indicates that no resource has been allocated, the **Status** field on the **Resource Allocation** page is set to **Nonactive**.  
* The allocation entry status is set to **Canceled** when you reallocate the referred service item in the service order allocation entry, which indicates that the allocated resource or resource group hasn't attempted the service task.  
  
The allocation status reflects when the service process is finished, or when another resource is necessary in order to finish the service of the service item.  
  
## Converting service quotes to service orders

When you convert a service quote to a service order, the service order, the service items in the order and their allocation entries are updated in the following ways:  
  
* The repair status of the service items is changed to **Initial**.  
* The service order status is changed to **Pending**.  
* There's a search for allocation entries for all the service items in the service order that have the status **Active**. If such allocation entries are found, their allocation status is changed from **Active** to **Reallocation Needed**.  
  
## Canceling allocations

When you cancel an allocation for a service item, [!INCLUDE[prod_short](includes/prod_short.md)] updates the allocation status of the corresponding allocation entry from **Active** to **Reallocation Needed**.

The repair status of the service item in the allocation entry is updated in the following ways:  
  
* If the repair status is **Initial**, the repair status is changed to **Referred** (no service has been started).  
* If the repair status is **In Process**, the repair status is changed to **Partly Serviced** (some service has been completed).  
  
## Reallocating an active allocation Entry

When you reallocate a service item in an allocation entry that's **Active**, the allocation entry is updated in the following ways:  
  
* If service was started when the allocation was **Active** (that is, if the repair status of the service item in the entry was changed to **In Process**), the allocation status is changed from **Active** to **Finished**.  
* If service wasn't started when the allocation was **Active**, the allocation status is changed from **Active** to **Canceled**.  
  
The repair status of the service item in the allocation entry is updated in the same way as if you had canceled the allocation:  
  
* If the repair status is **Initial**, the repair status is changed to **Referred** (no service has been started).  
* If the repair status is **In Process**, the repair status is changed to **Partly Serviced** (some service has been completed).  
  
A new allocation entry that contains the new resource is created that has the status **Active**.  
  
## Reallocating a service item

When you reallocate a service item in an allocation entry that has the status **Reallocation Needed**, the allocation entry is updated in the following ways:  
  
* If service was started when the allocation was **Active** (that is, if the repair status of the service item in the entry was changed to **In Process**), the allocation status is changed from **Reallocation Needed** to **Finished**.  
* If service wasn't started when the allocation was **Active**, the allocation status is changed from **Reallocation Needed** to **Canceled**.  
  
A new allocation entry that contains the new resource is created that has the status **Active**.  
  
## Related information

- [Set Up Resource Allocations](service-how-setup-resource-allocation.md)  
- [Allocate Resources](service-how-to-allocate-resources.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
