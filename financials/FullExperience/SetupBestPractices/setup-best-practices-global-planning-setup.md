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
The **Planning** FastTab in the **Manufacturing Setup** window contains several fields that define global rules for supply planning.  
  
 The following table provides best practices on how to set up selected global planning parameter fields. For more information about a field, choose the link in the **Setup field** column.  
  
|Setup field|Best practice|Comment|  
|-----------------|-------------------|-------------|  
|Use Forecast on Locations|Select if you have forecasts for specific locations.||  
|Components at Location|If items are not defined as SKUs, select the location code of your main warehouse.|This also applies if you only use the requisition worksheet.|  
|Blank Overflow Level|Select **Allow Default Calculation** if the solution has just been upgraded from a version earlier than ADD INCLUDE<!--[!INCLUDE[nav_5](../SetupAndAdministration/includes/nav_5_md.md)]--> SP1.|Use only if you want to allow all or some of your items to overflow the reorder point.|  
|Default Dampener Period|Set between 1D and 5D.<br /><br /> If new to planning in ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]-->, then set a longer period.|When users are more familiar with the different reasons for action messages, then shorten the dampener period to allow more change suggestions.|  
|Default Dampener Quantity|Set between 5 and 20 percent of the item’s lot size.||  
  
## See Also  
 [Setup Best Practices: Supply Planning](../SetupAndAdministration/setup-best-practices-supply-planning.md)   
 Manufacturing Setup   
 [Design Details: Supply Planning](../ApplicationDesign/design-details-supply-planning.md)   
 [Set Up a Company With RapidStart Services for Microsoft Dynamics NAV](../SetupAndAdministration/set-up-a-company-with-rapidstart-services-for-microsoft-dynamics-nav.md)