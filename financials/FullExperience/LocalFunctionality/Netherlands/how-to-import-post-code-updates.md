---
title: "How to: Import Post Code Updates"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "postal codes, importing"
  - "postal codes, updating"
ms.assetid: 1aa83184-3687-4cfa-b351-c5222f47d00c
caps.latest.revision: 7
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Import Post Code Updates
Every month a post code file will be delivered with all post code mutations in a month. This post code file can be imported and update the relevant data of the **\($ T\_11406 Post Code Range $\)** table.  
  
### To import the update file  
  
1.  In the **Search** box, enter **\($ N\_11408 Post Codes Updates $\)**, and then choose the related link.  
  
2.  In the **\($ N\_11408 Post Codes Updates $\)** window, on the **Actions** tab, in the **Functions** group, choose **Import Post Codes Update**.  
  
3.  Specify the path and name of the post code update file, and then choose the **OK** button. If you do not want to import the file, choose the **Cancel** button to close the window.  
  
 If there is no file imported with a full set of post code data, then a message appears.  
  
 Before updating the post codes the following checks will be performed:  
  
-   Is there already an update file imported with a [\($ T\_11407\_10 Date Field $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11407_10-date-field-$-.md) later then the date of this new update file? If so then the process will stop.  
  
-   Is there a gap between the date of this file and the value in the [\($ T\_11407\_10 Date Field $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11407_10-date-field-$-.md) field for the last imported file? If there is a gap then a message appears. You can choose if you still want to import the update file.  
  
 Information about the imported post code will be saved in the [\($ T\_11407 Post Code Update Log Entry Table $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11407-post-code-update-log-entry-table-$-.md) table.  
  
## See Also  
 [Dutch Post Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/dutch-post-codes.md)   
 [\($ T\_11407 Post Code Update Log Entry Table $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11407-post-code-update-log-entry-table-$-.md)   
 [\($ N\_11408 Post Code Updates Window $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_11408-post-code-updates-window-$-.md)   
 [\($ T\_11406 Post Code Range Table $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11406-post-code-range-table-$-.md)