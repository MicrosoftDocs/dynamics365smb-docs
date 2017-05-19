---
title: "Troubleshooting: RapidStart Services"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "troubleshooting, RapidStart Services"
  - "RapidStart Services, troubleshooting"
ms.assetid: e272921c-4dc1-4189-885b-9886357da721
caps.latest.revision: 3
ms.author: "edupont"
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
# Troubleshooting: RapidStart Services
This topic describes some common problems that you may see when you use [!INCLUDE[rimlong](../SetupAndAdministration/includes/rimlong_md.md)].  
  
## Binary type not supported  
 If you add a table to the Configuration Worksheet that contains a field of the Binary data type, you may receive the following error message:  
  
 **The type Binary is not supported.**  
  
 You may be unable to use navigation pane links or a ribbon action to reopen the worksheet. Other links, including those to tables listed in the worksheet, also become inoperable.  
  
 To resolve this error, consider the following change to your implementation. Before adding a table to the **\($ N\_8632 Configuration Worksheet $\)** window, check to see whether it contains fields of the Binary type, and modify the table before you continue with the addition.  
  
 For more information, see [Changes in C\-AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV](../Topic/Changes%20in%20C-AL%20Behavior%20and%20Support%20from%20Earlier%20Versions%20of%20Microsoft%20Dynamics%20NAV.md).  
  
## See Also  
 [Set Up a Company With RapidStart Services for Microsoft Dynamics NAV](../SetupAndAdministration/set-up-a-company-with-rapidstart-services-for-microsoft-dynamics-nav.md)