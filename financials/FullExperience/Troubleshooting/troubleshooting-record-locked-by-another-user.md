---
title: "Troubleshooting: Compression Option in IIS"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 90f7b300-8c7b-43a1-9289-92d7e540ab68
caps.latest.revision: 3
ms.author: "solsen"
manager: "edupont"
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
# Troubleshooting: Compression Option in IIS
Users may experience slow mobile client responses especially noticeable when they are running with a slow network connection. The reason for the mobile client running slowly can be that the dynamic compression is not enabled on the IIS server.  
  
## Resolution  
 The IIS administrator must make sure that dynamic compression is enabled on the IIS. For more information, see [Enable HTTP Compression of Dynamic Content](http://go.microsoft.com/fwlink/?LinkId=392634)  
  
> [!NOTE]  
>  Dynamic compression is enabled by the ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> installer when you install ADD INCLUDE<!--[!INCLUDE[nav_web_server](../TroubleshootingUsingMicrosoftDynamicsNav/includes/nav_web_server_md.md)]-->.  
  
## See Also  
 [Troubleshooting Using Microsoft Dynamics NAV](../TroubleshootingUsingMicrosoftDynamicsNav/troubleshooting-using-microsoft-dynamics-nav.md)   
 [Troubleshooting the Microsoft Dynamics NAV Universal App](../Topic/Troubleshooting%20the%20Microsoft%20Dynamics%20NAV%20Universal%20App.md)