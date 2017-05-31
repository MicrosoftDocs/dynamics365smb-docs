---
title: "Design Details: Lot-for-Lot"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "lot-for-lot policy"
ms.assetid: ff833e58-ccde-4990-b6fa-15223a77f054
caps.latest.revision: 6
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
# Design Details: Lot-for-Lot
The lot\-for\-lot policy is the most flexible because the system only reacts on actual demand, plus it acts on anticipated demand from forecast and blanket orders and then settles the order quantity based on the demand. The lot\-for\-lot policy is aimed at A\- and B\-items where inventory can be accepted but should be avoided.  
  
 In some ways, the lot\-for\-lot policy looks like the Order policy, but it has a generic approach to items; it can accept quantities in inventory, and it bundles demand and corresponding supply in time buckets defined by the user.  
  
 The time bucket is defined in the **Time Bucket** field. The system works with a minimum time bucket of one day, since this is the smallest time unit of measure on demand and supply events in the system \(although, in practice, the time unit of measure on production orders and component needs can be seconds\).  
  
 The time bucket also sets limits on when an existing supply order should be rescheduled to meet a given demand. If the supply lies within the time bucket, it will be rescheduled in or out to meet the demand. Otherwise, if it lies earlier, it will cause unnecessary build\-up of inventory and should be canceled. If it lies later, a new supply order will be created instead.  
  
 With this policy, it is also possible to define a safety stock in order to compensate for possible fluctuations in supply, or to meet sudden demand.  
  
 Because the supply order quantity is based on the actual demand it can make sense to use the order modifiers: round the order quantity up to meet a specified order multiple \(or purchase unit of measure\), increase the order to a specified minimum order quantity, or decrease the quantity to the specified maximum quantity \(and thus create two or more supplies to reach the total needed quantity\).  
  
## See Also  
 [Design Details: Reordering Policies](../ApplicationDesign/design-details-reordering-policies.md)   
 [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)