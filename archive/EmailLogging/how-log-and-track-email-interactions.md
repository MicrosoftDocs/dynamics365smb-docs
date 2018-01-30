---
    title: Logging and Tracking Email Interactions | Microsoft Docs
    description: Email logging in [!INCLUDE[d365fin](includes/d365fin_md.md)] contacts.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: logging, email, interactions, contacts
    ms.date: 09/05/2017
    ms.author: bholtorf

---
# Log and Track Email Interactions
Email logging is designed to capture interactions between senders and the recipients on the **To:** line of email messages. It captures the interactions that have been successfully concluded; interactions that are in a postponed state are not tracked.  
  
Email logging uses Exchange Web Services to access an Exchange server. It uses a specified mail folder on the Exchange Server, called the queue folder. After an email message is retrieved from the queue folder, it is copied to another folder, called a storage folder. The email interaction is logged in the **Interaction Log Entry** table in [!INCLUDE[d365fin](includes/d365fin_md.md)]. You can view the entries in the **Interaction Log Entries** window.  
  
> [!IMPORTANT]  
>  You must configure Exchange to allow public folders. This configuration is different across versions of Exchange. For more information, see [Public folders in Exchange Server 2013](http://go.microsoft.com/fwlink/?LinkId=526140).  
  
## Email Logging Rules  
The following table describes how mail messages are processed after they arrive in the Queue folder.  
  
|Condition|Action|  
|---------------|------------|  
|Email message is tagged Normal, and there is a valid email address in [!INCLUDE[d365fin](includes/d365fin_md.md)] for the salesperson and the contact.|The message is logged, if there is no duplicate message.|  
|Email message in queue folder is tagged Sensitive.|The message is deleted. If the email message is marked with a sensitivity level other than Normal, that is, **Private**, **Personal**, or **Confidential**, the message is deleted.|  
|Email address is not registered in [!INCLUDE[d365fin](includes/d365fin_md.md)] is designed to log interactions only between salespersons and purchasers, and their known contacts. It does not track interactions with customers.|  
|Email message is a duplicate of a message in storage folder.|The message is not copied to the storage folder and is deleted from the queue folder. The message is examined for a match.|  
|Email address is longer than 80 characters.|The message is not copied and is deleted from the queue folder.|  

## Security Considerations for Email Logging
Email messages received through the Internet can have fake sender addresses. That means that interaction log entries in [!INCLUDE[d365fin](includes/d365fin_md.md)] that are created from email logging could potentially include fake addresses and should be reviewed for security reasons.  
  
Before opening any mail message, make sure that you recognize the sender’s email address. In addition, we recommend that a [!INCLUDE[d365fin](includes/d365fin_md.md)] administrator follows the latest security best practices guidance.  
  
For more information about the steps that you can take to make your application more secure, see [Security TechCenter](http://go.microsoft.com/fwlink/?LinkID=80207).  

## To run email logging
Email logging can be used to capture email activities between salespersons and contacts. Both persons must have valid email addresses that are registered on the respective salesperson and contact cards.  

 You can create email messages in Outlook, or in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Send Documents by Email](ui-how-send-documents-email.md).  

> [!IMPORTANT]  
>  The interaction template associated with email logging must have the following characteristics:  
>   
>  * Interaction Template Code: EMAIL  
>  * Interaction Group Code: SYSTEM  

When you can create email messages using the **Create Interactions** assisted setup guide, these interactions are automatically captured in the **Interactions Log Entries** window based on the interaction template that you used, which requires an attachment. If the correspondence type is **EMAIL**, you can still take advantage of email logging to create a storage location for your company's emails that is widely available for work sharing and transfer. Any interactions will also be captured in the log under the EMAIL Interaction Template code.  

To use email logging, you must have sufficient permissions. Consider using the permission sets **BASIC** and **RM-CONT** as defined in the [!INCLUDE[d365fin](includes/d365fin_md.md)].  


1. Start the job queue that you have specified to manage email logging.
2. In your Outlook Sent Items folder, choose the email messages to use in email logging. The messages must be to or from a registered salesperson or contact in [!INCLUDE[d365fin](includes/d365fin_md.md)].  
3. Copy the email messages to the queue folder that you have set up in Exchange public folders.  
  
    > [!TIP]  
    >  You can use Outlook rules to automate this process. For example, you can set up a rule to always copy mail from a certain contact to your public queue folder. For more information, search Outlook Help for a topic called "Manage messages by using rules."  

4. After the email message in the queue folder is processed and validated, it is moved to the public storage folder.   
5. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Interaction Log Entries**, and then choose the related link.  

    > [!TIP]  
    >  To limit the log entries that you view to just those of the salesperson, you can open the **Interaction Log Entries** window from the salesperson card.  

6. You can scroll through the document to locate the log entry for the email message that has been logged and moved to the public storage folder.  
7. Select the log entry for the email message that you want to review. To review the mail, choose the **Show** action. The email message opens in Outlook. You can reply to the mail. To have the mail interaction tracked in the **Interaction Log**, repeat step 3.

## Troubleshooting: Email Logging
This section describes some common problems that you may see when you use email logging.  

### Managing Logging for Multiple Contacts Who Use One Email Address  
In some [!INCLUDE[d365fin](includes/d365fin_md.md)] company installations, one email address may be used by several contacts in a company. In this case, email interactions are logged only against the first contact, based on and ordered by the **No.**.  

To change this behavior, update the inheritance settings that you have specified in the **Marketing Setup** window. On the **Inheritance** FastTab, clear the **Communication Details** check box.  

### Using Email Logging in a Multiple Exchange Server Environment  
When you are using public folders in a multiple Exchange Server environment, you may encounter delays in seeing a mail message synchronize among the servers. For example, a mail message on one server can take several minutes to be synchronized with another server on the same domain. This can manifest itself when you are using email logging with job queues.  

As a result, during synchronization you may get the following message when you try to display the mail: The email message cannot be displayed or has been deleted.  

### Setting Up an Interaction Template for Email Logging  
 When you are working with interactions and the email logging feature, you should be aware of the following requirements:  

* The interaction template code must point to an existing interaction template.  
* The interaction group code must be SYSTEM.  

For more information, see [Recording Interactions with Contacts Automatically](marketing-auto-record-interactions.md).  

### Changing Storage Locations  
You can update the storage location for your email messages, with the following considerations.  

If you leave logged email messages in the original storage folder, then you can view the messages from the **Interaction Log Entries** window. In that window, select the log entry and on the **Home** tab, choose **Show**.  

If you move the logged messages to another storage location, you cannot view the message from the **Interaction Log Entries** window, as the location and ID of the message has changed.  

To respond, update the information in the **Marketing Setup** window. Then you can copy or move the messages to the public queue folder and reprocess the mail messages.  

### Logging Interaction Links are Lost When You Upgrade from Microsoft Dynamics NAV 2009 R2  
When you upgrade from [!INCLUDE[d365fin](includes/d365fin_md.md)], the link between interaction records and logged email messages is lost.  

To resolve this issue, the administrator has to log all mails again to restore the links. Although logging a large volume of mail messages can be a lengthy process, you can improve performance if email logging is configured to run on its own dedicated server instance. The administrator can use one of the following methods:  

* Copy all mails that are in the storage folder to the queue folder. The mail messages will be logged again.  
* Rename the existing storage folder as the queue folder, so that the messages are logged again. In this instance, you will also want to re-create a storage folder.  

### Upgrades to Job Queue Functionality Require Changes in Your Email Logging Implementation  
Job queue categories have been introduced in [!INCLUDE[d365fin](includes/d365fin_md.md)]. Accordingly, to upgrade email logging, you will have to update your implementation to reflect this change.  

For more information, see [Set Up Job Queues](../how-to-create-job-queue-categories.md).  

### Error when viewing mail based on interaction log entries  
**Description**: An error may appear when you want to view a logged email in the **Interaction Log Entries** window. The error occurs when [!INCLUDE[d365fin](includes/d365fin_md.md)] attempts to open the corresponding email in Microsoft Outlook.  

**Workaround**: Make sure that you are not running either [!INCLUDE[d365fin](includes/d365fin_md.md)] or Outlook as administrator. Otherwise, close all instances of Outlook, and then, in the **Interaction Log Entries** window, choose **Show** again. 

## See Also  
[Walkthrough: Logging Email Interactions in the Database](walkthrough-logging-email-interactions-in-the-database.md)   
[Set Up Email Logging](how-to-set-up-email-logging.md)   
