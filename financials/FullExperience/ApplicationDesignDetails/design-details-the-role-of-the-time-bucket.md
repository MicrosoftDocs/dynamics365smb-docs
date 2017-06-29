---
title: "Design Details: The Role of the Time Bucket"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "time buckets"
ms.assetid: 88484e41-e4d7-4515-a197-3dfde6e356c6
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
# Design Details: The Role of the Time Bucket
The purpose of the time bucket is to collect demand events within the time window in order to make a joint supply order.  
  
 For reordering policies that use a reorder point, you can define a time bucket. This ensures that demand within the same time period is accumulated before checking the impact on the projected inventory and whether the reorder point has been passed. If the reorder point is passed, a new supply order is scheduled forward from the end of the period defined by the time bucket. The time buckets begin on the planning starting date.  
  
 The time\-bucketed concept reflects the manual process of checking the inventory level on a frequent basis rather than for each transaction. The user needs to define the frequency \(the time bucket\). For example, the user gathers all item needs from one vendor to place a weekly order.  
  
 ![](../ApplicationDesign/media/nav_app_supply_planning_2_reorder_cycle.png "NAV\_APP\_supply\_planning\_2\_reorder\_cycle")  
  
 The time bucket is generally used to avoid a cascade effect. For example, a balanced row of demand and supply where an early demand is canceled, or a new one is created. The result would be that every supply order \(except the last one\) is rescheduled.  
  
## See Also  
 [Design Details: Reordering Policies](../ApplicationDesign/design-details-reordering-policies.md)   
 [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)