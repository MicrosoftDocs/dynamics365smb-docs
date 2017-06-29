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
# Logging and Tracking Email Interactions
Email logging in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> is a service that allows email integration between Microsoft Exchange Server and ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->. This lets the user maintain information about current email messages in both systems. It also lets the user, a salesperson or a purchaser, share and publish information that has been communicated to ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> contacts.  
  
## How It Works  
 Email logging is designed to capture interactions between senders and recipients on the **To:** line of email messages. It captures the interactions that have been successfully concluded; interactions that are in a postponed state are not tracked.  
  
 Email logging uses Exchange Web Services to access an Exchange server. It uses a specified mail folder on the Exchange Server, called the queue folder. After an email message is retrieved from the queue folder, it is copied to another folder, called a storage folder. The email interaction is logged in the **Interaction Log Entry** table in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->. You can view the entries in the **Interaction Log Entries** window.  
  
> [!IMPORTANT]  
>  You must configure Exchange to allow public folders. This configuration is different across versions of Exchange. For more information, see [Public folders in Exchange Server 2013](http://go.microsoft.com/fwlink/?LinkId=526140).  
  
## Email Logging Rules  
 The following table describes how mail messages are processed after they arrive in the Queue folder.  
  
|Condition|Action|  
|---------------|------------|  
|Email message is tagged Normal, and there is a valid email address in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> for the salesperson and the contact.|The message is logged, if there is no duplicate message.|  
|Email message in queue folder is tagged Sensitive.|The message is deleted. If the email message is marked with a sensitivity level other than Normal, that is, **Private**, **Personal**, or **Confidential**, the message is deleted.|  
|Email address is not registered in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->.|The message is not copied to the storage folder. Email logging in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> is designed to log interactions only between salespersons and purchasers, and their known contacts. It does not track interactions with customers.|  
|Email message is a duplicate of a message in storage folder.|The message is not copied to the storage folder and is deleted from the queue folder. The message is examined for a match.|  
|Email address is longer than 80 characters.|The message is not copied and is deleted from the queue folder.|  
  
## See Also  
 [Walkthrough: Logging Email Interactions in the Microsoft Dynamics NAV Database](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/walkthrough-logging-email-interactions-in-the-microsoft-dynamics-nav-database.md)   
 [How to: Set Up Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging.md)   
 [How to: Set Up Email Logging for use with the Job Queue](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md)   
 [How to: Run Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-run-email-logging.md)   
 [Troubleshooting: Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md)   
 [Security Considerations for Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/security-considerations-for-email-logging.md)