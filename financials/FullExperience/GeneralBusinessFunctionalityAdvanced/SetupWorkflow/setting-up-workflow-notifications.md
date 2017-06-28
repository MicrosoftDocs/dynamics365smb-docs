---
title: "Setting Up Workflow Notifications"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: 53d4a107-1fae-41cf-95cd-bc34c9a1fc08
caps.latest.revision: 8
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
# Setting Up Workflow Notifications
Many workflow responses are about notifying a user that an event has occurred that they must act on. For example, on one workflow step, the event can be that User 1 requests approval of a new record, and the response is that a notification is sent to User 2, the approver. On the next workflow step, the event can be that User 2 approves the record, and the response is that a notification is sent to User 3 to start a related processing of the approved record. For workflow steps that are about approval, each notification is tied to an approval entry. For more information, see [Workflow](../../BusinessFunctionality/Workflow/workflow.md).  
  
> [!NOTE]  
>  The generic version of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] supports notifications as email and as internal notes.  
  
> [!IMPORTANT]  
>  All workflow notifications are sent through a job queue. Make sure that the job queue in your installation of [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] is set up to handle workflow notifications, and that the **\($ T\_470\_8 Start Automatically From NAS $\)** check box is selected. For more information, see [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md).  
  
 You set up different aspects of workflow notifications in the following places:  
  
1.  For approval workflows, you set up the recipients of workflow notifications by filling a line in the **\($ N\_663 Approval User Setup $\)** window for each user that takes part in the workflow. For example, if User 2 is specified in the **\($ T\_91\_11 Approver ID $\)** field on the line for User 1, then the approval request notification is sent to User 1. For more information, see [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md).  
  
2.  You set when and how users receive workflow notifications by filling the **\($ N\_1513 Notification Schedule $\)** window for each workflow user. For more information, see [How to: Specify When and How to Receive Notifications](../../BusinessFunctionality/Workflow/how-to-specify-when-and-how-to-receive-notifications.md).  
  
3.  You set up the general content and layout of notifications, including notifications about overdue workflow responses, by setting up notification templates in the **\($ N\_1510 Notification Templates $\)** window. You can use the default templates provided with [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], or you can export, modify, and then reimport them. For more information, see [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md).  
  
4.  You set up specific content and rules of a workflow notification when you create the workflow in question. You do this by selecting options in the **\($ N\_1523 Workflow Response Options $\)** window for the workflow response that represents the notification. For more information, see step 9 in [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md).  
  
 To send emails from [!INCLUDE[dyn_nav](../../ApplicationDesign/includes/dyn_nav_md.md)] using an SMTP server, you must fill the **\($ N\_409 SMTP Mail Setup $\)** window. For more information, see [How to: Set Up SMTP Email](../../BusinessFunctionality/Workflow/how-to-set-up-smtp-email.md).  
  
## See Also  
 [How to: Set Up Approval Users](../../BusinessFunctionality/Workflow/how-to-set-up-approval-users.md)   
 [How to: Set Up Workflow Users](../../BusinessFunctionality/Workflow/how-to-set-up-workflow-users.md)   
 [How to: Specify When and How to Receive Notifications](../../BusinessFunctionality/Workflow/how-to-specify-when-and-how-to-receive-notifications.md)   
 [How to: Create Workflows](../../BusinessFunctionality/Workflow/how-to-create-workflows.md)   
 [How to: Manage Notification Templates](../../BusinessFunctionality/Workflow/how-to-manage-notification-templates.md)   
 [How to: Set Up Job Queues](../../SetupAndAdministration/how-to-set-up-job-queues.md)   
 [How to: Set Up SMTP Email](../../BusinessFunctionality/Workflow/how-to-set-up-smtp-email.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../../BusinessFunctionality/Workflow/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Workflow](../../BusinessFunctionality/Workflow/workflow.md)   
 [Business Functionality](../Topic/Business%20Functionality.md)