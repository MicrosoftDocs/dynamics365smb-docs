---
title: Schedule jobs to run automatically | Microsoft Docs
description: Scheduled tasks are managed by the job queue. These jobs run reports and codeunits. You can set jobs to run one time, or on a recurring basis.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 09/01/2017
ms.author: edupont

---
# Use Job Queues to Schedule Tasks
Job queues in [!INCLUDE[d365fin](includes/d365fin_md.md)] enables users to schedule and run specific reports and codeunits. You can set jobs to run one time, or on a recurring basis. For example, you might want to run the **Salesperson - Sales Statistics** report weekly, to track sales by salesperson each week, or you might want to run the **Process Service E-mail Queue** codeunit daily, to make sure pending email messages to customers regarding their service orders are sent out in a timely manner.  

## Add Jobs to the Job Queue
The **Job Queue Entries** window lists all existing jobs. If you add a new job queue entry that you want to schedule, you must specify information about the type of object you want to run, such as a report or codeunit, and the name and object ID of the object that you want to run. You can also add parameters to specify the behavior of the job queue entry. For example, you can add a parameter to only send posted sales orders. You must have permission to run the particular report or codeunit, or an error will be returned when the job queue is run.  

Optionally, you can set a filter in the **Job Queue Category Filter** field. Job queue categories can be used to group jobs in the list.

[!INCLUDE[d365fin](includes/d365fin_md.md)] automatically runs the jobs according to the specified schedules for each job queue entry. You can also start, stop, and put a job queue entry on hold manually.

### Log Files
Errors are listed in the **Job Queue Log Entries** window that you can access from the ribbon. You can also troubleshoot job queue errors. Data that is generated when a job queue is run is stored in the database.  

### Background Posting with Job Queues
Job queues are an effective tool to schedule the running of business processes in the background. For example, there may be an instance in which multiple users are trying to post sales orders at the same time, but only one order can be processed at a time. By setting up a background posting routine, you can place the postings in a queue for processing in the background.  

 Alternatively, you may want to schedule postings for hours when it is convenient for your organization. For example, it may make sense in your business to run certain routines when most of the data entry for the day has concluded. You can achieve this by setting the job queue up to run various batch post reports, such as the **Batch Post Sales Orders**, **Batch Post Sales Invoices**, and **Batch Post Sales Credit Memos** reports.  

 [!INCLUDE[d365fin](includes/d365fin_md.md)] supports background posting for the following document types:  

-   Sales: sales order, return order, credit memo, invoice  

-   Purchases: purchase order, return order, credit memo, invoice  

 If the job queue cannot post the sales order, the status is changed to **Error**, and the sales order is added to the list of sales orders that the user will have to handle.  

> [!NOTE]  
>  When you schedule a document for posting and the posting process begins, the posting routine is automatically configured to time out within two hours if the posting routine stops responding for any reason.  

You set up this use of the job queue in the **Sales & Receivables Setup** window or the **Purchases & Payables** window, respectively. On the **Background Posting** FastTab, you choose the **Post Documents via Job Queue** check box and then fill in the relevant information. Here you can also use the **Job Queue Category Code** field to run all job queue entries with that code. For example, you can use  a **SalesPost** category that filters to all sales orders that match any job queue that has the same category code.  

> [!IMPORTANT]  
>  If you set up a job that will post and print documents, and the printer displays a dialog box, such as a request for credentials or a warning about low printer ink, your document is posted but not printed. The corresponding job queue entry eventually times out and the **Status** field is set to **Error**. Accordingly, we recommend that you do not use a printer setup that requires interaction with the display of printer dialog boxes in conjunction with background posting.  

## Use the My Job Queue Part
The **My Job Queue** part shows the job queues entries that a user has started, but which are not yet finished. By default, the part is not visible, so you have to add it to your Role Center. For more information, see [Changing Basic Settings](ui-change-basic-settings.md).  

In this part, you can see those documents that are being processed or that are queued for which your ID is specified in the **Assigned User ID** field. The part helps you keep track of all job queue entries, including those related to background posting. The part can tell you at a glance whether there has been an error in the posting of a document or if there are errors in a job queue entry. The part also lets you cancel a document posting if it is not running.  

## Security  
Job queue entries run based on permissions. Those permissions must allow the execution of the report or codeunit.  

When a job queue is activated manually, it is run with the credentials of the user. When a job queue is activated as a scheduled task, it is run with the credentials of the server instance. When a job is run, it is run with the credentials of the job queue that activates it. However, the user who created that job queue entry must also have permissions. When a job is “run in user session” (such as during background posting), it is run with the credentials of the user who created that job.  

> [!IMPORTANT]  
>  If you use the SUPER permissions set that comes with [!INCLUDE[d365fin](includes/d365fin_md.md)], you and your users have permissions to run all objects. In this case, access for each user is only limited by permissions for data.  

## Using Job Queues Effectively  
The job queue entry record has many fields whose purpose is to carry parameters into a codeunit that you have specified to be run with a job queue. This also means that codeunits that are to be run via the job queue must be specified with the Job Queue Entry record as a parameter in the **OnRun** trigger. This helps provide an extra level of security, as this prevents users from running random codeunits via the job queue. If the user must pass parameters to a report, the only way to do this is by wrapping the report execution into a codeunit, which then parses the input parameters and enters them into the report before executing it.  

## See Also  
[Administration](admin-setup-and-administration.md)  
[Setting Up Business Central](setup.md)  
