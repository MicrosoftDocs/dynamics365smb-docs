---
title: Auditing changes| Microsoft Docs
description: You can activate a user log so that you have a history of any changes made to data in tracked tables. You can also track activities with certain types of activity logs.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: user log, user activity, tracking
ms.date: 04/01/2020
ms.author: edupont

---
# Auditing Changes in Business Central
A common challenge in many business management applications is avoiding unwanted changes in data. It could be anything from an incorrect customer telephone number to an incorrect posting to the general ledger. This topic describes the capabilities for finding out what changed, who changed it, and when the change was made.

## About the Change Log 
The change log lets you track all direct modifications a user makes to data in the database. You must specify each table and field that you want the system to log, and then you must activate the change log.  

The change log is based on changes that are made to data in the tables that you track. On the **Change Log Entries** page, entries are chronologically ordered and show all changes that are made to the values in fields on the tables you specify.

> [!Important]
> Changes display in the **Change Log Entries** only after the user's session is restarted, which happens as follows:
<br />
> * The session expired and was refreshed.
> * The user selected another company or Role Center.
> * The user signed out and back in.

### Working with the Change Log
You activate and deactivate the change log on the **Change Log Setup** page. When a user activates or deactivates the change log, this activity is logged, so you can always see which user deactivated or reactivated the change log.

On the **Change Log Setup** page, if you choose the **Tables** action, you can specify which tables you want to track changes for, and which changes to track. [!INCLUDE[d365fin](includes/d365fin_md.md)] also tracks a number of system tables.

After you have set up the change log, activated it, and made a change to data, you can view and filter the changes on the **Change Log Entries** page. If you want to delete entries, you can do that on the **Delete Change Log Entries** page, where you can set filters based on dates and time.  

## About Activity Logs
From some pages in [!INCLUDE [prodshort](includes/prodshort.md)], you can view an activity log that shows the status and any errors from files that you export from or import into [!INCLUDE [prodshort](includes/prodshort.md)].  

### Working with Activity Logs
The information is displayed in the **Activity Log** page according to the context that it is opened from. For example, you can open the page from the **Document Exchange Service Setup**, **Incoming Document**, **Posted Sales Invoice**, and **Posted Sales Credit Memo** pages. You can empty the list of log entries, or just clear the list of entries older than seven days.  

## Monitoring Sensitive Fields
Keeping sensitive data secure and private is a core concern for most businesses. To add a layer of security, you can monitor important fields and be notified by email when someone changes a value. For example, you might want to be notified if someone changes your company's IBAN number.

> [!NOTE]
> Sending notifications by email requires that you set up the email feature in [!INCLUDE [prodshort](includes/prodshort.md)]. For more information, see [Set Up Email](admin-how-setup-email.md).

### Setting Up Field Monitoring
To quickly set up field monitoring, you can use the **Field Monitoring** assisted setup guide to import the fields that you want to monitor based on filter criteria, such as the data sensitivity classification for the fields, and specify the person who will receive an email notification when a change occurs. Afterward, to change the email recipient or turn off field monitoring, you can do so on the **Field Monitoring Setup** page. That page is also where you specify the minimum number of days for which to keep entries for changes. New entries cannot be deleted for the number of days you specify.

> [!TIP]
> Over time, the list of entries on the **Monitored Fields Log Entries** page will grow. To reduce the number of entries, you can either delete one or more entries manually, or you can use a retention policy. 

### Working with Field Monitoring
You can manage settings for field monitoring, such as whether to send an email notification or just log the change, for each field on the **Monitored Fields Worksheet** page. The page is also where you can add or remove fields to monitor.

Entries for all changed values for monitored fields are available on the **Monitored Fields Log Entries** page. For example, entries contain information such as the field for which the value was changed, the original and new values, and who made the change and when they did so. To further investigate a change, choose a value to open the page where it was made.



<!--Email Account Name field needs a new name. This is the accoun t that will be used to send notifications to the pertion shocen in the Notification Receipt field. Typically this is not associated with a person. It is not the Notification Recipient\s account Need a tooltip for it too.

You can connect to a Retention Policy to specify how often to delete entries. Link to retention policies help.

Use **Add Fields** to add new fields to monitor.

Use **Set for Notification** and **Clear for Notification** to...

**Field Change Entries** action opens the list of all changes. 

After you add a field, you must sign out and sign in again. 

Show Monitoring Setup Entries and Hide... Buttons show and hide changes to the setup for monitored fields. 

You use the **Monitor Field Change Setup** assisted setup guide to set things up for the first time. You will 

You specify the person who will receive a notification in the **Notification Recipient field**

To start monitoring the selected fields for changes, choose Finish. You will need to restart Business Central. 

After you choose a table for monitoring, it will be hidden in the Change Log setup. This is to avoid redundency in monitoring. You will not see the table on the **Change Log Setup (Table) List** page.

Show notification informing use that some tables are hidden in change log table list as they are monitored in monitor sensitive fields feature.
Notify users that some tables are hidden in the Change Log Table List page because they contain fields that are being monitored for changes.

Notify users about monitor sensitive feature






 

.-->

## Defining Retention Policies
You can create retention policies to delete unneeded data in logs after a period of time that you specify. For example, over time the number of entries in a log can build up. By cleaning up old entries you can make it easier to focus on more recent, and probably more relevant, entries. For more information, see [Define Retention Policies](admin-data-retention-policies.md).

## See Also
[Change Basic Settings](ui-change-basic-settings.md)  
[Sorting, Searching, and Filtering](ui-enter-criteria-filters.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)    
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Define Retention Policies](admin-data-retention-policies.md)  