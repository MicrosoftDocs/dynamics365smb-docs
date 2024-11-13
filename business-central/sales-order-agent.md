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

# Sales order Copilot agent

This article explains the sales order agent's capabilities, setup, and use during its preview phase. It guides you through configuring the agent to monitor emails for sales quote requests, process them, and convert them into sales orders. It provides instructions to ensure effective usage and evaluation of the agent during the preview. 

## Introduction to the sales order agent

The sales order agent is a copilot with agent capabilities that automates the task of taking sales orders. It starts by receiving a customer's order by e-mail. Analyzing the content of that e-mail, it then identifies the customer from the registered list in Business Central, prepares a sales quote with the requested items, checks availability of items, sends the quote to the customer for approval, and upon confirmation, converts the quote into a sales order. 

The agent is readily available in the product. You just need to activate it. The sales order agent is also configurable, allowing you to define its name, a list of other users who can delegate the process of taking the sales orders to it, and more. 

### Capabilities 

The sales order agent operates based on its instructions and user configuration. It uses AI to identify and carry out the steps needed to complete this task within the Business Central environment. 

The sales order agent is provided with its own set of high-level business instructions, which describe its purpose, outline the task it needs to perform and additional considerations it needs to take when performing the steps. These instructions are defined in the sales order agent code and are not visible to the users. 

### Configurability 

When configuring the sales order agent, users can define the list of other users who can delegate their tasks to the sales order agent, channels for receiving orders (for example, email), and select which steps of the order taking process should be included or excluded (for example, whether to convert generated sales quote into an order). 

Operation through logical UI API 

To execute its tasks, the sales order agent interacts with the Business Central web client using a logical representation of the UI called the logical UI API.  

Through that logical UI API, the sales order agent can read the data displayed on the product pages and access properties of the UI elements (for example, names and descriptions of the pages, fields, actions, and tooltips). It can then combine that data with the instructions provided by the users during sales order agent configuration, along with data received via e-mail messages, and then use AI with its conventional business knowledge to orchestrate the steps which needed to complete each step and the overall task.  

The sales order agent will attempt to overcome errors and adapt when conditions change (for example, when new data is entered by another user on a page). It can also engage in multi-turn e-mail conversation with the customer placing the order, if it needs to clarify or confirm their requirements.  

The sales order agent runs as just another user in Business Central and is granted access solely to the necessary parts of the product to perform its task. It comes with predefined permissions and a UI role (profile) that can be assigned to it by the configuring user, limiting which parts of the product the sales order agent can access and which UI elements (pages, fields, actions and FactBoxes) it can interact with. 

The sales order agent will seek user intervention when specific situations arise, for instance, when preparing outbound communications or providing business approval for key operations.  

The sales order agent is invoked by a built-in e-mail dispatcher, running as a scheduled task, which monitors the company mailbox that’s specified in the sales order taker’s configuration settings. The dispatcher hands over e-mails received from the customers to the sales order agent and sends results of its work, such as prepared sales quote with requested items, in response. 

## Transparency 

Business Central maintains full transparency and provides control over changes made by the sales order agent. 

The sales order agent brings humans in the loop when their attention is required by issuing in-product notifications that are displayed on the role center. This happens before any outbound e-mail communications—such as sending a final sales quote or an order to a customer— when the sales order agent needs users to provide some missing details to get unblocked, or to provide business approval for important changes.  

For each task performed by the sales order agent, users get a detailed timeline that shows the key steps taken by the sales order agent and human users, including the email conversation. Users can review this information and update the values and actions the sales order agent suggested if needed. Business Central can also display the reasoning used by the sales order agent and citations that have led to suggesting a certain value. 

## Intended uses

The sales order agent is intended to handle the end-to-end sales order capturing process. This process includes taking the customer’s order by e-mail, iterating on the details with the customer via e-mail, preparing the sales quote with the requested items, checking the availability of the items, sending the quote to the customer for approval, and finally converting the quote to a sales order upon receiving customer confirmation. 




 
## See also

[Configure Copilot and AI capabilities](enable-ai.md)  
[Analyze data in lists with Copilot](analysis-assist.md)  
[Chat with Copilot](chat-with-copilot.md)  
[Create marketing text with Copilot](item-marketing-text.md)  
[Map e-documents to purchase order lines with Copilot](map-edocuments-with-copilot.md)  
[Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)  
[Suggest lines on sales orders with Copilot](sales-suggest-sales-lines-with-copilot.md)
