---
    title: Setting up Workflow Notifications
    description: This article tells you how to set up workflow notifications to alert a user that an event has occurred that they must react to; a workflow response is required. 
    author: SorenGP

    
    ms.topic: conceptual
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/11/2021
    ms.author: edupont

---
# Workflow Notifications

Set up your workflows to automatically notify users when their attention is required for a step in that workflow. Many workflow responses are about notifying a user that an event has occurred that they must act on.

For example, you can set that User 2, the approver user, receives a notification whenever User 1 requests approval for a new record. On the next workflow step, User 3 is notified after User 2 approves the record in order to start a related processing of the record. With approval workflow steps, each notification is tied to an approval entry. For more information, see [Workflow](across-workflow.md).  

> [!NOTE]  
> The default version of [!INCLUDE[prod_short](includes/prod_short.md)] supports notifications as email and as internal notes.  

> [!IMPORTANT]  
> All workflow notifications are sent through a job queue. Make sure that the job queue in your installation is set up to handle workflow notifications, and that the **Start Automatically From Server** check box is selected. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Set up notifications

You can set up different aspects of workflow notifications in the following places:  

* Approver notification

    For approval workflows, you set up the recipients of workflow notifications by filling a line on the **Approval User Setup** page for each user that takes part in the workflow.  

    For example, if User 2 is specified in the **Approver ID** field on the line for User 1, then the approval request notification is sent to User 2. For more information, see [Set Up Approval Users](across-how-to-set-up-approval-users.md).  
* Notification schedules

    You set up when and how users receive workflow notifications by filling the **Notification Schedule** page for each workflow user. For more information, see [Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md).  
* Customize the email notifications

    If you want, you can customize the content of the email notification by modifying Report 1320, Notification Email. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).  

    > [!NOTE]
    > If you want to use email as the notification method, you must set up email for both the sender and the receiver in [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Set up Email](admin-how-setup-email.md).

* Response options

    You set up specific content and rules of a workflow notification when you create the workflow in question. Select the customization options on the **Workflow Responses** page for the workflow response that represents the notification. For more information, see step 9 in [Create Workflows](across-how-to-create-workflows.md#to-create-a-workflow).  

* Notify sender

    For approval workflows, add a workflow response step to notify the sender when the request has been approved or rejected. For more information, see step 9 in [Create Workflows](across-how-to-create-workflows.md#to-create-a-workflow).  

## See related training at [Microsoft Learn](/learn/modules/create-workflows/)

## See also

[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Set Up Workflow Users](across-how-to-set-up-workflow-users.md)  
[Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md)  
[Create Workflows](across-how-to-create-workflows.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Set up Email](admin-how-setup-email.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Workflow](across-workflow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]