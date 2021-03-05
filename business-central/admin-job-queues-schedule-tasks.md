---
title: Schedule jobs to run automatically
description: Scheduled tasks are managed by the job queue. These jobs run reports and codeunits. You can set jobs to run one time, or on a recurring basis.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 01/12/2021
ms.author: edupont

---
# Use Job Queues to Schedule Tasks

Job queues in [!INCLUDE[prod_short](includes/prod_short.md)] enable users to schedule and run specific reports and codeunits. You can set jobs to run one time, or on a recurring basis. For example, you might want to run the **Salesperson * Sales Statistics** report weekly, to track sales by salesperson each week, or you might want to run the **Delegate Approval Requests** codeunit daily, to prevent documents from piling up or otherwise block the workflow.

The **Job Queue Entries** page lists all existing jobs. If you add a new job queue entry that you want to schedule, you must specify information about the type of object you want to run, such as a report or codeunit, and the name and object ID of the object that you want to run. You can also add parameters to specify the behavior of the job queue entry. For example, you can add a parameter to only send posted sales orders. You must have permission to run the particular report or codeunit, or an error will be returned when the job queue is run.  
> [!IMPORTANT]  
> If you use the SUPER permissions set that comes with [!INCLUDE[prod_short](includes/prod_short.md)], you and your users have permissions to run all objects within the license. That is still not enough for Delegated Admin or users with Device license, who cannot create job queue entires.

A job queue can have many entries, which are the jobs that the queue manages and runs. Information in the entry specifies what codeunit or report is run, when and how often the entry is run, in what category the job runs, and how it runs.  

After job queues are set up and running, the status can change as follows within each recurring period:

* **On Hold**  
* **Ready**  
* **In Process**  
* **Error**  
* **Finished**  

After a job has finished successfully, it is removed from the list of job queue entries unless it is a recurring job. If it is a recurring job, the **Earliest Start Time** field is adjusted to show the next time that the job is expected to run.  

## To view status or errors in the job queue

Data that is generated when a job queue is run is stored in the database, so that you can troubleshoot job queue errors.  
For each job queue entry, you can view and change the status. When you create a job queue entry, its status is set to **On Hold**. You can set the status to **Ready** and back to **On Hold**, for example. Otherwise, status information is updated automatically.

The following table describes the values of the **Status** field.

| Status | Description |
|--|--|
| Ready | Indicates that the job queue entry is ready to be run. |
| In Process | Indicates that the job queue entry is in process. This field is updated while the job queue is running. |
| On Hold | Default. Indicates the status of the job queue entry when it is created. Choose the **Set Status to Ready** action to change the status to **Ready**. Choose the **Set On Hold** or **Suspend** actions to change the status back to **On Hold**. |
| Error | Indicates that there is an error. Choose **Show Error** to see the error message. |
| Finished | Indicates that the job queue entry is complete. |

### To view status for any job
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, and then choose the related link.
2. On the **Job Queue Entries** page, select a job queue entry, and then choose the **Log Entries** action.  

> [!TIP]
> With [!INCLUDE [prod_short](includes/prod_short.md)] online, you can also view the status of job queue entries by using Application Insights in Microsoft Azure. For more information, see [Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace) in the [!INCLUDE [prod_short](includes/prod_short.md)] Developer and Administration content.

## The My Job Queue Part
The **My Job Queue** part on your Role Center shows the job queues entries that you have started, but which are not yet finished. By default, the part is not visible, so you have to add it to your Role Center. For more information, see [Personalize Your Workspace](ui-personalization-user.md).  

The part shows which documents with your ID in the **Assigned User ID** field are being processed or are queued, including those related to background posting. The part can tell you at a glance whether there has been an error in the posting of a document or if there are errors in a job queue entry. The part also lets you cancel a document posting if it is not running.

### To view an error from the My Job Queue part
1. On an entry with the status **Error**, choose the **Show Error** action.
2. Review the error message and fix the problem.


## Examples of what can be scheduled using job queue

### Schedule reports

You can schedule a report or batch job to run at a specific date and time. Scheduled reports and batch jobs are entered in the job queue and processed at the scheduled time, similar to other jobs. You choose the **Schedule** option after you choose the **Send to** action, and then you enter information such as printer, time and date, recurrence.  

For more information, see [Scheduling a Report to Run](ui-work-report.md#ScheduleReport)

### Schedule synchronization between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[prod_short](includes/cds_long_md.md)]

If you have integrated [!INCLUDE[prod_short](includes/prod_short.md)] with [!INCLUDE[prod_short](includes/cds_long_md.md)], you can use the job queue to schedule when you want to synchronize data for the records that you have coupled in the two business apps. Depending on the direction and rules that you have defined for the integration, the synchronization jobs can also create new records in the destination app to match those in the source. For example, if a salesperson creates a new contact in [!INCLUDE[crm_md](includes/crm_md.md)], the synchronization job can create that contact for the coupled salesperson in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Scheduling a Synchronization between Business Central and Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

### Schedule the posting of sales and purchase orders

Job queues are an effective tool to schedule the running of business processes in the background, such as when multiple users are trying to post sales orders, but only one order can be processed at a time.  

For more information, see [To set up background posting with job queues](ui-batch-posting.md#to-set-up-background-posting-with-job-queues)

## See Also

[Administration](admin-setup-and-administration.md)  
[Setting Up Business Central](setup.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Analyzing Job Queue Lifecycle Trace Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace)  


[!INCLUDE[footer-include](includes/footer-banner.md)]