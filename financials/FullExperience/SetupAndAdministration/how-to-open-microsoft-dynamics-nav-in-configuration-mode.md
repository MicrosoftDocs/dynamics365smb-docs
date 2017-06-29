---
title: "How to: Open Microsoft Dynamics NAV in Configuration Mode"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "profiles, editing"
  - "RoleTailored client, opening in configuration mode"
  - "configuration mode, opening RoleTailored client in"
ms.assetid: 2cacf201-e68f-4b70-8ce2-a14e222793f4
caps.latest.revision: 29
ms.author: "solsen"
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
# How to: Open Microsoft Dynamics NAV in Configuration Mode
To configure a profile, for example to customize the profile’s user interface, you must open the FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] --> --> --> --> in configuration mode.  
  
### To open the [!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] in configuration mode  
  
1.  At the command prompt, navigate to the root folder of the [!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)]. For example:  
  
    ```  
    cd navnow_x86install\RoleTailored Client  
    ```  
  
2.  Type the following command:  
  
    ```  
    Microsoft.Dynamics.Nav.Client.exe -configure -profile:"profileid"  
    ```  
  
     Replace **profileid** with the name of the profile that you want to configure.  
  
     For example, to configure the Accounting Manager profile, use this command to open the [!INCLUDE[nav_windows](../BusinessFunctionality/IntegratingWithMicrosoftOffice/includes/nav_windows_md.md)] in configuration mode:  
  
    ```  
    Microsoft.Dynamics.Nav.Client.exe -configure -profile:"Accounting Manager"  
    ```  
  
## See Also  
 [Configure the User Interface](../SetupAndAdministration/configure-the-user-interface.md)   
 [How to: Create a Profile](../SetupAndAdministration/how-to-create-a-profile.md)   
 [How to: Assign a User to a Profile](../SetupAndAdministration/how-to-assign-a-user-to-a-profile.md)