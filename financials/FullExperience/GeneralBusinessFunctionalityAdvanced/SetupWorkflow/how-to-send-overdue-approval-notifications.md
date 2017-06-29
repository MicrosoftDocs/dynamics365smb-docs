---
title: "How to: Send Overdue Approval Notifications"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 3f0566dc-2504-4295-a78e-8d04e015fcbf
caps.latest.revision: 4
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
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
# How to: Send Overdue Approval Notifications
At regular intervals, you must remind approval workflow users of overdue approval requests that they must react on. You use the **Send Overdue Approval Notifications** function for this.  
  
 The **Send Overdue Approval Notifications** function checks for all open approval requests that are currently overdue. Each approver that has at least one overdue approval entry receives a notification with the list of all their overdue approval requests. The notification is also sent to their approver and all the requesters of the overdue approvals. This helps if the overdue approval entry must be delegated to a substitute. To see notification entries for overdue approval requests, see [How to: View Overdue Approval Requests](../../BusinessFunctionality/Workflow/how-to-view-overdue-approval-requests.md).  
  
 The due date is either the date when the request was made or it a date calculated from the value in the **due Date Formula** field on the workflow response that represents the approvers action. For more information, see step 9.b. in [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md).  
  
 You can set up the overdue approval notification to include a list of all pending approvals and not just new ones that are overdue. For more information, see [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md).  
  
> [!TIP]  
>  It is advised that you set this function up to run periodically in a job queue. For more information, see [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md).  
  
 Approval of records must be set up as workflows, one workflow for each scenario, such as the Purchase Invoice Approval Workflow. The generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] includes workflow templates for approval of all types of sales and purchase documents and for other records, such as customer cards. For more information, see the list of workflow templates in the Workflow Templates window.  
  
### To send overdue approval notifications  
  
-   In the **Search** box, enter **Send Overdue Approval Notifications**, and then choose the related link.  
  
     The **Send Overdue Approval Notifications** function is executed.  
  
## See Also  
 Overdue Notification Entries   
 Notification Templates   
 [How to: View Overdue Approval Requests](../../BusinessFunctionality/Workflow/how-to-view-overdue-approval-requests.md)   
 [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md)   
 [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)   
 [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md)   
 [How to: View Overdue Approval Requests](../../BusinessFunctionality/Workflow/how-to-view-overdue-approval-requests.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)