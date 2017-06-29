---
title: "How to: Set Up SMTP Email"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 781becd7-4ba1-4ed9-b5b9-fc3b00fc44b0
caps.latest.revision: 6
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
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
# How to: Set Up SMTP Email
To send e\-mails from FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> --> --> using an SMTP server, you must fill the **SMTP Mail Setup** window.  
  
 E\-mail sending is used for several features in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], such as when notifying workflow users about a workflow step. For more information, see [Workflow](../../BusinessFunctionality/Workflow/workflow.md).  
  
 E\-mails that are sent from [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] are based on e\-mail templates that define which fields and text to show in the e\-mail. The e\-mail template is an HTML file that you can export, edit in Microsoft Word, for example, and then import. For more information, see [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md).  
  
### To set up SMTP e\-mail  
  
1.  In the **Search** box, enter **SMTP Mail Setup**, and then choose the related link.  
  
2.  Fill the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**SMTP Server**|Specify the name of the SMTP server.|  
    |**SMTP Server Port**|Specify a port for the SMTP server. The default port is 25. **Note:**  When you set up the port, make sure that incoming and outgoing communications on the port is enabled for all clients and the Microsoft Dynamics NAV Server. Check your firewall settings.|  
    |**Authentication**|Specify the type of authentication that the SMTP server uses.<br /><br /> The default setting is **Anonymous**, which requires no user ID or password information. On an Azure deployment, use **Basic**.|  
    |**Secure Connection**|Specify if the SMTP server setup requires a encrypted channel that uses a cryptography or security protocol, such as secure socket layers \(SSL\).|  
  
3.  Choose the **OK** button.  
  
 For more information about SMTP e\-mail systems, see [Configure SMTP E\-mail \(IIS 7\)](http://go.microsoft.com/fwlink/?LinkId=263830).  
  
## See Also  
 [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md)   
 SMTP Mail Setup   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Configure SMTP E\-mail \(IIS 7\)](http://go.microsoft.com/fwlink/?LinkId=263830)