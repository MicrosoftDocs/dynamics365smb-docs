---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Setting Up Workflow Notifications
Many workflow responses are about notifying a user that an event has occurred that they must act on. For example, on one workflow step, the event can be that User 1 requests approval of a new record, and the response is that a notification is sent to User 2, the approver. On the next workflow step, the event can be that User 2 approves the record, and the response is that a notification is sent to User 3 to start a related processing of the approved record. For workflow steps that are about approval, each notification is tied to an approval entry. For more information, see [Workflow](../FullExperience/workflow.md).  
  
> [!NOTE]  
>  The generic version of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/dyn_nav_md.md)]--> supports notifications as email and as internal notes.  
  
> [!IMPORTANT]  
>  All workflow notifications are sent through a job queue. Make sure that the job queue in your installation of ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-set-up-job-queues.md).  
  
 You set up different aspects of workflow notifications in the following places:  
  
1.  For approval workflows, you set up the recipients of workflow notifications by filling a line in the **Approval User Setup** window for each user that takes part in the workflow. For example, if User 2 is specified in the **Approver ID** field on the line for User 1, then the approval request notification is sent to User 1. For more information, see [How to: Set Up Approval Users](../FullExperience/how-to-set-up-approval-users.md).  
  
2.  You set when and how users receive workflow notifications by filling the **Notification Schedule** window for each workflow user. For more information, see [How to: Specify When and How to Receive Notifications](../FullExperience/how-to-specify-when-and-how-to-receive-notifications.md).  
  
3.  You set up the general content and layout of notifications, including notifications about overdue workflow responses, by setting up notification templates in the **Notification Templates** window. You can use the default templates provided with ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/how-to-manage-notification-templates.md).  
  
4.  You set up specific content and rules of a workflow notification when you create the workflow in question. You do this by selecting options in the **Workflow Response Options** window for the workflow response that represents the notification. For more information, see step 9 in [How to: Create Workflows](../FullExperience/how-to-create-workflows.md).  
  
 To send emails from ADD INCLUDE<!--[!INCLUDE[dyn_nav](../../includes/how-to-set-up-smtp-email.md).  
  
## See Also  
 [How to: Set Up Approval Users](../FullExperience/how-to-set-up-approval-users.md)   
 [How to: Set Up Workflow Users](../FullExperience/how-to-set-up-workflow-users.md)   
 [How to: Specify When and How to Receive Notifications](../FullExperience/how-to-specify-when-and-how-to-receive-notifications.md)   
 [How to: Create Workflows](../FullExperience/how-to-create-workflows.md)   
 [How to: Manage Notification Templates](../FullExperience/how-to-manage-notification-templates.md)   
 [How to: Set Up Job Queues](../FullExperience/how-to-set-up-job-queues.md)   
 [How to: Set Up SMTP Email](../FullExperience/how-to-set-up-smtp-email.md)   
 [Walkthrough: Setting Up and Using a Purchase Approval Workflow](../FullExperience/walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)   
 [Workflow](../FullExperience/workflow.md)   
 [Business Functionality](../FullExperience/Business%20Functionality.md)