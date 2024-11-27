---
title: Set up Sales Order Agent
description: Learn how to activate the Sales Order Agent and manage user access.
ms.date: 11/27/2024
ms.topic: how-to
author: dmc-dk
ms.author: dmitrych
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
---
# Set up Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The Sales Order Agent helps Business Central users automate the entire process of capturing sales orders from their customers, monitoring incoming emails to a designated mailbox. This article explains how to set up the agent and it's functionality. Learn more about the agent in [Sales Order Agent overview](sales-order-agent.md).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Prerequisites

- Turn on the Sales Order Agent capability

   The Sales Order Agent capability is on by default. If the ![Shows the Sales Order Agent icon](media/soa-icon.png) **Sales Order Agent** badge appears in the navigation menu at the top, then the agent capability is on, but the agent isn't yet active; it must be configured and activated to process customers' requests for sales orders.

   You turn the agent capability on or off from the **Copilot & AI Capabilities** page, as you do with other Copilot features in Business Central. The Sales Order Agent is listed under **Production ready previews**. Learn more about in [Configure Copilot and AI capabilities](enable-ai.md).

- Set up the email account for sales receiving incoming requests for quotes and orders.

   The Sales Order Agent monitors incoming emails to this mailbox. The email account can be either a Microsoft 365 personal account or a shared mailbox in your organization. Learn more at [Set up e-mail](admin-how-setup-email.md).

   > [!IMPORTANT]
   > The public-facing email account your sales team uses to receive requests for quotes may often receive irrelevant emails or junk. While the agent can detect and flag irrelevant or malicious emails, it would still need to review and process every email that arrives in the designated mailbox, consuming AI resources unnecessarily. Therefore, we recommend configuring a separate, internal-facing mailbox to which you can easily copy or move relevant emails from the public-facing email account for the agent to pick up and process.

## Activate and configure Sales Order Agent

1. In the navigation bar at the upper right of the role center, select ![Shows the Sales Order Agent icon](media/soa-icon.png) **Sales Order Agent** > **Activate**.
1. On the **Configure the Copilot agent** page, turn on the **Monitor incoming information** toggle (1), select the **Mailbox** check box (2), and then set **Mailbox** field (3) the email account you want the agent to monitor.

   ![Shows the Sales Order Agent configuration page](media/soa-configuration.png)

1. Select **Manage user access** (4) to specify the users that can manage or interact with the agent. You can add more users now or later. Learn more in [Manage user access to the Sales Order Agent ](#manage-user-access-to-the-sales-order-agent).
1. Turn on the **Active** toggle (5).
1. On the right side of the page, select the **Go to next card** arrow (6), and then choose how the agent helps with inquiries, quotes, and orders. There are several options to choose from:

    |Option|Description|Default|
    |-|-|-|
    |Match only to items with availability as requested|When on, the agent only includes items that will be available on the customer's requested delivery date requested.|On|
    |Create sales documents|When on, the agent can create sales quotes and orders from email inquiries based on the remaining options in this table. When off, the remaining options are irrelevant and can't be set.|On|
    |Review quotes when created and updated|When on, the agent adds a review step for a Business Central user to a task before it creates or modifies quotes. The step is added into the process after a Business Central user confirms a quote's acceptance email from the customer. When off, the agent creates or modifies quotes without requiring user review. |Off|
    |Make orders from quotes|When on, the agent converts confirmed sales quotes into orders. Orders are created after the customer agrees to the quote via email and the Business Central user confirms the email. |On|
    |Review orders when created and updated|When on, the agent adds a review step for a Business Central user to a task before it creates or modifies orders. The step is added into the process after a Business Central user confirms an order’s acceptance email from the customer. When off, the agent creates or modifies orders without requiring user review.|Off|

1. Select **Update** (7) to complete the setup.

The **Sales Order Agent** badge changes to ![Shows the Sales Order Agent icon after configured](media/soa-activated-icon.png), which indicates the agent is active and ready to handle incoming quote requests to the mailbox.

When the Sales Order Agent is active, a scheduled task that runs every 20 seconds on the mailbox is added to the job queue. This task monitors unread messages in the mailbox. If an unread message is found, the Sales Order Agent imports the message into Business Central and verifies whether there's already a task for the mail thread. If a task for the thread already exists, the Sales Order Agent incorporates the new message into the existing task. Otherwise, it creates a new task for the message.

> [!NOTE]
> The ![Shows the Sales Order Agent icon when the agent is configure but not active](media/soa-not-activated-icon.png) badge indicates the agent is configured with mailbox, but it's not active. To check, select the *tba* badge > **Activate**.

## Manage agent permissions and user access

The Sales Order Agent has a user account in Business Central, similar to other users. You can find it on the Agents page.

By default, the Sales Order Agent is assigned the **SOA AGENT – EDIT** permission set. This permission set restricts access to only the objects, data, and UI elements (such as pages, fields, and actions) necessary for handling sales quote requests. You can change the agent's permissions on the **Agents** page; however, the agent must be first disabled to make these changes.

### User access

Business Central provides the following system permission for administrators to control user access to the agent's functionality:

- **Configure All Agents**: Grants access to manage the configuration settings of the Sales Order Agent.
- **Manage Agent Tasks**: Allows users to work with agent tasks displayed in the Copilot pane.

Additionally, the following updates were made to existing permission sets and entitlements:

- The **SECURITY** permission set now includes the **Configure All Agents** permission.
- The **System Execute - Basic** permission set now includes the **Manage Agent Tasks** permission.
- The **System Tables - Basic** permission set includes all virtual tables used by the agent (labeled as "Agent *" tables).
- Essential and Premium license entitlements now include **Manage Agent Tasks** permissions.
- All license types include **Configure All Agents** permissions.

As an administrator, you can manage which users have permission to use the Sales Order Agent. You can configure user access during setup or later through the **Sales Order Agent** card page by selecting the **Manage user access link**.

- To configure the Sales Order Agent, users need to have the **"Configure All Agents"** permission (included in SUPER and SECURITY permission sets) or be listed as agent users with the **Can Configure** field selected on the **Select users that can manage or interact with the Agent** page.
- To work with agent tasks displayed in the Copilot pane, users must have the **"Manage Agent Tasks"** permission (either explicitly or as part of their Essential or Premium license permissions) and be listed as agent users on the **Select users that can manage or interact with the Agent page**.

<!--
## Choose how the agent helps with inquiries, quotes, and orders

There are several configuration options that define how the agent assists with inquiries, quotes, and orders. You specify these options on the second page of the **Configure the Copilot agent**.

|Option|Description|Default|
|-|-|-|
|Match only to items with availability as requested|When on, the agent only includes in a quote the items that will be available on the cutomer's requested delivery date requested.|On|
|Create sales documents|When on, the agent can create sales quotes and orders from email inquiries based on the remaining options in this table. When off, the remaining options are irrelevant and can't be set.|On|
|Review quotes when created and updated|When on, the agent adds a review step for a Business Central user to a task before it creates or modifies quotes. The step is added into the process after a Business Central user confirms a quote's acceptance email from the customer. When off, the agent creates or modifies quotes without requiring user review. |Off|
|Make orders from quotes|When on, the agent converts confirmed sales quotes into orders. Orders are created after the customer agrees to the quote via email and the Business Central user confirms the email. |On|
|Review orders when created and updated|When on, the agent adds a review step for a Business Central user to a task before it creates or modifies orders. The step is added into the process after a Business Central user confirms an order’s acceptance email from the customer. When off, the agent creates or modifies orders without requiring user review.|Off|-->

## Next steps

[Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)

## Related information

[Sales order agent overview](sales-order-agent.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)
[Configure Copilot and AI capabilities](enable-ai.md)  
