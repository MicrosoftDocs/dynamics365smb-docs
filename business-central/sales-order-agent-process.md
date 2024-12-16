---
title: Process sales quotes and orders with Sales Order Agent (preview)
description: Learn how to work with the Sales Order Agent to process sales quotes and orders.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.collection:
  - bap-ai-copilot
ms.date: 11/13/2024
ms.custom: bap-template
---
# Process sales quotes and orders with Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to use the Sales Order Agent to process sales orders from customer requests. The Sales Order Agent is a Copilot feature that automates taking sales orders based on customer inquiries about products/items received via email.

[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]

## How it works

The agent monitors a designated mailbox for incoming customer emails about item inquiries. When it identifies a potential request, it starts converting the request into an order. For example, it verifies the customer, checks item availability, creates a sales quote, and prepares an email response to the customer that includes the quote as a PDF attachment.

Some steps require your intervention, such as reviewing email correspondence and providing assistance to the agent as needed. Until an order is created, the agent handles back-and-forth email exchanges with the customer to resolve any missing details and allow for modifications to the original request, if necessary.

Learn more about Sales Order Agent process in [Sales Order Agent overview](sales-order-agent.md#process-flow).


<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

## Prerequisites

The Sales Order Agent is activated, and you have permission to use it. Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md).

## Get started

You collaborate with the Sales Order Agent to review and convert quotes into orders using the **Tasks** view in the **Copilot** pane.

To access this view, select ![Shows Sales Order Agent icon with an open action.](media/soa-activated-number-icon.png) **Sales Order Agent** on the upper right side of the navigation menu. A red circle with a number on the badge indicates the tasks that need attention.

![Shows the task view with steps](media/soa-task-view-callouts.png)

The ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view opens in the **Copilot** pane to display tasks recently created by the Sales Order Agent. Tasks that require attention&mdash;like reviewing an incoming or outgoing email&mdash;are at the top of the list.  

For each sales quote request, the Sales Order Agent adds a task to track, review, and process the quote into an order. Tasks can consist of multiple steps that form a timeline of the process.

## Review and assist

Your intervention is required for various steps in creating a sales order to move it through the process, such as:

- Reviewing and confirming incoming email requests for sales quotes or orders from customers.
- Reviewing and confirming the sales quotes and orders created by the agent.
- Reviewing and confirming with outgoing emails created by the agent to the customer.
- Providing assistance to the agent for fixing a problem or provising clarication.

> [!NOTE]
> You might not need to review sales quotes and orders depending on how an admin configures the Sales Order Agent.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** view. To review a step:

1. In **Task** view, select the step requesting review or assistance.

   The task *timeline* opens, focused on the selected step. The timelines displays each step of a task, past and present, in chronological order.

1. Select **Review**.

   The **Tasks** view switches to the **Review**, and the Agent Task Message window opens to display the email contents or quote or order, depending on the task.

1. Review the email contents or the quote or order and make changes as needed. You can't edit incoming emails from the customer.

1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane. If you want to cancel the process and discard the task, select **Stop**.

After confirmation, the Sales Order Agent moves the task on for more processing. After some time, a new notification appears on the Sales Order Agent badge. Follow the same flow to verify and approve the results.

## Modify sales quotes and orders

You might need to modify sales quotes or orders created by the agent during a review step or a request for assistance. When you select **Review**, the quote or order opens for you to inspect. Make changes as needed, then select **Confirm** in the **Review** pane. The agent then processes the document, creating a PDF for inclusion in the outgoing email to the customer.

You also have the opportunity to modify a quote or a order during the step for reviewing an outgoing email to the customer. In this case, select the **Discard** action on the step. This action pause the task to allow you to open the quote or order and makes changes.

After you make the changes, return the task view, select one of the options for resuming the task, and the select **Send**:

- **I have updated the quote** or **I have updated the order** - Select one of these options if you have mad changes to the quote or order, and you want the agent to generate a new PDF and email for the customer.
- **Just resume** - Select this option if you haven't changed the quote or order. With this option, the agent doesn't generate a new quote or order, and keeps the original email as before.  

## Stop a task

Most steps of a task include a **Stop** button that lets you terminate the process. When you select **Stop**, a task isn't terminated immediately—you're asked to confirm before the task is stopped.

Before you stop a task, consider the following behavior:

- Stopped tasks can't be restarted.
- Stopping the task might leave some results incomplete or unwanted, and it might require follow-up actions. Follow up actions depend on where in the process the task was stopped.

  For example, suppose you stopped a task after a sales quote was created. Although the process stopped, the sales quote is still stored in the system as open. You might have to manually edit the state depending on your company policy.
- Stopped tasks aren't deleted immediately. You can still explore a task's timeline until it's deleted, typically by an administrator.

## Discard and resume a taks to modify a quote or order

The **Discard**  action ellwo

## View timeline and details of steps

From the ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view, you can view the details of each step of a task in chronological order. Click on the task or select **...** (More options) > **Show Details**.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  