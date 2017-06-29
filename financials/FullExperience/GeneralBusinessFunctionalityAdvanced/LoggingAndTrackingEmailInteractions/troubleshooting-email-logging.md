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
# Troubleshooting: Email Logging
This topic describes some common problems that you may see when you use email logging.  
  
-   [Managing Logging for Multiple Contacts Who Use One Email Address](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md#MultipleContacts)  
  
-   [Using Email Logging in a Multiple Exchange Server Environment](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md#MultiExchangeServer)  
  
-   [Setting Up an Interaction Template for Email Logging](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md#SettingInteractionTemplates)  
  
-   [Changing Storage Locations](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md#ChangingStorage)  
  
-   [Logging Interaction Links are Lost When You Upgrade from Microsoft Dynamics NAV 2009 R2](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md#LoggingInteractionLinks)  
  
-   [Error when viewing mail based on interaction log entries](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/troubleshooting-email-logging.md#ErrorViewingMailBased)  
  
##  <a name="MultipleContacts"></a> Managing Logging for Multiple Contacts Who Use One Email Address  
 In some ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> company installations, one email address may be used by several contacts in a company. In this case, email interactions are logged only against the first contact, based on and ordered by the **No.**.  
  
 To change this behavior, update the inheritance settings that you have specified in the **Marketing Setup** window. On the **Inheritance** FastTab, clear the **Communication Details** check box.  
  
##  <a name="MultiExchangeServer"></a> Using Email Logging in a Multiple Exchange Server Environment  
 When you are using public folders in a multiple Exchange Server environment, you may encounter delays in seeing a mail message synchronize among the servers. For example, a mail message on one server can take several minutes to be synchronized with another server on the same domain. This can manifest itself when you are using email logging with job queues.  
  
 As a result, while synchronization is occurring, you may get the following message when you try to display the mail: The email message cannot be displayed or has been deleted.  
  
##  <a name="SettingInteractionTemplates"></a> Setting Up an Interaction Template for Email Logging  
 When you are working with interactions and the email logging feature, you should be aware of the following requirements:  
  
-   The interaction template code must point to an existing interaction template.  
  
-   The interaction group code must be SYSTEM.  
  
 For more information, see [How to: Set Up Interaction Templates](../../Marketing/how-to-set-up-interaction-templates.md).  
  
##  <a name="ChangingStorage"></a> Changing Storage Locations  
 You can update the storage location for your email messages, with the following considerations.  
  
 If you leave logged email messages in the original storage folder, then you can view the messages from the **Interaction Log Entries** window. In that window, select the log entry and on the **Home** tab, choose **Show**.  
  
 If you move the logged messages to another storage location, you cannot view the message from the **Interaction Log Entries** window, as the location and ID of the message has changed.  
  
 To respond to this behavior, update the information in the **Marketing Setup** window. Then you can copy or move the messages to the public queue folder and reprocess the mail messages.  
  
##  <a name="LoggingInteractionLinks"></a> Logging Interaction Links are Lost When You Upgrade from Microsoft Dynamics NAV 2009 R2  
 When you upgrade from ADD INCLUDE<!--[!INCLUDE[nav2009r2](../../BusinessFunctionality/IntegratingWithMicrosoftDynamicsCRM/includes/nav2009r2_md.md)]--> to ADD INCLUDE<!--[!INCLUDE[nav_current_long](../../ApplicationDesign/includes/nav_current_long_md.md)]-->, the link between interaction records and logged email messages is lost.  
  
 To resolve this issue, the administrator has to log all mails again to restore the links. Although logging a large volume of mail messages can be a lengthy process, you can improve performance if email logging is configured to run on its own dedicated server instance. The administrator can use one of the following methods:  
  
-   Copy all mails that are in the storage folder to the queue folder. The mail messages will be logged again.  
  
-   Rename the existing storage folder as the queue folder, so that the messages are logged again. In this instance, you will also want to re-create a storage folder.  
  
## Upgrades to Job Queue Functionality Require Changes in Your Email Logging Implementation  
 Job queue categories have been introduced in ADD INCLUDE<!--[!INCLUDE[nav_current_long](../../ApplicationDesign/includes/nav_current_long_md.md)]-->. Accordingly, to upgrade email logging, you will have to update your implementation to reflect this change.  
  
 For more information, see [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md) and [How to: Create Job Queue Categories](../../SetupAndAdministration/how-to-create-job-queue-categories.md).  
  
##  <a name="ErrorViewingMailBased"></a> Error when viewing mail based on interaction log entries  
 **Description**: An error may appear when you want to view a logged email in the **Interaction Log Entries** window. The error occurs when ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> attempts to open the corresponding email in Microsoft Outlook.  
  
 **Workaround**: Make sure that you are not running either ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> or Outlook as administrator. Otherwise, close all instances of Outlook, and then, in the **Interaction Log Entries** window, choose **Show** again.  
  
## See Also  
 [Walkthrough: Logging Email Interactions in the Microsoft Dynamics NAV Database](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/walkthrough-logging-email-interactions-in-the-microsoft-dynamics-nav-database.md)   
 [Logging and Tracking Email Interactions](../../BusinessFunctionality/LoggingAndTrackingEmailInteractions/logging-and-tracking-email-interactions.md)