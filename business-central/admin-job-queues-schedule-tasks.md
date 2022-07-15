---
title: Schedule jobs to run automatically
description: Scheduled tasks are managed by the job queue. These jobs run reports and codeunits. You can set jobs to run one time, or on a recurring basis.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 672, 673, 674, 671
ms.date: 10/01/2021
ms.author: edupont

---
# Use Job Queues to Schedule Tasks

The Job Queues enable users to schedule and run specific reports and codeunits. You can set jobs to run one time, or on a recurring basis. For example, you might want to run the **Salesperson * Sales Statistics** report weekly to track sales by salesperson each week, or run the **Delegate Approval Requests** codeunit daily to prevent documents from piling up.

The **Job Queue Entries** page lists all existing jobs. If you add a new job queue entry that you want to schedule, you must provide some information. For example:
* The type of object you want to run, such as a report or codeunit. You must have permission to run the particular report or codeunit.
* The name and object ID of the object. 
* Parameters to specify the behavior of the job queue entry. For example, you can add a parameter to only send posted sales orders. 
* When, and how often, the job queue entry will run.

> [!IMPORTANT]  
> If you use the SUPER permissions set that comes with [!INCLUDE[prod_short](includes/prod_short.md)], you and your users have permissions to run all objects within the license. That is still not enough for Delegated Admin or users with Device license, who cannot create job queue entires.

After job queues are set up and running, the status can change as follows within each recurring period:

* **On Hold**  
* **Ready**  
* **In Process**  
* **Error**  
* **Finished**  

After a job finishes successfully it's removed from the list of job queue entries, unless it's a recurring job. For recurring jobs, the **Earliest Start Time** field is adjusted to show the next time that the job is expected to run.  

## Monitor status or errors in the job queue

Data that the job queue generates is stored in the database, so that you can troubleshoot job queue errors.  

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
> You can also view the status of job queue entries by using Application Insights in Microsoft Azure for more in-depth analysis based on telemetry. For more information, see [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) and [Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace) in the [!INCLUDE [prod_short](includes/prod_short.md)] developer and administration content.

## View scheduled tasks

The **Scheduled Tasks** page in [!INCLUDE [prod_short](includes/prod_short.md)] shows which tasks are ready to run in the job queue. The page also shows information about the company that each task is set up to run in. However, only tasks that are marked as belonging to the current environment can run.  

For example, all scheduled tasks stop if the company is in an environment that's a copy of another environment. Use the **Scheduled Tasks** page to set tasks as ready to run in the job queue.  

> [!NOTE]
> Internal administrators and users can schedule tasks to run. Delegated administrators cannot.

## The My Job Queue Part

The **My Job Queue** part on your Role Center shows the job queues entries that you've started but aren't finished. By default the part isn't displayed, but you can add it to your Role Center. For more information, see [Personalize Your Workspace](ui-personalization-user.md).  

The part shows the following information:

* Which documents with your ID in the **Assigned User ID** field are being processed or are queued, including documents that are posting in the background. 
* Whether there was an error when posting a document or in the job queue entry. 

The My Job Queue part also lets you cancel a document posting.

### To view an error from the My Job Queue part

1. On an entry with the status **Error**, choose the **Show Error** action.
2. Review the error message and fix the problem.

## Examples of what can be scheduled using job queue

### Schedule reports

You can schedule a report or batch job to run at a specific date and time. Scheduled reports and batch jobs are entered in the job queue and processed at the scheduled time, similar to other jobs. You choose the **Schedule** option after you choose the **Send to** action, and then you enter information such as printer, time and date, recurrence.  

For more information, see [Scheduling a Report to Run](ui-work-report.md#ScheduleReport)

### Schedule synchronization between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)]

If you've integrated [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)], the job queue lets you schedule when to synchronize data. Depending on the direction and rules you've defined, the job queue entry can create records in one app to match records in the other. A good example is when you register a contact in [!INCLUDE[crm_md](includes/crm_md.md)], the job queue entry can set up that contact for you in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Scheduling a Synchronization between Business Central and Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

### Schedule the posting of sales and purchase orders

You can use job queue entries to schedule business processes to run in the background. For example, background tasks are useful when multiple users post sales orders at the same time, but only one order can be processed at a time. For more information, see [To set up background posting with job queues](ui-batch-posting.md#to-set-up-background-posting-with-job-queues)

## Monitor the job queue with telemetry

As an administrator, you can use [Application Insights](/azure/azure-monitor/app/app-insights-overview) to gather and analyze telemetry that you can use to identify problems. For more information, see [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) in the developer and administration content.  

## See Also

[Administration](admin-setup-and-administration.md)  
[Setting Up Business Central](setup.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace)  


[!INCLUDE[footer-include](includes/footer-banner.md)]