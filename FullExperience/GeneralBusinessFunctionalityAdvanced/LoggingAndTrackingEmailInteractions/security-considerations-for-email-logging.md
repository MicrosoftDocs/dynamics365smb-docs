---
title: "Security Considerations for Email Logging"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "email logging, security"
  - "security, considerations"
  - "security, email logging"
ms.assetid: 169d1eb1-1fe6-4ae1-97fc-be0326c2b1cc
caps.latest.revision: 5
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
# Security Considerations for Email Logging
Email messages received through the Internet can have fake sender addresses. That means that interaction log entries in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] that are created from email logging could potentially include fake addresses and should be reviewed for security reasons.  
  
 Before opening any mail message, make sure that you recognize the sender’s email address.  
  
 In addition, we recommend that a [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] administrator follow the latest security best practices guidance.  
  
 For more information about the steps that you can take to make your application more secure, see [Security TechCenter](http://go.microsoft.com/fwlink/?LinkID=80207).  
  
## See Also  
 [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md)   
 [Security and Protection](../Topic/Security%20and%20Protection.md)