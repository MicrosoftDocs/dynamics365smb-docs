---
title: "How to: Refresh Production Orders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "planning, orders"
  - "production orders, refreshing"
ms.assetid: 7af3fbfb-0576-40aa-b41f-68724a173a26
caps.latest.revision: 13
ms.author: "sgroespe"
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
# How to: Refresh Production Orders
This planning function calculates changes made to a production order header and does not involve production BOM levels.  
  
 The **Refresh** function calculates and initiates the values of the component lines and routing lines based on the master data defined in the assigned production BOM and routing, according to the order quantity and due date on the production order’s header. It is typically used after you have done one of the following:  
  
-   Created a production order header manually to calculate and create line data for the first time.  
  
-   Made changes to the production order header to recalculate all the line data.  
  
> [!NOTE]  
>  You can change component lines and routing lines, and the production order schedule is updated accordingly. When you refresh, those changes are cancelled as the order is reset according to master data.  
  
### To refresh a production order  
  
1.  In the **Search** box, enter **Planned Production Orders**, and then choose the related link.  
  
2.  Create a new production order or open one that you want to refresh and change the **Quantity** or **Due Date** fields.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Refresh Production Order**.  
  
     In the **Refresh Production Order** window, on the **Options** FastTab, define how and what to refresh.  
  
4.  In the **Scheduling Direction** field, select one of the following options.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**Back**|To calculate the operation sequence backwards from the earliest possible ending date, as defined by due date and other scheduled orders, to the latest possible starting date.<br /><br /> **NOTE:** This default option is relevant in the majority of situations.|  
    |**Forward**|To calculate the operation sequence forward from the latest possible starting date, as defined by due date and other scheduled orders, to the earliest possible ending date.<br /><br /> **NOTE:** This option is relevant for ASAP orders.|  
  
5.  In the **Calculate** field, select which parts of the production order to calculate when refreshing.  
  
6.  Select the **Warehouse – Create Inbound Request** field to create a warehouse request for the putting away of the production order's components.  
  
    > [!NOTE]  
    >  The warehouse location must be set up to require put\-away processing but not directed put\-away and pick.  
  
7.  Choose the **OK** button to start the **Refresh** function according to your settings.  
  
> [!NOTE]  
>  You cannot refresh a reserved production order. You can restore the reservation after the production order is refreshed, but in that case you should cancel the reservation before you refresh.  
  
> [!NOTE]  
>  Changes implemented with the **Refresh** function are very likely to change the capacity need of the production order. You may have to reschedule operations afterwards.  
  
## See Also  
 [How to: Replan Production Orders](../OperationsPlanning/how-to-replan-production-orders.md)   
 [About Production Orders](../Production/about-production-orders.md)