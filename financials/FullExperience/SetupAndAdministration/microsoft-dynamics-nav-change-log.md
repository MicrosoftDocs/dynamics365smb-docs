---
title: "Microsoft Dynamics NAV Change Log"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "change log, about"
  - "Outlook synchronization, change logs"
ms.assetid: c1ea1427-3e22-498f-a87f-7ca21f4b6093
caps.latest.revision: 8
ms.author: "edupont"
manager: "tsiggaar"
translation.priority.ht: 
  - "da-dk"
  - "de-de"
  - "es-es"
  - "fi-fi"
  - "fr-fr"
  - "it-it"
  - "nb-no"
  - "nl-nl"
  - "sv-se"
---
# Microsoft Dynamics NAV Change Log
The change log in FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> --> logs changes that are made to data in the tables that you track. In the change log, entries are chronologically ordered and show changes that are made to the fields on the specified tables.  
  
 The change log collects all changes that are made to the table. For more information, see [How to: Enable the Change Log](../SetupAndAdministration/how-to-enable-the-change-log.md).  
  
## Modifying How Changes Are Logged  
 The default behavior in [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] tracks all changes that are made to the data. The change log code is called from the `OnDatabaseInsert` function in codeunit 1, **Application Management**. This is different from FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[nav2009](../SetupAndAdministration/includes/nav2009_md.md)] --> --> -->, in which changes are only tracked when users make changes in the [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] user interface. If you want to revert to the [!INCLUDE[nav2009](../SetupAndAdministration/includes/nav2009_md.md)] behavior, you can move the relevant code to an `OnGlobalInsert` function that you create based on [!INCLUDE[nav2009](../SetupAndAdministration/includes/nav2009_md.md)].  
  
## See Also  
 [How to: Enable the Change Log](../SetupAndAdministration/how-to-enable-the-change-log.md)   
 [How to: View Change Log Entries](../SetupAndAdministration/how-to-view-change-log-entries.md)   
 [How to: Print Change Log Entries](../SetupAndAdministration/how-to-print-change-log-entries.md)   
 [How to: Delete Change Log Entries](../SetupAndAdministration/how-to-delete-change-log-entries.md)