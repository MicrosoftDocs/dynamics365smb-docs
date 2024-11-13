---
title: Set up sales order agent
description: This FAQ provides information about the AI technology used in Business Central, along with key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 07/03/2024
ms.topic: how-to
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
  - get-started
---

# Set up the sales order

This article explains the tasks required to set up the sales ore agent.

## Activate the sales order agent

The sales order agent is activated by default. If the sales order agent badge is present in the navigation menu at the top, then it's activated.  

You can activate or deactivate it from the **Copilot & AI Capabilities** page, as you do with other Copilot features in Business Central. The sales order agent is listed under **Production ready previews**. Learn more about activating and deactivating Copilot features in [Configure Copilot and AI capabilities](enable-ai.md). 

A screenshot of a computer

## Configure the sales order agent 

### Prerequisites

- Set up e-mail: The sales order agent monitors incoming emails to specific mailbox for sales quote requests. To configure the sales order agent, you need to know the email account of the mailbox that you want it to monitor. The email account can be either a Microsoft 365 personal account or a shared mailbox in your organization. Learn more at [Set up e-mail](admin-how-setup-email.md).

### Set up the sales order agent 

1. At the top of the screen, select  sales order agent.  
1. On the Set up sales order agent copilot page, turn on Monitor incoming information toggle, then set Mail box to the e-mail account you want to monitor. 

    A screenshot of a computer

1. Turn on the Active toggle and then select Update to complete the set up. 

The sales order agent badge changes to , which indicates the sales order agent is ready to handle incoming sales quote requests to the mailbox. 

When the sales order agent is activated, a scheduled task that runs every minute on the mailbox is added to the job queue. This task monitors unread messages in the mailbox. If an unread message is found, the sales order agent imports the message into Business Central and verifies whether there is already a task for the mail thread. If a task for the thread already exists, the sales order agent incorporates the new message into the existing task. Otherwise, it creates a new task for the message. 

## Control sales order agent permissions and user access 

The sales order agent has a user account in Business Central similar to other users. By default, the sales order agent is assigned the **SOA AGENT – EDIT** permission set. This permission set restricts access to only the necessary objects, data, and UI elements (such as pages, fields, and actions) needed for handling sales quote requests. 

As an administrator, you can manage which users have permission to access the sales order agent. You can specify the extent to which tasks can be delegated to it, the communication channels for receiving orders (such as email), and the stages of the order process to integrate (for instance, whether to convert a generated sales quote into an order).

You configure permissions and user access from the **sales order agent card page. To open this page, complete the following steps: 

1. Press Alt+Q, search for Agents, and then choose the related link.
1. On the Agents page, select sales order agent. 

## Next steps

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
