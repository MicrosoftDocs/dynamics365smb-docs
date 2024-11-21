---
title: How-to topic template #Required; page title displayed in search results. Don't enclose in quotation marks.
description: How-to description #Required; article description that's displayed in search results. Don't enclose in quotation marks. Do end with a period.
author: rhanajoy #Required; your GitHub user alias, with correct capitalization.
ms.author: rhcassid #Required; your Microsoft alias; optional team alias.
ms.reviewer: kfend #Required; Microsoft alias of content publishing team member.
ms.topic: how-to #Required; don't change.
ms.collection: get-started #Required; If this isn't a getting started article, don't remove the attribute, but leave the value blank. The values for this attribute will be updated over time.
ms.date: 11/13/2024
ms.custom: bap-template #Required; don't change.
---
# Process sales quotes and orders with sales order agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

When the sales order agent is activated, it monitors the designated mailbox for incoming emails about item inquiries from customers. When it identifies a potential request, its starts the process for converting the request to an order. Some steps in the process require your intervention. Learn more about the steps in the process in [Understand the process flow](sales-order-agent.md#understand-the-general-flow).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Prerequisites

Sale order agent is activated, you have permission to use it. Learn more in [Set up sales order agent](sales-order-agent-setup.md).

## Get started

You collaborate with the sales order agent to review and convert quotes into orders using the **Tasks** view in the **Copilot** pane.

To access this view, select the  sales order agent badge on the right side of the navigation menu at the top. A red circle with a number on the badge indicates the number of tasks needing attention.  

*A screenshot of a computer*

The **Tasks** view opens in the **Copilot pane**, showing tasks recently created by the sales order agent, with those requiring attention&mdash;like reviewing an incoming or outgoing email&mdash;at the top of the list.  

For each sales quote request, the sales order agent adds a "task" in the "Tasks" view for tracking, reviewing, and processing the quote into an order. A task can consist of multiple steps that make up a timeline of the entire process.

## View timeline and details of steps

From **Tasks** view, you can view the details of each step of task, in chronological order. Click on the task or select **...** (More options) > **Show Details**.  

## Review a step

Your intervention is required for various steps in the process of creating a sale order, for example:

- Review and confirm incoming email requests for sales quotes from customers.
- Review and confirm the sales quotes and order, along with outgoing emails created by the sales order agent for the customer.
- Provide assistance to the sales order agent for fixing a problem.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** view. To review a step: 

1. On the step, select **...** (More options) > **Review**.  

   The **Tasks** view switches to the **Review** pane, and the Agent Task Message window opens to display the contents of the incoming or outgoing email.  
1. Review the contents of the email. 
1. When you're satisfied with the content and want the process to continue, select **Confirm** on in the **Review** pane. If you want to cancel the process, select **Stop**.

After confirmation, the sales order agent moves the task on for more processing. After some time, a new notification appears on the sales order agent badge. Follow the same flow to verify and approve the results.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the sales order agent](sales-order-agent-setup.md)  
[FAQ for sales order agent](faqs-sales-order-taker-agent.md)
[Configure Copilot and AI capabilities](enable-ai.md)  