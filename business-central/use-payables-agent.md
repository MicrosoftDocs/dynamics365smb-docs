---
title: Process Vendor Invoices with Payables Agent
description: Payables Agent automates vendor invoice processing, tracks tasks, and keeps you informed. Discover how to simplify your accounts payable process.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.collection:
  - bap-ai-copilot
ms.date: 06/18/2025
ms.update-cycle: 180-days
ms.custom:
  - bap-template
  - ai-gen-docs-bap
  - ai-gen-description
  - ai-seo-date:06/18/2025
ms.search.form: 4400, 4410
ROBOTS: NOINDEX,NOFOLLOW
---
# Supervise agent activities (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

You interact with Business Central agents, such as sales order and payables agents, directly in Copilot's **Tasks** tab. You can monitor task status, review agent-generated drafts and suggestions, and provide confirmations or input to help tasks complete responsibly and accurately.

The process flow is different for each agent. This article explains the common aspects of working in the **Tasks** tab for all agents and answers frequently asked questions.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->

## Prerequisites

The agent is activated, and you have permission to use it. Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md) and [Set up Payables Agent](payables-agent-setup.md).

## Get started

On the upper right of the navigation menu, select the icon for the agent:

- ![Shows Payables Agent icon.](media/payables-agent-activated-icon.png) **Payable Agent**
- ![Shows Sales Order Agent icon.](media/soa-activated-number-icon.png) **Sales Order Agent**

A red circle with a number on the icon indicates the number of tasks that need attention.

![Shows the agents task view with steps](media/payables-agent-tasks-pane.svg)

Selecting the ![Shows the task view icon](media/sot-task-view-icon.png) icon opens the **Tasks** tab in the **Copilot** pane, where you can view tasks recently created by the agent. Tasks that require attention&mdash;like reviewing vendor information&mdash;are at the top of the list.  

For each inquiry the agent receives, like request for a quote or invoice, the agent adds a **task** to track, review, and follow up on until the agent creates the purchase invoice. Each task has multiple steps that create a timeline of the process. A timeline is a visual sequence that shows each step taken for the task, helping you understand the progress and history.

## View summary of agent activities

Hover over the agent's icon or select the ![Show summary for Agent icon](media/soa-summary-icon.png) **Show summary for agent** in the **Task** tab to get an overview of the agent's key performance indicators (KPIs) that measure the impact of the agent's work in your organization.

## Review and assist

The agent does most of the work autonomously, but sometimes it asks for user intervention to complete the process. When intervention is needed depends on the agent and  its setup, but here are some common situations:

- Reviewing and confirming incoming and outgoing emails
- Review and confirm contact or vendor information.
- Review and confirm the draft documents, like quotes, orders and purchase invoices.
- Help the agent get unblocked, like by providing missing data, creating a new contact for an order, or finding items.

Learn more about the Payables Agent and its process flow in [Payables Agent process flow](payables-agent.md#payables-agent-process-flow) and [PaSales Order Agent process flow](sales-order-agent.md#how-the-agent-processes-requests).

### Review a step

Steps that need intervention appear under **Needs Attention** in the **Tasks** tab. To review a step, follow these instructions:

1. In the **Task** tab, select the step requesting review or assistance.

   The task *timeline* opens, focused on the selected step. The timeline displays each step of a task, past and present, in chronological order.

1. Select **Review** for the step.

   The **Tasks** tab switches to **Review** mode, and the review content appears in the main display area.
1. Review the contents and make changes as needed.

1. If the agent need assistance, a message appears at the top of the text explaining the problem.

   You can often help the agent by making the changes yourself, like making an item available, creating the right customer, contact, or vendor, changing quantities in sales quotes, so on.

1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane.

   If you want to complete the task yourself, select **Stop** to halt the agent's processing of this task. Learn more in [Stop a task](#stop-a-task).

After confirmation, the agent continues with the task. When a new notification appears on the Payables Agent icon after some time, follow the same flow to review and confirm the results.

<!--
## Modify invoices

During review, you might need to modify the vendor details or purchase document draft created by the agent, or when the agent requests assistance. When you select **Review**, the invoice opens for inspection. Make changes as needed, then select **Confirm** in the **Review** pane. The agent processes the purchas invoice document.

You also have the opportunity to modify a quote or order during the review step for an outgoing email. In this case, select **...** (More options) > **Discard step** on the step. This action stops the task temporarily to allow you to open the quote or order and makes changes and then resume the step.

![Shows the discard step action on a Sales Order Agent task.](media/soa-discard-step.png "Shows the discard step action on a Sales Order Agent task.")

> [!NOTE]
> **Discard step** is available only on review steps for outgoing emails.

After you make the changes, return to the **Tasks** tab, select one of the following options for resuming the task, and then select **Send**:

- **I have updated the quote** or **I have updated the order**: Select one of these options if you made changes to the quote or order. The agent generates a new PDF and email for the customer.
- **Just resume**: Select this option if you didn't change the quote or order. The agent doesn't generate a new quote or order and keeps the original email as before.  

![Shows the resume step action on a Sales Order Agent task.](media/soa-resume-step.png "Shows the resume step action on a Sales Order Agent task.")

If you change your mind while reviewing the outgoing message and decide to make more changes to the sales document, use the **Discard step** action to discard the email message generated by the agent. Then, update the sales document as needed and instruct the agent to create a new outgoing email with the updated attachment.
-->

<!-- ## Reviewing drafts from the Inbound E-Documents page

To understand how the Payables Agent drafted the purchase invoice document, you can also go directly to the **Inbound E-Documents** page and open a purchase document draft.  

Business Central helps you focus your review by highlighting the fields that benefit most from your attention, reducing the review effort and minimizing risk of inaccuracy.

Fields that are recommended for review display an [info] information icon.

When you select this icon or use the <kbd>Alt</kbd>+<kbd>I</kbd> keyboard shortcut on the field, Business Central reveals why the Payables Agent chose that specific field value. This information helps you determine whether a better value would be more appropriate. 

You can quickly replace or correct any fields that the Payables Agent didn’t quite get right. 

To complete the review and elevate the draft to a purchase invoice document, choose the **Finalize draft** action.

> [!IMPORTANT]
> Fields recommended for review are provided as a convenience, and you aren't required to inspect all of them. Always review the entire purchase document draft, especially if you're new to the Payables Agent and are learning the limitations of how the agent works with your data.

> [!NOTE]
> While reviewing a purchase document draft, you can't use Copilot’s Autofill feature.-->

## Give instructions to the agent

When you review a step, you might need to change something the agent created or help it get unblocked. For example, you might need to make an item available, create the correct customer or vendor, or change quantities in sales quotes before the task can continue. Instead of making the changes yourself, you can guide the agent to do the work by providing instructions in the **Tasks** tab.

:::image type="content" source="media/give-instructions-to-agent.svg" alt-text="Shows a step in Copilot Task pane that includes the options to give instructions to the agent.":::

In the **Give instructions to the agent** section of the step, you might get suggestions for instructions you can give. Copilot generates these suggestions automatically based on the current task. In some cases, there are no suggestions. Alternatively, you can write your own instructions in the **Type your instruction** box. After you select a suggestion or type instructions, select **Confirm** to let the agent resume the task.

### How to write instructions

You're free to enter any text in the **Type your instruction** box, which lets you write instructions in plain, everyday language. Here are some tips to get the best results:

- Be specific and clear.
- Keep instructions focused on actions relevant to the current step.

Examples:

|Scenario|Instructions|
|-|-|
|When requested quantity of an item isn't available|Change the quantity to 50|
|When the agent can't determine the exact item|Give a quote for the Rome guest chair in blue|
|When you want to change a field| Change the shipping date to 09/01|
|When you want to specific information when creating an entity|Create vendor using OCR data|

Here's what to avoid:

- Instructions that directly alter the workflow, such as stopping the task, skipping or discarding a step. These types of operations have dedicated actions in the interface rather than through freeform instructions.
- Instructions that are out of scope for the step or task, asking the agent to update unrelated records or perform actions outside the current task's context.

## Stop a task

Most steps of a task include a **Stop** button that lets you terminate the process. When you select **Stop**, a task isn't terminated immediately&mdash;you're asked to confirm before the task is stopped.

Before you stop a task, consider the following behavior:

- Stopped tasks can't be restarted.
- Stopping the task might leave some results incomplete or unwanted, and it might require follow-up actions. Follow up actions depend on where in the process the task was stopped.
- Stopped tasks aren't deleted immediately. You can still explore a task's timeline until it's deleted, typically by an administrator.

## Related information

[Payables Agent overview](payables-agent.md)  
[Set up Payables Agent](payables-agent-setup.md)  
[FAQ for Payables Agent](faqs-payables-agent.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
