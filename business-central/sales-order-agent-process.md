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
ms.custom: bap-template #Required; don't change.
---
# Process sales quotes and orders with Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After the Sales Order Agent is activated, it monitors the designated mailbox for incoming emails about item inquiries from customers. When it identifies a potential request, it starts the process for converting the request to an order. Some steps in the process require your intervention. Learn more about the steps in the process in [Understand the process flow](sales-order-agent.md#process-flow).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Prerequisites

The Sales Order Agent is activated, and you have permission to use it. Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md).

## Get started

You collaborate with the Sales Order Agent to review and convert quotes into orders using the **Tasks** view in the **Copilot** pane.

To access this view, select ![Shows Sales Order Agent icon with an open action.](media/soa-activated-number-icon.png) **Sales Order Agent** on the right side of the navigation menu at the top. A red circle with a number on the badge indicates the number of tasks needing attention.  

![Shows the task view with steps](media/soa-task-view-callouts.png)

The ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view opens in the **Copilot** pane to display tasks recently created by the Sales Order Agent. Tasks that require attention&mdash;like reviewing an incoming or outgoing email&mdash;are at the top of the list.  

For each sales quote request, the Sales Order Agent adds a task for tracking, reviewing, and processing the quote into an order. A task can consist of multiple steps that make up a timeline of the entire process.

## Review a step

Your intervention is required for various steps in creating a sales order, such as:

- Review and confirm incoming email requests for sales quotes from customers.
- Review and confirm the sales quotes and order, along with outgoing emails created by the Sales Order Agent for the customer.
- Provide assistance to the Sales Order Agent for fixing a problem.

The review steps depend, in part, on how the Sales Order Agent is configured.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** view. To review a step:

1. On the step, select **...** (More options) > **Review**.

   The **Tasks** view switches to the **Review** pane, and the Agent Task Message window opens to display the contents of the incoming or outgoing email.
1. Review the contents of the email.
1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane. If you want to cancel the process and discard the task, select **Stop**.

After confirmation, the Sales Order Agent moves the task on for more processing. After some time, a new notification appears on the Sales Order Agent badge. Follow the same flow to verify and approve the results.

## Discard and revive messages

## Modify documents

## Stop and resume task

## View timeline and details of steps

From the ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view, you can view the details of each step of a task in chronological order. Click on the task or select **...** (More options) > **Show Details**.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)
[Configure Copilot and AI capabilities](enable-ai.md)  