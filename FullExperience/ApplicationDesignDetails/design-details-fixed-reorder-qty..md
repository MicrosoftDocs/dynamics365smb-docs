---
title: "Design Details: Fixed Reorder Qty."
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "orders, fixed quantities"
ms.assetid: 1a392239-421e-476d-b617-757b41a89511
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
# Design Details: Fixed Reorder Qty.
The Fixed Reorder Qty. policy is related to inventory planning of typical C\-items \(low inventory cost, low risk of obsolescence, and\/or many items\). This policy is usually used in connection with a reorder point reflecting the anticipated demand during the lead time of the item.  
  
## Calculated per Time Bucket  
 If the planning system detects that the reorder point has been reached or crossed in a given time bucket \(reorder cycle\) – above or on the reorder point at the start of the period and below or on the reorder point at the end of the period – it will suggest to create a new supply order of the specified reorder quantity and forward schedule it from the first date after the end of the time bucket.  
  
 The bucketed reorder point concept reduces the number of supply suggestions. This reflects a manual process of frequently walking through the warehouse to check the actual contents in the various bins.  
  
## Creates only Necessary Supply  
 Before suggesting a new supply order to meet a reorder point, the planning system checks if supply has already been ordered to be received within the item’s lead time. If an existing supply order will solve the problem by bringing the projected inventory to or above the reorder point within the lead time, the system will not suggest a new supply order.  
  
 Supply orders that are created specifically to meet a reorder point is excluded from ordinary supply balancing, and will not in any way be changed afterwards. Consequently, if an item using reorder point is to be phased out \(not replenished\), it is advisable to review outstanding supply orders manually or change the reordering policy to Lot\-for\-Lot, whereby the system will reduce or cancel superfluous supply.  
  
## Combines with Order Modifiers  
 The order modifiers, Minimum Order Quantity, Maximum Order Quantity, and Order Multiple, should not play a big role when the fixed reorder quantity policy is used. However, the planning system still takes these modifiers into account and will decrease the quantity to the specified maximum order quantity \(and create two or more supplies in order to reach the total order quantity\), increase the order to the specified minimum order quantity, or round the order quantity up to meet a specified order multiple.  
  
## Combines with Calendars  
 Before suggesting a new supply order to meet a reorder point, the planning system checks if the order is scheduled for a non\-working day, according to any calendars that are defined in the **\($ T\_79\_7600 Base Calendar Code $\)** field in the **\($ N\_1 Company Information $\)** and **\($ N\_5703 Location Card $\)** windows.  
  
 If the scheduled date is a non\-working day, the planning system moves the order forward to the nearest working date. This may result in an order that meets a reorder point but does not meet some specific demand. For such unbalanced demand, the planning system creates an extra supply.  
  
## Should Not be Used with Forecast  
 Because the anticipated demand is already expressed in the reorder point level it is not necessary to include a forecast in the planning of an item using a reorder point. If it is relevant to base the plan on a forecast, use the lot\-for\-lot policy.  
  
## Must Not be Used with Reservations  
 If the user has reserved a quantity, for instance a quantity in inventory, for some distant demand, the planning foundation will be disturbed. Even if the projected inventory level is acceptable in relation to the reorder point, the quantities might not be available. The system may try to compensate for that by creating exception orders; however, it is recommended that the Reserve field is set to Never on items that are planned using a reorder point.  
  
## See Also  
 [Design Details: Reordering Policies](../ApplicationDesign/design-details-reordering-policies.md)   
 [Design Details: Maximum Qty.](../ApplicationDesign/design-details-maximum-qty..md)   
 [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)