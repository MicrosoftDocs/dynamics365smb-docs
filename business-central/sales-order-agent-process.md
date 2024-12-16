---
title: Process sales quotes and orders with Sales Order Agent (preview)
description: Learn how to work with the Sales Order Agent to process sales quotes and orders from customer requests made via email.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.collection:
  - bap-ai-copilot
ms.date: 12/16/2024
ms.custom: bap-template
---
# Process sales quotes and orders with Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to use the Sales Order Agent to automate taking sales orders based on customer inquiries about products/items received via email.

[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]

## How it works

The agent monitors a designated mailbox for incoming customer emails about item inquiries. When it identifies a potential request, it starts to prepare a sales quote. For example, it verifies whether the customer is registered in Business Central. It then checks item availability, creates a sales quote, and prepares an email response to the customer that includes the quote as a PDF attachment.

The agent ensures that a request from one customer can't be about another customer's requests. When the agent processes a request, it first identifies the customer in Business Central using the sender's email address (the agent searches among the registered Business Central contacts and then looks up the customer linked to that contact). If the customer isn't found, the agent stops processing the task and requests intervention from the user. If the customer is found, the agent filters out all sales quotes and orders that don't belong to the customer. This behavior ensures that the agent only creates and updates documents belonging to the customer that sent the email.

The agent analyzes incoming emails to detect parameters for preparing a new sales quote or updating an existing one. Apart from the items tehmselves, parameters might include the item attributes, quantities, units of measure, requested delivery date, external document number, and more. The agent then searches for these items in the Business Central's inventory, within a wide range of related tables.

|Table|Fields|
|-|-|
|Items|No.<br>Description<br>Description 2<br>Search Description<br>GTIN<br>Vendor Item Number|
|Item Variant|Code<br>Description<br>Description 2|
|Item Reference|Reference No.<br>Description<br>Description 2|
|Item Attributes|Name<br>Value|
|Item Category| Code<br>Description<br>Parent Category - 1 Level|
|Item Translation|Language<br>Description<br>Description 2|
|Item Identifier|Code|
|Extended text Line|Text|

Although the agent can find products based on vague and incomplete descriptions, its effectiveness is influenced by the quality of product information in Business Central. You can improve the agent's ability to find products by enhancing descriptions, attributes, categories, and extended text of your inventory items.

When it finds the items, the agent checks the items' availability by analyzing multiple parameters, such as required quantity, delivery date, location, scheduled and planned receipts and more. 

Some steps require your intervention, like reviewing email correspondence and assisting the agent as needed. Until an order is created, the agent handles back-and-forth email exchanges with the customer to resolve missing details and allow modifications to the original request.

Learn more about Sales Order Agent process in [Sales Order Agent overview](sales-order-agent.md#process-flow).


<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

## Prerequisites

The Sales Order Agent is activated, and you have permission to use it. Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md).

## Get started

You collaborate with the Sales Order Agent to review and convert quotes into orders using the **Tasks** tab in the **Copilot** pane.

To access this view, select ![Shows Sales Order Agent icon with an open action.](media/soa-activated-number-icon.png) **Sales Order Agent** on the upper right side of the navigation menu. A red circle with a number on the badge indicates the tasks that need attention.

![Shows the task view with steps](media/soa-task-view-callouts.png)

The ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** tab opens in the **Copilot** pane to display tasks recently created by the Sales Order Agent. Tasks that require attention&mdash;like reviewing an incoming or outgoing email&mdash;are at the top of the list.  

For each sales quote request, the Sales Order Agent adds a task to track, review, and follow up on updates and eventually process the quote into an order. Tasks can consist of multiple steps that form a timeline of the process.

## Review and assist

While the agent does the bulk of work autonomously, it asks for user intervention when required for various steps to move through the process, such as:

- Reviewing and confirming incoming email requests from customers.
- Reviewing and confirming the sales quotes and orders if an admin configured the Sales Order Agent to do so.
- Reviewing outgoing emails created by the Sales Order Agent for the customer.
- Providing assistance to the Sales Order Agent when it needs to get unblocked, for example to provide missing data.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** tab. To review a step:

1. In **Task** tab, select the step requesting review or assistance.

   The task *timeline* opens, focused on the selected step. The timeline displays each step of a task, past and present, in chronological order.

1. Select **Review** for the step.

   The **Tasks** tab switches to **Review** mode, and the Agent Task Message window opens to display the email contents or quote or order, depending on the task.

1. Review the email contents or the quote or order and make changes as needed. You can't edit incoming emails from the customer.

1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane. If you want to complete the task yourself, select **Stop** and the agent no longer processes this task.

After confirmation, the Sales Order Agent moves the task on for more processing. After some time, a new notification appears on the Sales Order Agent badge. Follow the same flow to verify and approve the results.

## Modify sales quotes and orders

You might need to modify sales quotes or orders created by the agent during a review step or when the agent requests assistance, based on its configuration. When you select **Review**, the quote or order opens for you to inspect. Make changes as needed, then select **Confirm** in the **Review** pane. The agent then processes the document, creating a PDF for inclusion in the outgoing email to the customer.

You also have the opportunity to modify a quote or order during the review step for an outgoing email. In this case, select **...** (More options) > **Discard step** on the step. This action stops the task temporarily to allow you to open the quote or order and makes changes and then resume the step.

![Shows the discard step acion on a sales order agent task.](media/soa-discard-step.png)

> [!NOTE]
> **Discard step** is available only on review steps for outgoing emails.

After you make the changes, return the **Tasks** tab, select one of the options for resuming the task, and the select **Send**:

- **I have updated the quote** or **I have updated the order** - Select one of these options if you made changes to the quote or order. The agent generates a new PDF and email for the customer.
- **Just resume** - Select this option if you didn't change the quote or order. The agent doesn't generate a new quote or order, and keeps the original email as before.  

![Shows the resume step acion on a sales order agent task.](media/soa-resume-step.png)

If, while reviewing the outgoing message, you change your mind and decide to make more changes to the sales document, you can use the **Discard step** action to discard the email message generated by the agent. Then, update the sales document as needed and instruct the agent to proceed with creating a new outgoing email with the updated attachment.

## Stop a task

Most steps of a task include a **Stop** button that lets you terminate the process. When you select **Stop**, a task isn't terminated immediately—you're asked to confirm before the task is stopped.

Before you stop a task, consider the following behavior:

- Stopped tasks can't be restarted.
- Stopping the task might leave some results incomplete or unwanted, and it might require follow-up actions with the customers. Follow up actions depend on where in the process the task was stopped.

  For example, suppose you stopped a task after a sales quote was created. Although the process stopped, the sales quote is still stored in the system as open. You might have to manually edit the state depending on your company policy and then update the customer.
- Stopped tasks aren't deleted immediately. You can still explore a task's timeline until it's deleted, typically by an administrator.

<!--
## Discard and resume a taks to modify a quote or order

The **Discard**  action ellwo

## View timeline and details of steps

From the ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view, you can view the details of each step of a task in chronological order. Click on the task or select **...** (More options) > **Show Details**.-->

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
