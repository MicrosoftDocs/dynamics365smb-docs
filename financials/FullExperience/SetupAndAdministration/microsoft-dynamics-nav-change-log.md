---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Microsoft Dynamics NAV Change Log
The change log in ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> logs changes that are made to data in the tables that you track. In the change log, entries are chronologically ordered and show changes that are made to the fields on the specified tables.  
  
 The change log collects all changes that are made to the table. For more information, see [How to: Enable the Change Log](../SetupAndAdministration/how-to-enable-the-change-log.md).  
  
## Modifying How Changes Are Logged  
 The default behavior in ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> tracks all changes that are made to the data. The change log code is called from the `OnDatabaseInsert` function in codeunit 1, **Application Management**. This is different from ADD INCLUDE<!--[!INCLUDE[nav2009](../SetupAndAdministration/includes/nav2009_md.md)]-->, in which changes are only tracked when users make changes in the ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> user interface. If you want to revert to the ADD INCLUDE<!--[!INCLUDE[nav2009](../SetupAndAdministration/includes/nav2009_md.md)]--> behavior, you can move the relevant code to an `OnGlobalInsert` function that you create based on ADD INCLUDE<!--[!INCLUDE[nav2009](../SetupAndAdministration/includes/nav2009_md.md)]-->.  
  
## See Also  
 [How to: Enable the Change Log](../SetupAndAdministration/how-to-enable-the-change-log.md)   
 [How to: View Change Log Entries](../SetupAndAdministration/how-to-view-change-log-entries.md)   
 [How to: Print Change Log Entries](../SetupAndAdministration/how-to-print-change-log-entries.md)   
 [How to: Delete Change Log Entries](../SetupAndAdministration/how-to-delete-change-log-entries.md)