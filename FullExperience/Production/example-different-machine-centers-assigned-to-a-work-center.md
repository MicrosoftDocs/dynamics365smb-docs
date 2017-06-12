---
title: "Example - Different Machine Centers Assigned  to a Work Center"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "capacities"
ms.assetid: 4e692986-de5a-4e66-bca6-ebff0a65710f
caps.latest.revision: 7
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
# Example - Different Machine Centers Assigned  to a Work Center
It is important to plan which capacities are to make up the total capacity when setting up the machine centers and work centers.  
  
 If different machine centers \(such as 210 Packing table 1, 310 Painting Cabin ...\) are assigned to a work center, the consideration of the single capacities of the machine centers is significant because failure of one machine center can interrupt the entire process. The machine groups can be entered according to their capacity but may not be included in the planning. By deactivating the **Consolidated Calendar** field only the capacity of the work center but not the machine center is assigned in the planning.  
  
 If, however, identical machine centers \(such as 210 Packing table 1 and 220 Packing table 2\) are combined in a work center, the consideration of the work center as a sum of the assigned machine centers is of interest. Therefore, the work center would be listed with zero capacity. By activating the **Consolidated Calendar** field, the common capacity is assigned to the work center.  
  
 If capacities of work centers are to make no contribution to the total capacity, you can achieve this with efficiency \= 0.  
  
## See Also  
 [Work Center Card](../Topic/\($%20N_99000754%20Work%20Center%20Card%20$\).md)   
 [Machine Center Card](../Topic/\($%20N_99000760%20Machine%20Center%20Card%20$\).md)   
 [Shop Calendars](../OperationsPlanning/shop-calendars.md)   
 [Consolidated Calendar](../Topic/\($%20T_99000754_52%20Consolidated%20Calendar%20$\).md)