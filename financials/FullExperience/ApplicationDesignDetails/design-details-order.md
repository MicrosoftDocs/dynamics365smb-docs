---
title: "Design Details: Order"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "orders, overview"
ms.assetid: 089b0059-1569-43e6-8964-f165e6d124eb
caps.latest.revision: 5
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
# Design Details: Order
In a make\-to\-order environment, an item is purchased or produced to exclusively cover a specific demand. Typically it relates to A\-items, and the motivation for choosing the Order reordering policy can be that the demand is infrequent, the lead\-time is insignificant, or the required attributes vary.  
  
 The program creates an order\-to\-order link, which acts as a preliminary connection between the supply, a supply order or inventory, and the demand that it is going to fulfill.  
  
 Apart from using the Order policy, the order\-to\-order link can be applied during planning in the following ways:  
  
-   When using the Make\-to\-Order manufacturing policy to create multi\-level or project type production orders \(producing needed components on the same production order\).  
  
-   When using the Sales Order Planning feature to create a production order from a sales order.  
  
 Even if a manufacturing company considers itself as a make\-to\-order environment, it might be best to use a Lot\-for\-Lot reordering policy if the items are pure standard without variation in attributes. As a result, the system will use unplanned inventory and only accumulates sales orders with the same shipment date or within a defined time bucket.  
  
## Order\-to\-Order Links and Past Due Dates  
 Unlike most supply\-demand sets, linked orders with due dates before the planning starting date are fully planned for by the system. The business reason for this exception is that specific demand\-supply sets must be synchronized through to execution. For more information about the frozen zone that applies to most demand\-supply types, see [Design Details: Dealing with Orders Before the Planning Starting Date](../ApplicationDesign/design-details-dealing-with-orders-before-the-planning-starting-date.md).  
  
## See Also  
 [Design Details: Reordering Policies](../ApplicationDesign/design-details-reordering-policies.md)   
 [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)