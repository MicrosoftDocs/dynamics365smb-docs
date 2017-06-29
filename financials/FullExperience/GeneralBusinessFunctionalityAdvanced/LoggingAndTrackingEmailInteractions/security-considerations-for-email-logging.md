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
# Security Considerations for Email Logging
Email messages received through the Internet can have fake sender addresses. That means that interaction log entries in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> that are created from email logging could potentially include fake addresses and should be reviewed for security reasons.  
  
 Before opening any mail message, make sure that you recognize the sender’s email address.  
  
 In addition, we recommend that a ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> administrator follow the latest security best practices guidance.  
  
 For more information about the steps that you can take to make your application more secure, see [Security TechCenter](http://go.microsoft.com/fwlink/?LinkID=80207).  
  
## See Also  
 [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md)   
 [Security and Protection](../Topic/Security%20and%20Protection.md)