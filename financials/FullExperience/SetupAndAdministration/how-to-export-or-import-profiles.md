---
title: "How to: Export or Import Profiles"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "roles, exporting profiles"
  - "exporting, profiles"
  - "profiles, importing"
  - "roles, importing profiles"
  - "importing, profiles"
  - "profiles, exporting"
ms.assetid: c42b90a3-0b50-4aeb-955e-8390172d372c
caps.latest.revision: 10
ms.author: "solsen"
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
# How to: Export or Import Profiles
You can export a profile, for example to reuse UI configurations in other FIX INCLUDE HERE<!--[!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] --> databases.  
  
 You can quickly implement UI configurations for a profile by importing an XML file that holds the configured profile.  
  
> [!NOTE]  
>  You cannot import a profile that already exists in the database, even though the XML file is named differently or has different content. You must delete the existing profile before you can import the new profile.  
  
### To export a profile  
  
1.  In the **Search** box, enter **Export Profiles**, and then choose the related link.  
  
2.  In the **Export Profiles** window, on the **Profile** FastTab, set a filter for the profile ID that you want to export, and then choose **OK**.  
  
3.  Name and save the XML file for the profile.  
  
### To import a profile  
  
1.  In the **Search** box, enter **Import Profiles**, and then choose the related link.  
  
2.  In the **Import from XML File** window, select the profile that you want to import.  
  
     If you are importing a profile that already exists in the database, then you must first delete that profile. For more information, see [Manage Profiles](../SetupAndAdministration/manage-profiles.md).  
  
3.  Choose the **OK** button to import the new profile.  
  
## See Also  
 [Administration in the Clients](../SetupAndAdministration/administration-in-the-clients.md)   
 [Configure the User Interface](../SetupAndAdministration/configure-the-user-interface.md)