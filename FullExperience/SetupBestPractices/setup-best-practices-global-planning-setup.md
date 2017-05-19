---
title: "Setup Best Practices: Global Planning Setup"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "setup (best practices), global planning"
  - "best practices, global planning setup"
ms.assetid: d0754652-2e95-4fdc-bfec-aa9351989fed
caps.latest.revision: 14
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
# Setup Best Practices: Global Planning Setup
The **Planning** FastTab in the **\($ N\_99000768 Manufacturing Setup $\)** window contains several fields that define global rules for supply planning.  
  
 The following table provides best practices on how to set up selected global planning parameter fields. For more information about a field, choose the link in the **Setup field** column.  
  
|Setup field|Best practice|Comment|  
|-----------------|-------------------|-------------|  
|[\($ T\_99000765\_37 Use Forecast on Locations $\)](../Topic/\($%20T_99000765_37%20Use%20Forecast%20on%20Locations%20$\).md)|Select if you have forecasts for specific locations.||  
|[\($ T\_99000765\_39 Components at Location $\)](../Topic/\($%20T_99000765_39%20Components%20at%20Location%20$\).md)|If items are not defined as SKUs, select the location code of your main warehouse.|This also applies if you only use the requisition worksheet.|  
|[\($ T\_99000765\_43 Blank Overflow Level $\)](../Topic/\($%20T_99000765_43%20Blank%20Overflow%20Level%20$\).md)|Select **Allow Default Calculation** if the solution has just been upgraded from a version earlier than [!INCLUDE[nav_5](../SetupAndAdministration/includes/nav_5_md.md)] SP1.|Use only if you want to allow all or some of your items to overflow the reorder point.|  
|[\($ T\_99000765\_40 Default Dampener Period $\)](../Topic/\($%20T_99000765_40%20Default%20Dampener%20Period%20$\).md)|Set between 1D and 5D.<br /><br /> If new to planning in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)], then set a longer period.|When users are more familiar with the different reasons for action messages, then shorten the dampener period to allow more change suggestions.|  
|[\($ T\_99000765\_41 Default Dampener Quantity $\)](../Topic/\($%20T_99000765_41%20Default%20Dampener%20Quantity%20$\).md)|Set between 5 and 20 percent of the item’s lot size.||  
  
## See Also  
 [Setup Best Practices: Supply Planning](../SetupAndAdministration/setup-best-practices-supply-planning.md)   
 [\($ N\_99000768 Manufacturing Setup $\)](../Topic/\($%20N_99000768%20Manufacturing%20Setup%20$\).md)   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)   
 [Set Up a Company With RapidStart Services for Microsoft Dynamics NAV](../SetupAndAdministration/set-up-a-company-with-rapidstart-services-for-microsoft-dynamics-nav.md)