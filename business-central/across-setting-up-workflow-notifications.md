---
title: Setting up approval workflow notifications
description: This article tells you how to set up workflow notifications to alert a user that an event has occurred that they must react to; a workflow response is required. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords:
ms.date: 05/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Approval workflow notifications

Set up your workflows to automatically notify users when their attention is required for a step in a workflow. Many workflow responses involve notifying a user an event they must act on has occurred.

For example, you can set it so User 2, the approver user, receives a notification whenever User 1 requests approval for a new record. On the next workflow step, after User 2 approves the record, User 3 is notified and can begin a related processing of the record. With approval workflow steps, each notification is tied to an approval entry. Learn more at [Workflow](across-workflow.md).  

> [!NOTE]  
> The default version of [!INCLUDE[prod_short](includes/prod_short.md)] supports notifications in email or as internal notes.  

> [!IMPORTANT]  
> All workflow notifications are sent through a job queue. Make sure the job queue in your installation is set up to handle workflow notifications, and that you've selected the **Start Automatically From Server** check box. Learn more at [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Set up notifications

You can set up different aspects of workflow notifications in the following places:  

* Approver notification

  For approval workflows, set up the recipients of workflow notifications by filling in a line on the **Approval User Setup** page for each user that takes part in the workflow.  

  For example, if User 2 is specified in the **Approver ID** field on the line for User 1, then the approval request notification is sent to User 2. Learn more at [Set Up Approval Users](across-how-to-set-up-approval-users.md). 
  
* Notification schedules

  Set up when and how users receive workflow notifications by filling in the **Notification Schedule** page for each workflow user. Learn more at [Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md). 
  
* Customize the email notifications

  If you like, you can customize the content of the email notification by modifying Report 1320, Notification Email. Learn more at [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).  

  > [!NOTE]
  > If you want to use email as the notification method, you must set up email for both the sender and the receiver in [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more at [Set up Email](admin-how-setup-email.md).
  
* Response options

  Set up specific content for and rules of a workflow notification when you create the workflow in question. Select the customization options on the **Workflow Responses** page for the workflow response that represents the notification. Learn more from step 9 in the [Create Workflows](across-how-to-create-workflows.md#to-create-a-workflow) section. 
  
* Notify sender

  For approval workflows, add a workflow response step to notify the sender when the request has been approved or rejected. Learn more from step 9 in the [Create Workflows](across-how-to-create-workflows.md#to-create-a-workflow) section.   

## Related information

[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Set Up Workflow Users](across-how-to-set-up-workflow-users.md)  
[Specify When and How to Receive Notifications](across-how-to-specify-when-and-how-to-receive-notifications.md)  
[Create Approval Workflows](across-how-to-create-workflows.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Set up Email](admin-how-setup-email.md)  
[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
