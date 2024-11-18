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

# Sales order agent overview

The sales order agent automates the task of taking sales order, handling the end-to-end process from the customer's request to order's creation:

- Receives a customer's order by e-mail.
- Analyzes the e-mail to identify the customer from the registered list in Business Central
- Prepares a sales quote with the requested items based on item availability
- Sends the quote to the customer for approval.
- Upon confirmation, converts the quote into a sales order.

## Transparency and intervention

The sales order agent maintains full transparency by including humans in the loop during the entire process. The agent enables you to review and confirm changes before they're committed to the system and shared with the customer. It issues  in-product notifications that users must address before the agent can continues. For example, a user must approve any outbound e-mail messages to customer before they're sent or provide missing details to about a request.

For each task performed by the sales order agent, users get a detailed timeline that shows the key steps taken by the sales order agent and human users, including the email conversation. Users can review this information and update the values and actions the sales order agent suggested if needed. Business Central can also display the reasoning used by the sales order agent and citations that have led to suggesting a certain value.

## Setup and user access management

The agent is readily available in the product. You only need to activate it by specifying an email inbox you want the agent to monitor. You can also specify the users who can delegate their tasks to the sales order agent, channels for receiving orders (for example, email), and select which steps of the order taking process should be included or excluded (for example, whether to convert generated sales quote into an order). 

> [!Video https://www.youtube.com/watch?v=6icbmbLc_Og]

*The video doesn't exactly reflect how the feature currently works or looks in the product. The feature has changed since the video was produced. But it gives you a general idea of the feature and what you can use it for.*
  
<!--
### Capabilities 

The sales order agent operates based on its instructions and user configuration. It uses AI to identify and carry out the steps needed to complete this task within the Business Central environment. 

The sales order agent is provided with its own set of high-level business instructions, which describe its purpose, outline the task it needs to perform and additional considerations it needs to take when performing the steps. These instructions are defined in the sales order agent code and are not visible to the users. 



### Operation through logical UI API

To execute its tasks, the sales order agent interacts with the Business Central web client using a logical representation of the UI called the logical UI API.  

Through that logical UI API, the sales order agent can read the data displayed on the product pages and access properties of the UI elements (for example, names and descriptions of the pages, fields, actions, and tooltips). It can then combine that data with the instructions provided by the users during sales order agent configuration, along with data received via e-mail messages, and then use AI with its conventional business knowledge to orchestrate the steps which needed to complete each step and the overall task.  

The sales order agent will attempt to overcome errors and adapt when conditions change (for example, when new data is entered by another user on a page). It can also engage in multi-turn e-mail conversation with the customer placing the order, if it needs to clarify or confirm their requirements.  

The sales order agent runs as just another user in Business Central and is granted access solely to the necessary parts of the product to perform its task. It comes with predefined permissions and a UI role (profile) that can be assigned to it by the configuring user, limiting which parts of the product the sales order agent can access and which UI elements (pages, fields, actions and FactBoxes) it can interact with. 

The sales order agent will seek user intervention when specific situations arise, for instance, when preparing outbound communications or providing business approval for key operations.  

The sales order agent is invoked by a built-in e-mail dispatcher, running as a scheduled task, which monitors the company mailbox that’s specified in the sales order taker’s configuration settings. The dispatcher hands over e-mails received from the customers to the sales order agent and sends results of its work, such as prepared sales quote with requested items, in response. -->

## Next steps

- [Set up the sales order agent](sales-order-agent-setup.md)
- [Process sales quotes and orders using the sales order agent](sales-order-agent-process.md)

## Related information

[Configure Copilot and AI capabilities](enable-ai.md)  

