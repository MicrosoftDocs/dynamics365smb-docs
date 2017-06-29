---
title: "Use Job Queues to Schedule Tasks"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "job queues, scheduling tasks"
  - "job queues, using"
ms.assetid: cdf7e841-8a49-40b4-8701-4f1fdc368a88
caps.latest.revision: 9
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Use Job Queues to Schedule Tasks
Job queues in FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] --> --> enables users to schedule and run specific reports and codeunits. You can set jobs to run one time, or on a recurring basis. For example, you might want to run the Salesperson \- Sales Statistics report weekly, to track sales by salesperson each week, or you might want to run the Process Service E\-mail Queue codeunit daily, to make sure pending email messages to customers regarding their service orders are sent out in a timely manner.  
  
 [!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)] also has the following features that use job queues to automate repetitive tasks.  
  
-   Email logging. For more information, see [How to: Set Up Email Logging for use with the Job Queue](../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md).  
  
-   Background posting. For more information, see [How to: Background Post with Job Queues](../SetupAndAdministration/how-to-background-post-with-job-queues.md).  
  
 In the **Job Queue Entries** window, you add information about the job queue entry that you want to schedule, such as a report or codeunit for the object type, the name and object ID of the object that you want to run, recurrence, priority, and status. You can also add parameters to specify the behavior of the job queue entry. For example, you can add a parameter to only send posted sales orders. You must have permission to run the particular report or codeunit, or an error will be returned when the job queue is run. Errors are listed in the **Job Queue Log Entries** window. You can also troubleshoot job queue errors. Data generated when a job queue is run is stored in the database.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Activate and deactivate the job queue.|[How to: Set Up Job Queues](../SetupAndAdministration/how-to-set-up-job-queues.md)|  
|Set the jobs that you want to run, including whether they are reports or codeunits, their object IDs and names, whether they are recurring, and when they should run.|[How to: Create Job Queue Entries](../SetupAndAdministration/how-to-create-job-queue-entries.md)|  
|Find status on jobs in the queue, troubleshoot jobs, activate or deactivate a job queue session, or set priorities for the jobs in the queue.|[How to: Check Job Queues Entries](../SetupAndAdministration/how-to-check-job-queues-entries.md)|  
|Use job queues for background posting.|[How to: Background Post with Job Queues](../SetupAndAdministration/how-to-background-post-with-job-queues.md)|  
  
## See Also  
 [How to: Set Up Email Logging for use with the Job Queue](../BusinessFunctionality/LoggingAndTrackingEmailInteractions/how-to-set-up-email-logging-for-use-with-the-job-queue.md)