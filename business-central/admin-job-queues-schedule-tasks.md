---
title: Schedule jobs to run automatically
description: Learn how to use job queue entries to run reports and codeunits.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: conceptual
ms.date: 09/15/2023
ms.custom: bap-template
ms.search.form: 672, 673, 674, 671
---
# Use job queues to schedule tasks

Use the **Job Queue Entries** page to schedule and run specific reports and codeunits. You can set jobs to run one time, or on a recurring basis. For example, you might want to run the **Salesperson * Sales Statistics** report weekly to track sales by salesperson each week, or run the **Delegate Approval Requests** codeunit daily to prevent documents from piling up.

The Job Queue Entries page lists all existing jobs. If you add a new job queue entry that will run on a schedule, you must provide some information. For example:

* The type of object to run, such as a report or codeunit. You must have permission to run the particular report or codeunit.
* The name and object ID of the object.
* Parameters to specify the behavior of the job queue entry. For example, you can add a parameter to only send posted sales orders.
* When, and how often, the job queue entry will run.

> [!IMPORTANT]  
> If you're assigned the SUPER permissions set that comes with [!INCLUDE[prod_short](includes/prod_short.md)], you have permission to run all objects included in your license. If you have the Delegated Admin role, you can create and schedule job queue entries, but only administrators and licensed users can run them.

After job queues are set up and running, the status can change as follows within each recurring period:

* **On Hold**  
* **Ready**  
* **In Process**  
* **Error**  
* **Finished**  
* **On Hold Due to Inactivity**

> [!NOTE]
> The **On Hold Due to Inactivity** status is used primarily for job queue entries that schedule synchronization between [!INCLUDE [prod_short](includes/prod_short.md)] and another application, such as [!INCLUDE [cds_long_md](includes/cds_long_md.md)]. To learn more about this status, go to [About inactivity timeouts](/dynamics365/business-central/admin-scheduled-synchronization-using-the-synchronization-job-queue-entries#about-inactivity-timeouts).

After a job finishes successfully it's removed from the list of job queue entries, unless it's a recurring job. For recurring jobs, the **Earliest Start Time** field is adjusted to show the next time that the job will run. 

## Important for scheduling recurring jobs

> [!IMPORTANT]  
> Recurring job queues can affect performance, so you shouldn't run them too frequently. When you set up how often to run a recurring job, try to set the largest time interval you can. For example, if you're about to set a recurrence of five minutes, consider whether it can be 15 minutes, or even once per hour instead. When planning for recurring job queues, consider which areas of the application the job will affect. Is it an area where many users work and will be impacted by heavy activity? Consider the length of a single job run and the business motivations for running jobs with a given cadence.

## The earliest start date

The value in the **Earliest Start Date/Time** field on the **Job Queue Entry Card** page shows the next time the job will run. There are several factors that can affect whether a job queue entry actually runs at that time.

The most common factors are the number of job queue entries in an environment, and the overall number of scheduled tasks. To protect performance levels, there are operational limits. If you have a lot of entries in the queue and, for example, one of them fails or the entries just take longer than expected, the next job might not start at the expected time. If you have codeunits that are generating 100,000 or more scheduled tasks, you should investigate whether you actually need all of those tasks. You can access the list of all scheduled tasks on the **Scheduled Tasks** page.

To learn more about monitoring the status of job queue entries, go to [To view status for any job](#to-view-status-for-any-job). To learn more about operational limits, go to [Asynchronous task limits](/dynamics365/business-central/dev-itpro/administration/operational-limits-online#Task).

## Monitor status or errors in the job queue

Data that the job queue generates is stored, so that you can troubleshoot errors.  

For each job queue entry, you can view and change the status. When you create a job queue entry, its status is set to **On Hold**. You can set the status to **Ready** and back to **On Hold**, for example. Otherwise, status information is updated automatically.

The following table describes the values of the **Status** field.

| Status | Description |
|--|--|
| Ready | The job queue entry is ready to be run. |
| In Process | The job queue entry is in process. This field updates while the job queue is running. |
| On Hold | The default status of the job queue entry when it's created. Choose the **Set Status to Ready** action to change the status to **Ready**. Choose the **Set On Hold** action to revert the status to **On Hold**. |
| Error | Something went wrong. Choose **Show Error** to show the error message. |
| Finished | The job queue entry is complete. |

> [!Tip]  
> Job queue entries stop running when there's an error. For example, this can be a problem when an entry connects to an external service, such as a bank feed. If the service is temporarily not available and the job queue entry can't connect, the entry will show an error and stop running. You'll have to manually restart the job queue entry. However, the **Maximum No. of Attempts** and **Rerun Delay (sec.)** fields can help you avoid this situation. The **Maximum No. of Attempts** field lets you specify how many times the job queue entry can fail before it stops trying to run. The **Rerun Delay (sec.)** field lets you specify the amount of time, in seconds, between attempts. The combination of these two fields might keep the job queue entry running until the external service becomes available.

### To view status for any job

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, and then choose the related link.
2. On the **Job Queue Entries** page, select a job queue entry, and then choose the **Log Entries** action.  

> [!TIP]
> For in-depth analysis based on telemetry, you can use Application Insights in Microsoft Azure to review the status of job queue entries. To learn more about telemetry, go to [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) and [Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

## View scheduled tasks

The **Scheduled Tasks** page in [!INCLUDE [prod_short](includes/prod_short.md)] shows which tasks are ready to run in the job queue. The page also shows information about the company that each task is set up to run in. However, only tasks that are marked as belonging to the current environment can run.  

For example, all scheduled tasks stop if the company is in an environment that's a copy of another environment. Use the **Scheduled Tasks** page to set tasks as ready to run in the job queue.  

> [!NOTE]
> Internal administrators and licensed users can schedule tasks to run. Delegated administrators can set up and schedule tasks to run, but only licensed users can run them.

## The My Job Queue part

The **My Job Queue** part on your Role Center shows the job queues entries that you've started but aren't finished. By default the part isn't displayed, but you can add it to your Role Center. To learn more about personlization, go to [Personalize Your Workspace](ui-personalization-user.md).  

The part shows the following information:

* Which documents with your ID in the **Assigned User ID** field are being processed or are queued, including documents that are posting in the background. 
* Whether there was an error when posting a document or in the job queue entry. 

The My Job Queue part also lets you cancel a document posting.

### To view an error from the My Job Queue part

1. On an entry with the status **Error**, choose the **Show Error** action.
2. Review the error message and fix the problem.

## Examples of what you can schedule using job queue entries

### Schedule reports

You can schedule a report or batch job to run at a specific date and time. Scheduled reports and batch jobs are entered in the job queue and processed at the scheduled time, similar to other jobs. You choose the **Schedule** option after you choose the **Send to** action, and then you enter information such as printer, time and date, recurrence.  

To learn more about scheduling, go to [Scheduling a Report to Run](ui-work-report.md#ScheduleReport)

### Schedule synchronization between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)]

If you've integrated [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)], the job queue lets you schedule when to synchronize data. Depending on the direction and rules you've defined, the job queue entry can create records in one app to match records in the other. A good example is when you register a contact in [!INCLUDE[crm_md](includes/crm_md.md)], the job queue entry can set up that contact for you in [!INCLUDE[prod_short](includes/prod_short.md)]. To learn more about scheduling, go to [Scheduling a Synchronization between Business Central and Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

### Schedule when to post sales and purchase orders

You can use job queue entries to schedule business processes to run in the background. For example, background tasks are useful when multiple users post sales orders at the same time, but only one order can be processed at a time. To learn more about background posting, go to [To set up background posting with job queues](ui-batch-posting.md#to-set-up-background-posting-with-job-queues).

## Handle job queue entry issues

If a job queue entry shows an error, your first option to resolve the issue is to restart the job queue entry. You can set the status of the job queue entry to **On Hold** and then to **Ready**, or just restart it.

If a restart doesn't help, the issue might be in the code. You can find the owner (also called the *publisher*) of the code in the AL stack trace in the Job Queue log. If the error comes from an app/extension, contact your Microsoft partner. If the error comes from a Microsoft application, open a support request with Microsoft.

If you contact your Microsoft partner or Microsoft for support, please provide the following information:

* The ID of the job queue entry run where the error occurred
* The timestamp of when the error occurred
* Your timezone

> [!TIP]
> Depending on whether your [!INCLUDE [prod_short](includes/prod_short.md)] is earlier or later than version 22.1, gather the information in the following ways:
>
> * For earlier versions, provide a screenshot of the **Job Queue Log Entries** page.
> * For later versions, use the **Copy details** action on the Job Queue Log Entries page to copy the information (job queue ID, timestamp, and your timezone).

## Monitor the job queue with telemetry

Administrators can use [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) to gather and analyze telemetry that helps identify problems. To learn more about telemetry, go to [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) and [Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

Telemetry lets administrators set up alerts on job queue issues that send a text message, email, or a message in Teams if something isn't right. To learn more about these alerts, go to [Alert on Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-alert).

## See also

[Administration](admin-setup-and-administration.md)  
[Setting Up Business Central](setup.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace)  
[Alert on Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-alert)

[!INCLUDE[footer-include](includes/footer-banner.md)]
