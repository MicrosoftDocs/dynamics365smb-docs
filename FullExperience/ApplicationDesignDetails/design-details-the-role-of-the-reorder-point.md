---
title: "Design Details: The Role of the Reorder Point"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "reorder points"
ms.assetid: c4b12355-ce24-49bf-8368-e0d877fdd371
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
# Design Details: The Role of the Reorder Point
In addition to the general balancing of supply and demand, the planning system must also monitor inventory levels for the affected items to respect the defined reordering policies:  
  
 A reorder point represents demand during lead time. When the projected inventory passes below the inventory level defined by the reorder point, it is time to order more quantity. Meanwhile, the inventory is expected to decrease gradually and possibly reach zero \(or the safety stock level\), until the replenishment arrives.  
  
 Accordingly, the planning system will suggest a forward\-scheduled supply order at the point when the projected inventory passes below the reorder point.  
  
 The reorder point reflects a certain inventory level. However, inventory levels can move significantly during the time bucket and, therefore, the planning system must constantly monitor the projected available inventory.  
  
## See Also  
 [Design Details: Reordering Policies](../ApplicationDesign/design-details-reordering-policies.md)   
 [Design Details: Planning Parameters](../ApplicationDesign/design-details-planning-parameters.md)   
 [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)