---
title: "How to: Set Up Email Logging"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "email logging, setting up"
  - "email logging, validating setup"
ms.assetid: d734aeac-5c2a-4bb1-a24f-7eab855056f2
caps.latest.revision: 14
ms.author: "edupont"
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
# How to: Set Up Email Logging
You set up email logging in the **Marketing Setup** window. Setup requires an email account that has a valid email address on Exchange. It also requires that you use public folders. This enables you to share and log information and email in a company.  
  
> [!NOTE]  
>  Consider creating a domain user email account that is not tied to specific individual. If you do this, you will also have to add the domain account to [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] as a Windows user who has the relevant permission set.  
  
 In order to set up email logging, you will require a [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] user who has sufficient permission sets. Consider using the permission sets BASIC and RM\-SETUP as defined in the [!INCLUDE[demolong](../../ApplicationDesign/includes/demolong_md.md)].  
  
 You must also have configured public folders on your Exchange server. For more information about configuring public folders in Exchange Server, see [Public folders](http://go.microsoft.com/fwlink/?LinkId=526140).  
  
 You can set up email logging for use with Exchange Server and with Exchange Online.  
  
### To set up email logging  
  
1.  In the **Search** box, enter **Marketing Setup**, and then choose the related link.  
  
2.  Expand the **E\-Mail Logging** FastTab to enter information to enable email logging.  
  
3.  In the **Autodiscovery E\-Mail Address** field, enter the email address that you want to use to enable the discovery and identification of your Exchange connection.  
  
4.  If you use Exchange Online, you must also specify the following fields:  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Exchange Service URL**|Optionally, specify the URL for your Exchange service.<br /><br /> If you specify this URL, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] connects faster to Exchange when you choose **Validate Email Logging Setup**.|  
    |**Exchange Account User Name**|Specify the name of the user account that has access to Exchange.|  
    |**Exchange Account User Password**|Specify the password of the user account that has access to Exchange.|  
  
5.  In the **Queue Folder Path** and **Storage Folder Path** fields, choose the **AssistEdit** button to open the **Exchange Public Folders** window.  
  
6.  For each field, select the public folder that you have set up for email logging. On the **Home** tab, in the **Process** group, choose **Get Subfolders**. If you have to access subfolders, select the folder, and choose **Get Subfolders** again. Expand the folder directory to reach the **Queue** and **Storage** folders that you have created.  
  
    > [!NOTE]  
    >  [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] does not support folder paths that are longer than 250 characters. Accordingly, you should set up your public folder structure to be able to handle this limitation.  
  
7.  In the **Email Batch Size** field, enter the number of emails that you want to process at a time. You can use the value that you specify to address performance issues.  
  
8.  To make sure that the address is valid on an Exchange Server, on the **Actions** tab, choose **Validate Email Logging Setup**.  
  
 After you have completed the setup of email logging, set up a job queue to start the process of having your email interactions logged on a regular or one\-time basis. For more information, see [How to: Set Up Email Logging for use with the Job Queue](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md).  
  
### To undo email logging setup  
  
-   To undo all settings for email logging setup, on the **Actions** tab, choose **Clear Email Logging Setup**.  
  
## See Also  
 [How to: Create Interactions](../../Marketing/how-to-create-interactions.md)   
 [Storage Folder Name](../Topic/\($%20T_5079_59%20Storage%20Folder%20Name%20$\).md)   
 [Queue Folder Name](../Topic/\($%20T_5079_56%20Queue%20Folder%20Name%20$\).md)   
 [How to: Set Up Email Logging for use with the Job Queue](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md)   
 [Walkthrough: Logging Email Interactions in the Microsoft Dynamics NAV Database](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/walkthrough-logging-email-interactions-in-the-microsoft-dynamics-nav-database.md)   
 [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md)