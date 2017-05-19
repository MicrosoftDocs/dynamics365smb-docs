---
title: "Design Details: Demand and Supply"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "demand, supply"
ms.assetid: be8e6d90-fac9-4f6b-a32f-0227e6821696
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
# Design Details: Demand and Supply
Demand is the common term used for any kind of gross demand, such as a sales order and component need from a production order. In addition, the program allows more technical types of demand, such as negative inventory and purchase returns.  
  
 Supply is the common term used for any kind of positive or inbound quantity, such as inventory, purchases, assembly, production, or inbound transfers. In addition, a sales return may also represent supply.  
  
 To sort out the many sources of demand and supply, the planning system organizes them on two time lines called inventory profiles. One profile holds demand events, and the other holds the corresponding supply events. Each event represents one order network entity, such as a sales order line, an item ledger entry, or a production order line.  
  
 When inventory profiles are loaded, the different demand\-supply sets are balanced to output a supply plan that fulfills the listed goals.  
  
 Planning parameters and inventory levels are other types of demand and supply respectively, which undergo integrated balancing to replenish stock items. For more information, see [Design Details: Handling Reordering Policies](../ApplicationDesign/design-details-handling-reordering-policies.md).  
  
## See Also  
 [Design Details: Balancing Demand and Supply](../ApplicationDesign/design-details-balancing-demand-and-supply.md)   
 [Design Details: Central Concepts of the Planning System](../ApplicationDesign/design-details-central-concepts-of-the-planning-system.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)