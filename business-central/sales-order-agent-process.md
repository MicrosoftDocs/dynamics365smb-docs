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

This article explains how to use the Sales Order Agent to automate taking sales orders based on customer inquiries about products/items received via email.

[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]

## How it works

The agent monitors a designated mailbox for incoming customer emails about item inquiries. When it identifies a potential request, it starts preparing a sales quote. For example, it verifies that the customer, requesting the items, is registered in Business Central, it checks item availability, creates a sales quote, and prepares an email response to the customer that includes the quote as a PDF attachment.

The agent ensures that a request from one customer cannot be about another customer's requests. When a request is being processed by the agent, it first identifies the customer in Business Central by their email address. If the customer is not found, the agent stops task processing and requests intervention from the user. If the customer is found, the agent filters out all sales quotes and orders that do not belong to this customer, ensuring it only creates and updates documents belonging to the owner of the email.

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

For each sales quote request, the Sales Order Agent adds a task to track, review, follow up on updates and eventually process the quote into an order. Tasks can consist of multiple steps that form a timeline of the process.

## Review and assist

While the agent does the bulk of work autonomously, it asks for user intervention when required for various steps to move through the process, such as:

- Reviewing and confirming incoming email requests from customers.
- Reviewing and confirming the sales quotes and orders (if an admin configured the Sales Order Agent to do so).
- Reviewing outgoing emails created by the Sales Order Agent for the customer.
- Providing assistance to the Sales Order Agent when it needs to get unblocked, for example to provide missing data.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** view. To review a step:

1. In **Task** view, select the step requesting review or assistance.

   The task timeline opens, focused on the selected step, which includes a brief description.

1. Select **Review**.

   The **Tasks** view switches to the **Review** pane, and the Agent Task Message window opens to display the email contents or quote or order, depending on the task.

1. Review the email contents or the quote or order and make changes as needed. You can't edit incoming emails from the customer.

1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane. If you want to complete the task yourself, select **Stop** and the agent will no longer be processing this task. 

After confirmation, the Sales Order Agent moves the task on for more processing. After some time, a new notification appears on the Sales Order Agent badge. Follow the same flow to verify and approve the results.

## Modify sales quotes and orders

You might need to modify sales quotes or orders created by the agent during a review step or when the agent requests assistance, based on its configuration.

When you select **Review**, the quote or order opens for you to inspect. Make changes as needed, then select **Confirm** in the **Review** pane. The agent then processes the document, creating a PDF for inclusion in the outgoing email to the customer.

If, while reviewing the outgoing message, you change your mind and decide to make more changes to the sales document, you can use the **Discard step** action to discard the email message generated by the agent. Then, update the sales document as needed and instruct the agent to proceed with creating a new outgoing email with the updated attachment.

## Stop a task

Most steps of a task include a **Stop** button that lets you terminate the process. When you select **Stop**, a task isn't terminated immediately—you're asked to confirm before the task is stopped.

Before you stop a task, consider the following behavior:

- Stopped tasks can't be restarted.
- Stopping the task might leave some results incomplete or unwanted, and it might require follow-up actions with the customers. Follow up actions depend on where in the process the task was stopped.

  For example, suppose you stopped a task after a sales quote was created. Although the process stopped, the sales quote is still stored in the system as open. You might have to manually edit the state depending on your company policy and then update the customer.
- Stopped tasks aren't deleted immediately. You can still explore a task's timeline until it's deleted, typically by an administrator.

## View timeline and details of steps

From the ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view, you can view the details of each step of a task in chronological order. Click on the task or select **...** (More options) > **Show Details**.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
