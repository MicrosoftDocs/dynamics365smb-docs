---
title: "How to: Enable the Change Log"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "change log, enabling"
ms.assetid: e094b7d5-4382-4bff-8435-97a33fa72149
caps.latest.revision: 11
ms.author: "edupont"
manager: "terryaus"
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
# How to: Enable the Change Log
A common problem in an administrative computer system is to locate the origin of errors and changes in data. It could be anything from an incorrect customer telephone number to an incorrect posting to the general ledger. The change log functionality lets you track all direct modifications a user makes to data in the database.  
  
 You must specify each table and field that you want the system to log, and then you must activate the change log.  
  
### To set up a change log  
  
1.  In the **Search** box, enter **Change Log Setup**, and then choose the related link.  
  
2.  In the **Change Log Setup** window, on the **Actions** tab, in the **Setup** group, choose **Tables**. The **Change Log Setup \(Table\) List** window opens.  
  
3.  Fill in the fields for each line.  
  
4.  Close the window.  
  
5.  To activate the change log, in the **Change Log Setup** window, select the **Change Log Activated** field. Close the window.  
  
 You must restart the FIX INCLUDE HERE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] --> for the new change log settings to take effect.  
  
> [!IMPORTANT]  
>  The change log cannot track all changes to BLOB fields. FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> --> tracks that the BLOB field gets set or cleared but cannot read if the field value changes.  
  
 [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] always logs changes to the **Change Log Activated** field, which means that you are always able to see which user deactivated or reactivated the change log. This cannot be turned off.  
  
 [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] also always tracks the following system tables:  
  
-   **Access Control**  
  
-   **Change Log Setup**  
  
-   **Change Log Setup \(Table\)**  
  
-   **Change Log Setup \(Field\)**  
  
-   **Permission**  
  
-   **Permission Set**  
  
-   **User**  
  
-   **User Property**  
  
## See Also  
 [How to: View Change Log Entries](../SetupAndAdministration/how-to-view-change-log-entries.md)   
 [How to: Delete Change Log Entries](../SetupAndAdministration/how-to-delete-change-log-entries.md)   
 [How to: Print Change Log Entries](../SetupAndAdministration/how-to-print-change-log-entries.md)   
 Change Log Activated