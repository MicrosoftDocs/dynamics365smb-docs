---
title: Set up sales order agent
description: Learn how to activate the sales order agent and manage user access.
ms.date: 1/18/2024
ms.topic: how-to
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
  - get-started
---

# Set up the sales order agent

The sale order agent automates processing sales quote requests to orders by monitoring incoming emails to a designated mailbox. To set up the sales order agent working, you first need make sure it's activated on the **Copilot & AI Capabilities** page. Once it's activated, you configure the agent to monitor the desired mailbox, and manage user access to the agent.

## Turn on the sales order agent

The sales order agent is turned on by default. If the ![Shows the sales order agent icon](media/soa-icon.png) **Sales Order Agent** badge appears in the navigation menu at the top, then the agents is on, but not yet configured to process sales orders.

You turn the agent on or off from the **Copilot & AI Capabilities** page, as you do with other Copilot features in Business Central. The sales order agent is listed under **Production ready previews**. Learn more about in [Configure Copilot and AI capabilities](enable-ai.md).

## Configure the sales order agent

1. Set up the email account for sales recieving incoming requests for quotes and orders. 

   The sales order agent monitors incoming emails to this mailbox. The email account can be either a Microsoft 365 personal account or a shared mailbox in your organization. Learn more at [Set up e-mail](admin-how-setup-email.md).

1. In the top the role center, select ![Shows the sales order agent icon](media/soa-icon.png) **Sales Order Agent** > **Activate**.  
1. On the **Configure the Copilot agent** page, turn on the **Monitor incoming information** toggle, select the **Mailbox** check box, and then set **Mailbox** field the email account you want to monitor.

   ![Shows the sales order agent configuration page](media/soa-configuration.png)

1. Turn on the **Active** toggle.
1. Select **Manage user access** to specify the users that can manage or interact with the agent.

   By default, you account is granted **UserAndOwner** access to agent. You can add more users now or later. Learn more in [Manage user access to the sales order agent ](#manage-user-access-to-the-sales-order-agent).
1. Select **Update** to complete the set up.

The **Sales Order Agent** badge changes to ![Shows the sales order agent icon after configured](media/soa-activated-icon.png), which indicates the sales order agent is active ready to handle incoming sales quote requests to the mailbox.

When the sales order agent is active, a scheduled task that runs every minute on the mailbox is added to the job queue. This task monitors unread messages in the mailbox. If an unread message is found, the sales order agent imports the message into Business Central and verifies whether there is already a task for the mail thread. If a task for the thread already exists, the sales order agent incorporates the new message into the existing task. Otherwise, it creates a new task for the message.

> [!]

## Manage user access to the sales order agent 

The sales order agent has a user account in Business Central similar to other users. By default, the sales order agent is assigned the **SOA AGENT – EDIT** permission set. This permission set restricts access to only the necessary objects, data, and UI elements (such as pages, fields, and actions) needed for handling sales quote requests.

As an administrator, you can manage which users have permission to access the sales order agent and and the tasks they can perform to prosees incoming requests. <!--> You can specify the extent to which tasks can be delegated to it, the communication channels for receiving orders (such as email), and the stages of the order process to integrate (for instance, whether to convert a generated sales quote into an order).-->

You configure user access during the agent configuration or later from **Sales Order Agent** card page, describe in the follwoing steps To open this page, complete the following steps: 

1. Press <kbd>Alt</kbd>+<kbd>Q</kbd>, search for **Agents**, and then choose the related link.
1. On the **Agents** page, select sales order agent. 

## Next steps

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
