---
title: "How to: Test Databases Before Consolidating"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "testing, databases before consolidating"
  - "databases, testing"
  - "consolidating, testing databases"
ms.assetid: 42fe0ff0-c9e6-41b1-bc74-d6c6aa7bee50
caps.latest.revision: 8
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
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
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
# How to: Test Databases Before Consolidating
After you have set up the consolidated company and the business units and exported the necessary data, you are ready to do the consolidation. This means you can transfer the figures from the business units to the consolidated company.  
  
 Before you do this, it is a good idea to check whether there are differences between the basic information in the business units and in the consolidated company. There are two reports that you can use to test the database and file.  
  
 For more information, see [How to: Export Business Unit Information](../Finance/how-to-export-business-unit-information.md) and [How to: Test Files Before Consolidating](../Finance/how-to-test-files-before-consolidating.md).  
  
### To test databases before consolidating  
  
1.  Open the consolidated company.  
  
2.  In the **Search** box, enter **Business Units**, and then choose the related link.  
  
3.  In the **Business Units**, on the **Actions** tab, in the **Functions** group, choose **Test Database**.  
  
4.  On the **Business Unit** FastTab, you can set a filter to select the business units to be tested. If you do not set a filter, all business units that are selected in **Consolidate** field will be tested.  
  
5.  On the **Options** FastTab, fill in the appropriate fields. FIX INCLUDE HERE<!--[!INCLUDE[bp_fieldhelp]()] --> Choose the **Copy Dimensions** field and select the dimension codes.  
  
6.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
 FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> checks whether you have used account numbers or dimension codes that are not in the consolidated company. If any errors are found, they are listed in the report. If there is insufficient space to display all the errors on the screen, [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] prints a message.  
  
 If the report contains errors, you must correct them before you run the consolidation.  
  
## See Also  
 [How to: Process Consolidations](../Finance/how-to-process-consolidations.md)   
 [How to: Enter Basic Information for Consolidated Companies](../Finance/how-to-enter-basic-information-for-consolidated-companies.md)   
 [How to: Enter Consolidation Information on General Ledger Accounts](../Finance/how-to-enter-consolidation-information-on-general-ledger-accounts.md)   
 [How to: Export Business Unit Information](../Finance/how-to-export-business-unit-information.md)   
 [How to: Consolidate from Databases](../Finance/how-to-consolidate-from-databases.md)   
 [How to: Consolidate from Files](../Finance/how-to-consolidate-from-files.md)   
 Dimension   
 [\($ S\_COMPANY How to: Select a Company $\)](../WorkingWithDynamics/-$-s_company-how-to-select-a-company-$-.md)