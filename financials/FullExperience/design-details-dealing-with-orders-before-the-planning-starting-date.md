---
title: "Design Details: Dealing with Orders Before the Planning Starting Date"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "orders, before the start date"
ms.assetid: 76e5c26a-0048-42a0-a749-d29385085b78
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
# Design Details: Dealing with Orders Before the Planning Starting Date
To avoid that a supply plan shows impossible and therefore useless suggestions, the planning system regards the period up until the planning starting date a frozen zone where nothing is planned for. The following rule applies to the frozen zone:  
  
 All supply and demand before the starting date of the planning period will be considered a part of inventory or shipped.  
  
 Accordingly, the planning system will not, with a few exceptions, suggest any changes to supply orders in the frozen zone, and no order tracking links are created or maintained for that period.  
  
 The exceptions to this rule are as follows:  
  
-   If the projected available inventory, including the sum of supply and demand in the frozen zone, is below zero.  
  
-   If serial\/lot numbers are required on the backdated order\(s\).  
  
-   If the supply\-demand set is linked by an order\-to\-order policy.  
  
 If the initial available inventory is below zero, the planning system suggests an emergency supply order on the day before the planning period to cover the missing quantity. Consequently, the projected and available inventory will always be at least zero when planning for the future period begins. The planning line for this supply order will display an Emergency warning icon and additional information is provided upon lookup.  
  
## Serial\/Lot Numbers and Order\-to\-Order Links are Exempt from the Frozen Zone  
 If serial\/lot numbers are required or an order\-to\-order link exists, the planning system will disregard the frozen zone and incorporate such quantities that are back\-dated from the starting date and potentially suggest corrective actions if demand and supply is not synchronized. The business reason for this principle is that such specific demand\-supply sets must match to ensure that this specific demand is fulfilled.  
  
## See Also  
 [Design Details: Balancing Demand and Supply](../ApplicationDesign/design-details-balancing-demand-and-supply.md)   
 [Design Details: Central Concepts of the Planning System](../ApplicationDesign/design-details-central-concepts-of-the-planning-system.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)