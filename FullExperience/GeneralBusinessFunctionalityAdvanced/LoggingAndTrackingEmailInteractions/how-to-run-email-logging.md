---
title: "How to: Run Email Logging"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "email logging, running"
  - "email logging, automating"
ms.assetid: 837b9c82-ddf6-4730-ba66-a1f84b5647e2
caps.latest.revision: 6
ms.author: "edupont"
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
# How to: Run Email Logging
Email logging can be used to capture email activities between a [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] salesperson or purchaser and a [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] contact. Both persons must have valid email addresses that are registered on the respective salesperson and contact cards.  
  
 You can create your email messages directly in Outlook, or you can create your messages in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]. For more information, see [How to: Send Email Messages](../../WorkingWithDynamics/how-to-send-email-messages.md).  
  
> [!IMPORTANT]  
>  The interaction template associated with email logging must have the following characteristics:  
>   
>  -   Interaction Template Code: EMAIL  
> -   Interaction Group Code: SYSTEM  
  
 When you can create email messages using the **Create Interactions** wizard, these interactions are automatically captured in the **Interactions Log Entries** window based on the interaction template that you used, which requires an attachment. If the correspondence type is E\-MAIL, you can still take advantage of email logging to create a storage location for your company's emails that is widely available for work sharing and transfer. Any interactions will also be captured in the log under the EMAIL Interaction Template code.  
  
 In order to use email logging, you will need sufficient permission sets. Consider using the permission sets BASIC and RM\-CONT as defined in the [!INCLUDE[demolong](../../ApplicationDesign/includes/demolong_md.md)].  
  
### To automate and run email logging  
  
1.  Start the job queue that you have specified to manage email logging. For more information, see [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md) and [How to: Set Up Email Logging for use with the Job Queue](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md).  
  
2.  In your Outlook Sent folder, select the email messages that you want to use in email logging. The messages must be to or from a registered [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] salesperson or contact.  
  
3.  Copy the emails messages to the queue folder that you have set up in Exchange public folders.  
  
    > [!TIP]  
    >  You can use Outlook rules to automate this process. For example, you can set up a rule to always copy mail from a certain contact to your public queue folder. For more information, search Outlook Help for a topic called "Manage messages by using rules."  
  
4.  After the mail in the queue folder is processed and determined to be valid, it is moved to the public storage folder. For more information, see [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md).  
  
5.  In the **Search** box, enter **\($ N\_5076 Interaction Log Entries $\)**, and then choose the related link.  
  
    > [!TIP]  
    >  To limit the log entries that you view to just those of the salesperson, you can open the **\($ N\_5076 Interaction Log Entries $\)** window from the salesperson card.  
  
6.  You can scroll through the document to locate the log entry for the email message that has been logged and moved to the public storage folder.  
  
7.  Select the log entry for the email message that you want to review. To review the mail, on the **Home** tab, choose **Show.** The email message opens in Outlook. You can reply to the mail. To have the mail interaction tracked in the **Interaction Log**, repeat step 3.  
  
## See Also  
 [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md)