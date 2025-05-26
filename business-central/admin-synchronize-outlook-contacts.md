---
title: Share contacts between Business Central and Outlook
description: This service has deep integration with Microsoft 365 so you can share contacts between Outlook and Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: contacts, Microsoft 365
ms.search.form: 6700, 5320, 5300, 5301, 5302, 5303, 5304, 5305, 5306, 5307, 5308, 5309, 5310, 5311 
ms.date: 03/17/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Synchronize Contacts in Business Central with Contacts in Microsoft Outlook

You can set up contact synchronization so that your contacts in [!INCLUDE[prod_short](includes/prod_short.md)] have the same information as your contacts in Microsoft Outlook. For example, if you're a sales person, you might work in Outlook and [!INCLUDE[prod_short](includes/prod_short.md)] at the same time. If the contacts are the same in both places, your work is more straightforward.  

By default, the contacts you're syncing are kept in a **Business Central** folder in your Favorites on the Folder Pane in Outlook. The Business Central folder can make it easier to identify which contacts you're syncing. You can set filters to sync only specific contacts from [!INCLUDE[prod_short](includes/prod_short.md)] to Outlook. After you've set up synchronization, you can synchronize manually or automate the process to synchronize on a scheduled basis.  

## Prerequisites

- You user profile in [!INCLUDE[prod_short](includes/prod_short.md)] must specify your Microsoft 365 email account.

  You can check this setting in the **Microsoft 365 Authentication** section of your user profile in the **Users** list.
- With [!INCLUDE[prod_short](includes/prod_short.md)], you've set up contact synchronization as described in [Set Up Contact Synchronization with Outlook for Business Central On-premises](admin-contact-sync-setup-onprem.md)

## Set Up Synchronization

You set up how you want to synchronize contacts with Outlook on the **Exchange Sync. Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. 

On the **Exchange Sync. Setup** page, you can validate that the connection to Exchange is working and then set up contact synchronization. From the **Exchange Sync. Setup** page, you can open the **Contact Sync. Setup** page and start the synchronization. Optionally, set a filter to specify which contacts to synchronize. For example, you can filter on name, type, company, and so on. You can also change the default name of the folder in Outlook that the contacts will synchronize to.  

Each of your coworkers can also set up their own Exchange synchronization and set their own filters on which contacts to synchronize.  

After you set up synchronization, you can sync changes to the contact manually, or you can automate the process by setting up a job queue entry. For more information about automation, see the next section in this article.

### Automate synchronization

You can create a job queue entry that will synchronize contacts according to a schedule that you define. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md). 

The following table lists the settings on the **Job Queue Entry Card** page that are for synchronizing contacts:

|Field|Setting for Contact Sync|
|-----|-----|
|Object Type to Run|Codeunit|
|Object ID to Run|6700|

## Synchronize Contacts

If you're used to working with contacts in [!INCLUDE[prod_short](includes/prod_short.md)], you'll find it easy to sync manually from the **Contacts** list whenever it suits you. You can synchronize contacts in two ways:

* **Sync with Microsoft 365**

  Synchronize all changes from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft 365 that were made after the last synchronization, based on the last modified date. Also, new contacts from Microsoft 365 will be synchronized to [!INCLUDE[prod_short](includes/prod_short.md)]. Typically, this action is faster than a full sync. 

* **Full Sync with Microsoft 365**

  Synchronize all contacts in both directions, regardless of the last sync date and last modified date.  

In both cases, contacts are only synchronized from Outlook if they have the required fields filled in. The required fields to synchronize to Microsoft 365 are **Name**, **Email address** and the contact must be of the type **Person**. [!INCLUDE[prod_short](includes/prod_short.md)] is the source of the contact information, so the [!INCLUDE[prod_short](includes/prod_short.md)] contact information will be saved if there are duplicates.  

> [!NOTE]
> If you delete a contact in Outlook, but keep it in [!INCLUDE[prod_short](includes/prod_short.md)], the contact will be recreated in Outlook the next time you sync. 

## Related information

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Use contacts (People) in Outlook on the web](https://support.office.com/article/Using-contacts-People-in-Outlook-on-the-web-1e3438c7-26b2-420c-87de-3cea9d31b5cb?appver=OWB150)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
