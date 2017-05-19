---
title: "Design Details: Maximum Qty."
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "maximum quantity"
ms.assetid: b214f620-bec4-40fa-a9c6-cd49ac829eee
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
# Design Details: Maximum Qty.
The Maximum Quantity policy is a way to maintain inventory using a reorder point.  
  
 Everything regarding the Fixed Reorder Qty. policy also applies to this policy. The only difference is the quantity of the suggested supply. When using the maximum quantity policy, the reorder quantity will be defined dynamically based on the projected inventory level and will therefore usually differ from order to order.  
  
## Calculated per Time Bucket  
 The reorder quantity is determined at the point of time \(the end of a time bucket\) when the planning system detects that the reorder point has been crossed. At this time, the system measures the gap from the current projected inventory level up to the specified maximum inventory. This constitutes the quantity that should be reordered. The system then checks if supply has already been ordered elsewhere to be received within the lead time and, if so, reduces the quantity of the new supply order by already ordered quantities.  
  
 The system will ensure that the projected inventory at least reaches the reorder point level – in case the user has forgotten to specify a maximum inventory quantity.  
  
## Combines with Order Modifiers  
 Depending on the setup, it may be best to combine the Maximum Quantity policy with order modifiers to ensure a minimum order quantity or round it to an integer number of purchase units of measure, or split it into more lots as defined by the maximum order quantity.  
  
## Combines with Calendars  
 Before suggesting a new supply order to meet a reorder point, the planning system checks if the order is scheduled for a non\-working day, according to any calendars that are  defined in the **\($ T\_79\_7600 Base Calendar Code $\)** field in the **\($ N\_1 Company Information $\)** and **\($ N\_5703 Location Card $\)** windows.  
  
 If the scheduled date is a non\-working day, the planning system moves the order forward to the nearest working date. This may result in an order that meets a reorder point but does not meet some specific demand. For such unbalanced demand, the planning system creates an extra supply.  
  
## See Also  
 [Design Details: Reordering Policies](../ApplicationDesign/design-details-reordering-policies.md)   
 [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)