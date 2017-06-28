---
title: "How to: Allocate Resource Groups"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "allocating, resource groups"
  - "resources, allocating groups"
ms.assetid: 679d758e-5f46-4b1d-aba3-fa3ac5ae881e
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
# How to: Allocate Resource Groups
When you have created service orders or quotes, you can allocate resource groups, for example, groups of technicians, to perform the service tasks in the orders or quotes.  
  
### To allocate a resource group  
  
1.  In the **Search** box, enter **\($ N\_6000 Dispatch Board $\)**, and choose the related link.  
  
2.  Browse to the relevant service order.  
  
3.  On the **Navigate** tab, in the **Planning** group, choose **Resource Allocations**. The **\($ N\_6005 Resource Allocations $\)** window opens.  
  
4.  Select the nonactive allocation entry with the service task to which you want to allocate a resource.  
  
     If there is no nonactive allocation entry, you need to create one. On the **Home** tab, in the **New** group, choose **New**.  
  
5.  In the **\($ T\_5950\_5 Resource Group No. $\)** field, choose the relevant resource group.  
  
     [!INCLUDE[bp_choose_columns](../DesignAndEngineering/includes/bp_choose_columns_md.md)]  
  
6.  Fill in the **\($ T\_5950\_4 Allocation Date $\)** and **\($ T\_5950\_8 Allocated Hours $\)** fields.  
  
     The status of the resource allocation is automatically updated to be **Active**.  
  
 Repeat these steps for each date that you want to allocate the resource group to the service task.  
  
> [!NOTE]  
>  For a service item in a service order, there can only be **Active** allocation entries with one resource or resource group at a time.  
  
## See Also  
 [How to: Allocate Resources by Using Resource Group Availability](../Service/how-to-allocate-resources-by-using-resource-group-availability.md)   
 [How to: Allocate Resources by Using the Dispatch Board](../Service/how-to-allocate-resources-by-using-the-dispatch-board.md)   
 [How to: Cancel Allocations](../Service/how-to-cancel-allocations.md)   
 [How to: Reallocate Resources by Using the Dispatch Board](../Service/how-to-reallocate-resources-by-using-the-dispatch-board.md)