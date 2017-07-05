---
    title: How to: Enable the Change Log | Microsoft Docs
    description: A common problem in an administrative computer system is to locate the origin of errors and changes in data. It could be anything from an incorrect customer telephone number to an incorrect posting to the general ledger. The change log functionality lets you track all direct modifications a user makes to data in the database.
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
# How to: Enable the Change Log
A common problem in an administrative computer system is to locate the origin of errors and changes in data. It could be anything from an incorrect customer telephone number to an incorrect posting to the general ledger. The change log functionality lets you track all direct modifications a user makes to data in the database.  
  
 You must specify each table and field that you want the system to log, and then you must activate the change log.  
  
### To set up a change log  
  
1.  In the **Search** box, enter **Change Log Setup**, and then choose the related link.  
  
2.  In the **Change Log Setup** window, on the **Actions** tab, in the **Setup** group, choose **Tables**. The **Change Log Setup (Table) List** window opens.  
  
3.  Fill in the fields for each line.  
  
4.  Close the window.  
  
5.  To activate the change log, in the **Change Log Setup** window, select the **Change Log Activated** field. Close the window.  
  
 You must restart the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]--> for the new change log settings to take effect.  
  
> [!IMPORTANT]  
>  The change log cannot track all changes to BLOB fields. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] tracks that the BLOB field gets set or cleared but cannot read if the field value changes.  
  
 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] always logs changes to the **Change Log Activated** field, which means that you are always able to see which user deactivated or reactivated the change log. This cannot be turned off.  
  
 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] also always tracks the following system tables:  
  
-   **Access Control**  
  
-   **Change Log Setup**  
  
-   **Change Log Setup (Table)**  
  
-   **Change Log Setup (Field)**  
  
-   **Permission**  
  
-   **Permission Set**  
  
-   **User**  
  
-   **User Property**  
  
## See Also  
 [How to: View Change Log Entries](../how-to-view-change-log-entries.md)   
 [How to: Delete Change Log Entries](../how-to-delete-change-log-entries.md)   
 [How to: Print Change Log Entries](../how-to-print-change-log-entries.md)   
 Change Log Activated