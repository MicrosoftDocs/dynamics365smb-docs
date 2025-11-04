---
title: Auditing changes
description: Track changes to data in selected tables and monitor user activities with change logs and activity logs in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: user log, user activity, tracking, audit changes
ms.search.form: 592, 593, 594, 595, 710, 1366, 1367, 1368, 1369
ms.date: 10/16/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Audit changes

A common challenge in many business management applications is avoiding unwanted changes in data. It could be anything from an incorrect customer telephone number to an incorrect posting to the general ledger. This article describes the capabilities for finding out what changed, who changed it, and when the change was made.

## About the change log

The change log lets you track all direct modifications a user makes to data in the database. You specify each table and field that you want the system to log, and then you activate the change log. The change log is based on changes that are made to data in the tables that you track. On the **Change Log Entries** page, entries are chronologically ordered and show all changes that are made to the values in fields on the tables you specify.

Tracking changes can affect performance, which can cost you time, and increase the size of your database, which might cost you money. To reduce those costs, keep the following things in mind:

- Use caution when choosing the tables and operations.
- Don't add ledger entries and posted documents. Instead, prioritize system fields such as Created By and Created Date.
- Don't use the **All Fields** tracking type. Instead, choose **Some Fields** and track only the most important fields.

> [!NOTE]
> The Change Log doesn't track changes for fields that use the `autoIncrement property`. An example of a field that uses the property is the Integer field on the Error Messages and VAT Report Line tables.

Also for performance reasons, the change log is turned off during the process of upgrading [!INCLUDE [prod_short](includes/prod_short.md)] to the next version. In addition to speeding up the upgrade process, turning off the log also helps reduce clutter in the change log. As soon as the upgrade is complete, the log starts tracking changes again.

> [!Important]
> Changes display in the **Change Log Entries** only after the user's session is restarted, which happens as follows:
>
> - The session expired and was refreshed.
> - The user selected another company or Role Center.
> - The user signed out and signed in again.

## Set up the change log

On the **Change Log Setup** page, you can turn on or turn off the change log. When you do, the activity is logged, so you can always see who made the change.

On the **Change Log Setup** page, if you choose the **Tables** action, you can specify which tables you want to track changes for, and which changes to track. [!INCLUDE[prod_short](includes/prod_short.md)] also tracks several system tables.

> [!NOTE]
> You can monitor specific fields for changes, such as fields that contain sensitive data, by setting up field monitoring. If you do, to avoid redundancy the table that contains the field will not be available for the change log setup. Learn more in [Monitor Sensitive Fields](across-log-changes.md#monitor-sensitive-fields).

After you set up the change log, activated it, and made a change to data, you can view and filter the changes on the **Change Log Entries** page. If you want to delete entries, set up a retention policy, where you can set filters based on dates and time. Learn more in [Define Retention Policies](admin-data-retention-policies.md) for information about retention policies.  

## Analyze data in the change log

You can use the **Data Analysis** feature to analyze data in the Change Log from the [Change Log Entries](https://businesscentral.dynamics.com/?page=595) page. You don't have to run a report or open another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "Who changed what data, and when," or "Data changes by table/field," or any other view you can imagine. Learn more in [Analyze list and query data with analysis mode](analysis-mode.md) for information about how to use the **Data Analysis** feature.

### Change log ad-hoc analysis scenarios

The following sections provide examples of scenarios where analyzing change log can help you monitor and audit important changes.

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Who changed what data, and when](#example-who-changed-what-data-and-when) | See who changed what data. | [Change Log Entries](https://businesscentral.dynamics.com/?page=595&layout=analysis) | **User ID**, **Date and Time**, **Table Caption**, **Field Caption**, **Primary Key Value 2**, **Primary Key Value 3**, **Type of Change**, **Old Value**, and **New Value**. |
| [Data changes by table/field](#example-data-changes-by-tablefield) | See data changes by table/field, and who made the change. | [Change Log Entries](https://businesscentral.dynamics.com/?page=595&layout=analysis) | **Table Caption**, **Field Caption**, **User ID**, **Date and Time**, **Primary Key Value 2**, **Primary Key Value 3**, **Type of Change**, **Old Value**, and **New Value**. |

### Example: Who changed what data, and when

To analyze Who changed What data When, follow these steps:

1. Open the [Change Log Entries](https://businesscentral.dynamics.com/?page=595&layout=analysis) list, and choose the :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: icon to turn on analysis mode.
1. On the **Columns** menu, remove all columns (select the box next to the **Search** field on the right).
1. Drag the **User ID** field (who did it) to the **Row Groups** area.
1. Now choose the following fields:
   - To show when it happened, choose **Date and Time**.
   - To show the table where it happened, choose **Table Caption**. 
   - To show which field, choose **Field Caption**.
   - To show the field code, choose **Primary Key Value 2**. 
   - To show the company name, choose **Primary Key Value 3**.
   - To show whether the change was an insert, update, or delete action, choose **Type of Change**.
   - To show the change, choose **Old Value** and **New Value**.
1. Rename your analysis tab to **Who changed what data when**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source=" media/data-analysis-change-log-entries-Who-changed-What-data-When.png" alt-text="Example of how to do data analysis on the Change Log Entries page (Who changed What data When)." lightbox="media/data-analysis-change-log-entries-Who-changed-What-data-When.png":::

### Example: data changes by table/field

To analyze data changes by table/field, follow these steps:

1. Open the [Change Log Entries](https://businesscentral.dynamics.com/?page=595&layout=analysis) list, and choose the :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: icon to turn on analysis mode.
1. On the **Columns** menu, remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Table Caption** (on what table), and **Field Caption** (on which field) fields to the **Row Groups** area.
1. Now choose the following fields:
   - To show when it happened, choose **Date and Time**
   - To show who made the change, choose **User ID**.
   - To show the code for the field, choose **Primary Key Value 2**.
   - To show the company name, choose **Primary Key Value 3** (typically the company name), 
   - To show whether the change was an insert, update, or delete action, choose **Type of Change**.
   - To show the change, choose **Old Value** and **New Value**.
1. Rename your analysis tab to **Data changes by table + field**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source=" media/data-analysis-change-log-entries-data-changes-by-table-field.png" alt-text="Example of how to do data analysis on the Change Log Entries page (data changes by table/field)." lightbox="media/data-analysis-change-log-entries-data-changes-by-table-field.png":::

## About activity logs

From some pages in [!INCLUDE [prod_short](includes/prod_short.md)], you can view an activity log that shows the status and any errors from files that you export from or import into [!INCLUDE [prod_short](includes/prod_short.md)].  

### Work with activity logs

The information is displayed on the **Activity Log** page according to the context you opened it from. For example, you can open the page from the **Document Exchange Service Setup**, **Incoming Document**, **Posted Sales Invoice**, and **Posted Sales Credit Memo** pages. You can empty the list of log entries, or just clear the list of entries older than seven days.  

## Monitor sensitive fields

Keeping sensitive data secure and private is a core concern for most businesses. To add a layer of security, you can monitor important fields and get an email when someone changes a value. For example, you might want to be notified if someone changes your company's IBAN number.

> [!NOTE]
> Sending notifications by email requires that you set up the email feature in [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more in [Set Up Email](admin-how-setup-email.md).

### Set up field monitoring

You can use the **Monitor Field Change Setup** assisted setup guide to specify the fields that you want to monitor based on filter criteria, such as the data sensitivity classification for the fields. Learn more in [Classifying Data Sensitivity](admin-classifying-data-sensitivity.md). The guide also lets you specify the person who receives an email notification when a change occurs, and the email account that sends the notification. Specify both the user to notify and the account from which to send the notification. After you finish the guide, you can manage settings for field monitoring on the **Field Monitoring Setup** page.

> [!NOTE]
> When you specify the email account from which to send notifications, you must add either the **Microsoft 365** or **SMTP** account types. Notifications should be sent from an account that isn't associated with an actual user. Therefore you can't choose the **Current User** account type. If you do, notifications will not be sent.

Over time, the list of entries on the **Monitored Fields Log Entries** page will grow. To reduce the number of entries, you can create a retention policy that will delete entries after a specified period of time. Learn more in [Define Retention Policies](admin-data-retention-policies.md).

When you set up field monitoring, or change something in the setup, entries are created for your changes. You can specify whether to display entries related to the monitoring setup by showing or hiding them.

You can manage settings for field monitoring, such as whether to send an email notification or just log the change, for each field on the **Monitored Fields Worksheet** page. The page is also where you can add or remove fields to monitor.

> [!NOTE]
> After you add one or more fields and start monitoring, you must sign out of [!INCLUDE[prod_short](includes/prod_short.md)] and sign in again to apply your settings.

### Work with field monitoring

Entries for all changed values for monitored fields are available on the **Monitored Fields Log Entries** page. For example, entries contain the following information:

- The field in which the value changed.
- The original and new values.
- Who made the change, and when they did so.

To further investigate a change, choose a value to open the page where it was made. To view a list of all entries, choose **Field Change Entries**.

### View field monitoring telemetry

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to send field monitoring activity to an Application Insights resource in Microsoft Azure. Then, using Azure Monitor, you create reports and set up alerts on the gathered data. Refer to the following articles in the [!INCLUDE[prod_short](includes/prod_short.md)] Developer and IT Pro help:

- [Monitoring and Analyzing Telemetry - Enabling Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-overview?toc=/dynamics365/business-central/toc.json#enable)
- [Analyzing Field Monitoring Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-field-monitoring-trace?toc=/dynamics365/business-central/toc.json)

## Define retention policies

You can create retention policies to delete unneeded data in logs after a period of time that you specify. For example, over time the number of entries in a log can build up. By cleaning up old entries you can make it easier to focus on more recent, and probably more relevant, entries. Learn more in [Define Retention Policies](admin-data-retention-policies.md) for information about retention policies.

## Related information

[Monitor Sensitive Fields](across-log-changes.md#monitor-sensitive-fields)  
[Analyze Field Monitoring Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-field-monitoring-trace?toc=/dynamics365/business-central/toc.json)  
[Define Retention Policies](admin-data-retention-policies.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Sort, Search, and Filter](ui-enter-criteria-filters.md)  
[Find Pages and Information with Tell Me](ui-search.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
