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
---
# Set up sales order agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The sale order agent automates processing sales quote requests to orders by monitoring incoming emails to a designated mailbox. To set up the sales order agent, you first need make sure it's turned on using the **Copilot & AI Capabilities** page. Once the agent is turned on, you configure it to monitor the desired mailbox, and manage user access to the agent.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Turn on sales order agent

The sales order agent is turned on by default. If the ![Shows the sales order agent icon](media/soa-icon.png) **Sales Order Agent** badge appears in the navigation menu at the top, then the agent is on, but not yet configured to process sales orders.

You turn the agent on or off from the **Copilot & AI Capabilities** page, as you do with other Copilot features in Business Central. The sales order agent is listed under **Production ready previews**. Learn more about in [Configure Copilot and AI capabilities](enable-ai.md).

## Configure  sales order agent

1. Set up the email account for sales receiving incoming requests for quotes and orders. 

   The sales order agent monitors incoming emails to this mailbox. The email account can be either a Microsoft 365 personal account or a shared mailbox in your organization. Learn more at [Set up e-mail](admin-how-setup-email.md). <!-- Sorry, your Copilot isn't activated for Sales Order Agent-->

1. In the navigation bar at the top of the role center, select ![Shows the sales order agent icon](media/soa-icon.png) **Sales Order Agent** > **Activate**.  
1. On the **Configure the Copilot agent** page, turn on the **Monitor incoming information** toggle, select the **Mailbox** check box, and then set **Mailbox** field the email account you want to monitor.

   ![Shows the sales order agent configuration page](media/soa-configuration.png)

1. Turn on the **Active** toggle.
1. Select **Manage user access** to specify the users that can manage or interact with the agent.

   By default, you're granted **UserAndOwner** access to agent. You can add more users now or later. Learn more in [Manage user access to the sales order agent ](#manage-user-access-to-the-sales-order-agent).
1. Select **Update** to complete the setup.

The **Sales Order Agent** badge changes to ![Shows the sales order agent icon after configured](media/soa-activated-icon.png), which indicates the agent is active and ready to handle incoming quote requests to the mailbox.

When the sales order agent is active, a scheduled task that runs every minute on the mailbox is added to the job queue. This task monitors unread messages in the mailbox. If an unread message is found, the sales order agent imports the message into Business Central and verifies whether there's already a task for the mail thread. If a task for the thread already exists, the sales order agent incorporates the new message into the existing task. Otherwise, it creates a new task for the message.

> [!NOTE]
> The *tba* badge indicates the agent is configured with mailbox, but it's not active. To check, select the *tba* badge > **Activate**.

## Manage user access to sales order agent

The sales order agent has a user account in Business Central similar to other users. By default, the sales order agent is assigned the **SOA AGENT – EDIT** permission set. This permission set restricts access to only the necessary objects, data, and UI elements (such as pages, fields, and actions) needed for handling sales quote requests.

As an administrator, you can manage which users have permission to use the sales order agent. You can configure user access during the configuration or later from **Sales Order Agent** card page as described in the following steps. 

1. Press <kbd>Alt</kbd>+<kbd>Q</kbd>, search for **Agents**, and then choose the related link.
1. On the **Agents** page, select sales order agent. 

Need more info. Currently there are two option UserandOwner and User. Note sure what these mean.

## Next steps

[Process sales quotes and orders with sales order agent](sales-order-agent-process.md)

## Related information

[Sales order agent overview](sales-order-agent.md)  
[FAQ for sales order agent](faqs-sales-order-taker-agent.md)
[Configure Copilot and AI capabilities](enable-ai.md)  
