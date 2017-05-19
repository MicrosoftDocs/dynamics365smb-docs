---
title: "Design Details: The Concept of Balancing in Brief"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "balancing accounts, overview"
ms.assetid: 1c2aa444-e8d4-43d0-ad4d-a1175ea7714c
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
# Design Details: The Concept of Balancing in Brief
Demand is given by a company’s customers. Supply is what the company can create and remove to establish balance. The planning system starts with the independent demand and then tracks backwards to the supply.  
  
 The inventory profiles are used to contain information about the demands and supplies, quantities, and timing. These profiles essentially make up the two sides of the balancing scale.  
  
 The objective of the planning mechanism is to counterbalance the demand and supply of an item to ensure that supply will match demand in a feasible way as defined by the planning parameters and rules.  
  
 ![](../ApplicationDesign/media/nav_app_supply_planning_2_balancing.png "NAV\_APP\_supply\_planning\_2\_balancing")  
  
## See Also  
 [Design Details: Balancing Demand and Supply](../ApplicationDesign/design-details-balancing-demand-and-supply.md)   
 [Design Details: Central Concepts of the Planning System](../ApplicationDesign/design-details-central-concepts-of-the-planning-system.md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)