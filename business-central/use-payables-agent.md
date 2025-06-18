---
title: Use Payables Agent
description: Learn how to use Payables Agent.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.collection:
  - bap-ai-copilot
ms.date: 06/17/2025
ms.custom: bap-template
ms.search.form: 4400, 4410
---
# Use Payables Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to use Payables Agent to help you process vendor invoices received via email. The Payables Agent uses  AI to analyze incoming invoices, create drafts for review, and reduce manual corrections.

The agent monitors a designated mailbox for incoming email from vendors or employees with attached PDF invoices. Some steps require your intervention.

Learn more about the Payables Agent and its process flow in [Payables Agent process flow](payables-agent.md#payables-agent-process-flow).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->

## Supported languages

[!INCLUDE[soa-language-support](includes/soa-language-support.md)]

## Prerequisites

Payables Agent is activated, and you have permission to use it. Learn more in [Set up Payables Agent](payables-agent-setup.md).

## Get started

You collaborate with Payables Agent to process invoices using the **Tasks** tab in the **Copilot** pane.

To access this view, select ![Shows Payables Agent icon.](media/payables-agent-activated-icon.png) **Payable Agent** on the upper right of the navigation menu. A red circle with a number on the icon indicates the tasks that need attention.

![Shows the task view with steps](media/soa-task-view-callouts.png "Shows the task view with steps")

The ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** tab opens in the **Copilot** pane to display tasks recently created by the agent. Tasks that require attention&mdash;like reviewing an incoming or outgoing email&mdash;are at the top of the list.  

For each invoice request, the agent adds a task to track, review, and follow up on updates, eventually processing the request into a purchase invoice. Tasks can consist of multiple steps that form a timeline of the process.

> [!TIP]
> Hover over the ![Shows Payables Agent icon.](media/payables-agent-activated-icon.png) **Payable Agent** icon in the role or select the ![Show summary for Agent icon](media/soa-summary-icon.png) **Show summary for Payables Agent** in the **Task** tab to get an overview of the agent's key performance indicators (KPIs) summarizing the impact of the agent's work in your organization. For example, view the number of sales quotes or orders created by the agent, the time saved by your team, and the total number of sales orders created.

## Review and assist

While the agent does the bulk of work autonomously, it asks for user intervention when required for various steps to move through the process, such as:

- Review and confirm the vendor.
- Review and confirm the generated invoice document.
- Providing assistance to the agent when it needs to get unblocked—for example, to provide missing data.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** tab. To review a step:

1. In the **Task** tab, select the step requesting review or assistance.

   The task *timeline* opens, focused on the selected step. The timeline displays each step of a task, past and present, in chronological order.

1. Select **Review** for the step.

   The **Tasks** tab switches to **Review** mode, and the Agent Task Message window opens to display the email contents or quote or order, depending on the task.

1. Review the contents and make changes as needed.

1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane. If you want to complete the task yourself, select **Stop** to halt the agent's processing of this task.

After confirmation, the agent continues processing the task. When a new notification appears on the Payables Agent icon after some time, follow the same flow to review  and confirm the results.

## Modify invoices

You might need to modify an invoice created by the agent during a review step or when the agent requests assistance, based on its configuration. When you select **Review**, the invoice opens for inspection. Make changes as needed, then select **Confirm** in the **Review** pane. The agent processes the document, creating a PDF for the outgoing email to the customer.

You also have the opportunity to modify a quote or order during the review step for an outgoing email. In this case, select **...** (More options) > **Discard step** on the step. This action stops the task temporarily to allow you to open the quote or order and makes changes and then resume the step.

![Shows the discard step action on a Sales Order Agent task.](media/soa-discard-step.png "Shows the discard step action on a Sales Order Agent task.")

> [!NOTE]
> **Discard step** is available only on review steps for outgoing emails.

After you make the changes, return to the **Tasks** tab, select one of the following options for resuming the task, and then select **Send**:

- **I have updated the quote** or **I have updated the order**: Select one of these options if you made changes to the quote or order. The agent generates a new PDF and email for the customer.
- **Just resume**: Select this option if you didn't change the quote or order. The agent doesn't generate a new quote or order and keeps the original email as before.  

![Shows the resume step action on a Sales Order Agent task.](media/soa-resume-step.png "Shows the resume step action on a Sales Order Agent task.")

If you change your mind while reviewing the outgoing message and decide to make more changes to the sales document, use the **Discard step** action to discard the email message generated by the agent. Then, update the sales document as needed and instruct the agent to create a new outgoing email with the updated attachment.

## Stop a task

Most steps of a task include a **Stop** button that lets you terminate the process. When you select **Stop**, a task isn't terminated immediately—you're asked to confirm before the task is stopped.

Before you stop a task, consider the following behavior:

- Stopped tasks can't be restarted.
- Stopping the task might leave some results incomplete or unwanted, and it might require follow-up actions with the customers. Follow up actions depend on where in the process the task was stopped.

  For example, suppose you stopped a task after a sales quote was created. Although the process stopped, the sales quote is still stored in the system as open. You might have to manually edit the state depending on your company policy and then update the customer.
- Stopped tasks aren't deleted immediately. You can still explore a task's timeline until it's deleted, typically by an administrator.


## Related information

[Sales Order Agent overview](sales-order-agent.md)  
[Set up Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
