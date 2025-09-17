---
title: Schedule jobs to run automatically
description: Learn how to use job queue entries to run reports and codeunits.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 08/26/2024
ms.custom: bap-template
ms.search.form: 672, 673, 674, 671
ms.service: dynamics-365-business-central
---
# Use job queues to schedule tasks

Use the **Job Queue Entries** page to schedule and run specific reports and codeunits. You can set jobs to run one time, or on a recurring basis. For example, you might want to run the **Salesperson * Sales Statistics** report weekly to track sales by salesperson each week, or run the **Delegate Approval Requests** codeunit daily to prevent documents from piling up.

The **Job Queue Entries** page lists all existing jobs. If you add a job queue entry that runs on a schedule, you must provide some information. For example:

* The type of object to run, such as a report or codeunit. You must have permission to run the report or codeunit.
* The name and object ID of the object.
* Parameters to specify the behavior of the job queue entry. For example, you can add a parameter to only send posted sales orders.
* The schedule for when, and how often, the job queue entry runs.

> [!IMPORTANT]  
> If you're assigned the SUPER permissions set that comes with [!INCLUDE[prod_short](includes/prod_short.md)], you have permission to run all objects included in your license. If you have the Delegated Admin role, you can create and schedule job queue entries, but only administrators and licensed users can run them.

After a job finishes successfully, [!INCLUDE [prod_short](includes/prod_short.md)] removes it from the list of job queue entries, unless it's a recurring job. For recurring jobs, the **Earliest Start Time** field is adjusted to show the next time that the job will run.

## Examples of what you can schedule using job queue entries

### Schedule reports

You can schedule a report or batch job to run at a specific date and time. Scheduled reports and batch jobs are entered in the job queue and processed at the scheduled time, similar to other jobs. You choose the **Schedule** option after you choose the **Send to** action, and then you enter information such as printer, time, date, and recurrence.  

To learn more about scheduling, go to [Scheduling a Report to Run](ui-work-report.md#ScheduleReport)

### Schedule synchronization between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)]

If you integrate [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)], the job queue lets you schedule when to synchronize data. Depending on the direction and rules you define, the job queue entry can create records in one app to match records in the other. A good example is when you register a contact in [!INCLUDE[crm_md](includes/crm_md.md)], the job queue entry can set up that contact for you in [!INCLUDE[prod_short](includes/prod_short.md)]. To learn more about scheduling, go to [Scheduling a Synchronization between Business Central and Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

### Schedule when to post sales and purchase orders

You can use job queue entries to schedule business processes to run in the background. For example, background tasks are useful when multiple users post sales orders at the same time, but only one order can be processed at a time. To learn more about background posting, go to [To set up background posting with job queues](ui-batch-posting.md#to-set-up-background-posting-with-job-queues).

## Important for scheduling recurring jobs

> [!IMPORTANT]  
> Recurring job queues can affect performance, so you shouldn't run them too frequently. When you set up how often to run a recurring job, try to set the largest time interval you can. For example, if you're about to set a recurrence of five minutes, consider whether it can be 15 minutes, or even once per hour instead. When planning for recurring job queues, consider which areas of the application the job will affect. Is it an area where many users work and will be impacted by heavy activity? Consider the length of a single job run and the business motivations for running jobs with a given cadence.

## The earliest start date

The value in the **Earliest Start Date/Time** field on the **Job Queue Entry Card** page shows the next time the job will run. There are several factors that can affect whether a job queue entry actually runs at that time.

The most common factors are the number of job queue entries in an environment, and the overall number of scheduled tasks. To protect performance levels, there are operational limits. If you have many entries and, for example, one of them fails or takes longer than expected, the next job might not start at the expected time. If you have codeunits that are generating 100,000 or more scheduled tasks, you should investigate whether you actually need all of those tasks. You can access the list of all scheduled tasks on the **Scheduled Tasks** page.

To learn more about monitoring the status of job queue entries, go to [To view status for any job](#to-view-status-for-any-job). To learn more about operational limits, go to [Asynchronous task limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online#Task).

## Monitor status or errors in the job queue

Data that the job queue generates is stored, so that you can troubleshoot errors.  

For each job queue entry, you can view and change the status. When you create a job queue entry, its status is set to **On Hold**. You can set the status to **Ready** and back to **On Hold**, for example. Otherwise, status information is updated automatically.

The following table describes the values of the **Status** field.

| Status | Description |
|--|--|
| Ready | The job queue entry is ready to be run. |
| In Process | The job queue entry is in process. This field updates while the job queue is running. |
| On Hold | The default status of the job queue entry when you create it. Choose the **Set Status to Ready** action to change the status to **Ready**. Choose the **Set On Hold** action to revert the status to **On Hold**. To learn more, go to [About On Hold](#about-on-hold).|
| On Hold Due to Inactivity | Used primarily for job queue entries that schedule synchronization between [!INCLUDE [prod_short](includes/prod_short.md)] and another application, such as [!INCLUDE [cds_long_md](includes/cds_long_md.md)]. To learn more about this status, go to [About inactivity timeouts](/dynamics365/business-central/admin-scheduled-synchronization-using-the-synchronization-job-queue-entries#about-inactivity-timeouts). |
|Waiting | Only relevant for job queue entries that are assigned a category code. Indicates that the job is scheduled, but the underlying scheduled task isn't active. After the job queue entry that's currently running and is in the same category finishes, the status of the next job in the category with the status Waiting becomes Ready. |
| Error | Something went wrong. Choose **Show Error** to show the error message. |
| Finished | The job queue entry is complete. |

### About On Hold

Setting a job queue entry to **On Hold** doesn't affect a job that's already running. After a job starts, it continues to run until completion, regardless of any subsequent changes made to the job queue entry, such as putting it on hold.<br><br>The **On Hold** status is typically used to prevent a job from automatically starting when it reaches its scheduled start time. It allows you to temporarily pause a job before it begins processing. <br><br>If you need to stop or cancel a running job, you can manually intervene in the process. For example, you can stop the corresponding session or process.

### To view status for any job

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Job Queue Entries**, and then choose the related link.
2. On the **Job Queue Entries** page, select a job queue entry, and then choose the **Log Entries** action.  

> [!TIP]
> For in-depth analysis based on telemetry, you can use Application Insights in Microsoft Azure to review the status of job queue entries. To learn more about telemetry, go to [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) and [Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

## View scheduled tasks

The **Scheduled Tasks** page in [!INCLUDE [prod_short](includes/prod_short.md)] shows which tasks are ready to run in the job queue. The page also shows information about the company that each task is set up to run in. However, only tasks that are marked as belonging to the current environment can run.  

For example, all scheduled tasks stop if the company is in an environment that's a copy of another environment. Use the **Scheduled Tasks** page to set tasks as ready to run in the job queue.  

> [!NOTE]
> Internal administrators and licensed users can schedule tasks to run. Delegated administrators can set up and schedule tasks to run, but only licensed users can run them.

## The My Job Queue part

The **My Job Queue** part on your home page shows the job queues entries that you started but aren't finished. By default the part isn't displayed, but you can add it to your home page. To learn more about personalization, go to [Personalize Your Workspace](ui-personalization-user.md).  

The part shows the following information:

* Which documents with your ID in the **User ID** field are being processed or are queued, including documents that are posting in the background.
* Whether there was an error when posting a document or in the job queue entry.

The My Job Queue part also lets you cancel a document posting.

> [!TIP]
> Another useful feature is the **Job Queue Tasks** cue on your home page. The cue makes it easy to monitor job queue entries based on their status. To learn more, go to [The Job Queue Tasks cue](#the-job-queue-tasks-cue).

### To view an error from the My Job Queue part

1. On an entry with the status **Error**, choose the **Show Error** action.
2. Review the error message and fix the problem.

## The Job Queue Tasks cue

The **Job Queue Tasks** cue on your home page makes it easy to keep an eye on your job queue entries. The cue shows tiles for three statuses:

* Tasks Failed: These tasks need attention. Tasks display in this tile after they exceed the maximum number of attempts to run that you specified for the job queue entry. To learn more, go to [Handle job queue entry issues](#handle-job-queue-entry-issues).
* Tasks in Process: These tasks are running.
* Tasks in Queue: These tasks are waiting their turn.

You can configure the **Job Queue Tasks** cue to use color indicators, so it's easy to know when job queue entries need attention. To learn more about color indicators for cues, go to [Set Up a Colored Indicator on Cues for the Company or Individual Users](admin-how-set-up-colored-indicator-on-cues.md).

## Handle job queue entry issues

Job queue entries stop running when there's an error. For example, this can be a problem when an entry connects to an external service, such as a bank feed. If the service is temporarily not available and the job queue entry can't connect, the entry will show an error and stop running. You'll have to manually restart the job queue entry. However, the **Maximum No. of Attempts** and **Rerun Delay (sec.)** fields can help you avoid this situation. The **Maximum No. of Attempts** field lets you specify how many times the job queue entry can fail before it stops trying to run. The **Rerun Delay (sec.)** field lets you specify the amount of time, in seconds, between attempts. The combination of these two fields might keep the job queue entry running until the external service becomes available.

If a job queue entry shows an error, your first option to resolve the issue is to restart the job queue entry. You can set the status of the job queue entry to **On Hold** and then to **Ready**, or just restart it.

If a restart doesn't help, the issue might be in the code. You can find the owner (also called the *publisher*) of the code in the AL stack trace in the Job Queue log. If the error comes from an app/extension, contact your Microsoft partner. If the error comes from a Microsoft application, open a support request with Microsoft.

If you contact your Microsoft partner or Microsoft for support, provide the following information:

* The ID of the job queue entry runs where the error occurred
* The timestamp of when the error occurred
* Your timezone

> [!TIP]
> Depending on whether your [!INCLUDE [prod_short](includes/prod_short.md)] is earlier or later than version 22.1, gather the information in the following ways:
>
> * For earlier versions, provide a screenshot of the **Job Queue Log Entries** page.
> * For later versions, use the **Copy details** action on the Job Queue Log Entries page to copy the information (job queue ID, timestamp, and your timezone).

### Get notified when a job queue entry fails

If something goes wrong and a job queue entry fails, or isn't scheduled for some reason, you might want to be notified so you can react quickly. You can set up notifications to alert you, your job queue administrator, or both. The notification lets you:

* Restart the job queue entry, which is typically the first thing to try.
* Go directly to details about the failure.

To set up notifications for job queue entry failures, start the **Set Up Job Queue Notifications** assisted setup guide from the **Assisted Setup** page. Use the guide to enter the following settings:

* Who to notify about a failure. You can notify the person who started the job queue entry, or job queue entry administrators, or both.
* How you want to be notified. You can turn on in-product notifications that show at the top of your home page.

   :::image type="content" source="media/in product notification example.png" alt-text="Shows a notification at the top of a home page.":::

   Or, use [external business events](/dynamics365/business-central/dev-itpro/developer/business-events-overview#query-business-central-catalog-of-business-events-in-dataverse) to start a Power Automate flow. You can specify when, how, and who to notify for the flow. Your Power Automate flow must subscribe to the **Job queue task failed** event. To make it easier to create a flow that uses external business events, [!INCLUDE [prod_short](includes/prod_short.md)] provides the [Notify in Outlook when Job Queue in Business Central fails](https://go.microsoft.com/fwlink/?linkid=2288541) Power Platform template. An assisted setup guide helps you get set up in just a few steps. To learn more about Power Automate flows, go to [Use Power Automate flows in Business Central](/dynamics365/business-central/across-how-use-financials-data-source-flow).
* When you want to be notified. You can choose to be notified immediately, or specify thresholds to be notified only after a number of job queue entries fail.

After you set up notifications, you can always turn them on or off. On the **My Notifications** page, for the **Job Queue Failed Notification**, select or clear the **Enabled** checkbox.

## Monitor the job queue with telemetry

Administrators can use [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) to gather and analyze telemetry that helps identify problems. To learn more about telemetry, go to [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) and [Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

Telemetry lets administrators set up alerts on job queue issues that send a text message, email, or a message in Teams if something isn't right. To learn more about these alerts, go to [Alert on Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-alert).

## Related information

[Administration](admin-setup-and-administration.md)  
[Setting Up Business Central](setup.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace)  
[Alert on Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-alert)

[!INCLUDE[footer-include](includes/footer-banner.md)]
