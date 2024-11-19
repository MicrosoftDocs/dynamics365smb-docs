---
title: FAQ for sales order taker agent
description: This FAQ provides information about the AI technology used in Business Central, along with key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 07/03/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
---
# FAQ for sales order taker agent 

These frequently asked questions (FAQ) describe the AI impact of sales order taker agent feature in Business Central.

## What is the sales order taker agent?

The sales order taker agent is an integrated copilot with agent capabilities that automates the task of taking sales orders. The agent can handle the entire sales order capturing process. It starts by receiving a customer's order by email. It then identifies the customer from the registered list in Business Central, prepares a quote with the requested items, checks availability of items, sends the quote to the customer for approval, and upon confirmation, converts it to salesorder.

The agent is readliy available in the product. You just need to activate it. The agent is also configurable, for example, allowing you to define a list of users who can delegate the process of taking the sales orders, specify the channel for receiving the orders (for example, by e-mail), select the steps which they want to include or exclude in that process. Once the agent's activated, it's ready to process sales orders.  

## What are capabilities of the sales order taker agent?

To support of and in addition to the task of taking and processing sales orders, the agent has the following capabilities:

- Operational instructions and configuration

  The agent operates based on its instructions and user configuration. It uses AI to identify and carry out the steps needed to complete this task within the Business Central environment. 

  The agent is provided with its own set of high-level business instructions, which describe its purpose, outline the task it needs to perform and additional considerations it needs to take when performing the steps. These instructions are defined in the agent code and are not visible to the users. 
  
  When configuring the sales order taker agent, users can define the list of other users who can delegate their tasks to the agent, channels for receiving orders (for example, email), and select which steps of the order taking process should be included or excluded (for example, whether to convert generated sales quote into an order). 

- Task execution and interaction

  To execute its tasks, the sales order taker agent interacts with the Business Central web client using a logical representation of the UI called the logical UI API.  

  Through that logical UI API, the agent can read the data displayed on the product pages and access properties of the UI elements (for example, names and descriptions of the pages, fields, actions, and tooltips). It can then combine that data with the instructions provided by the users during agent configuration, along with data received via e-mail messages, and then use AI with its conventional business knowledge to orchestrate the steps which needed to complete each step and the overall task.  

  The agent will attempt to overcome errors and adapt when conditions change (for example, when new data is entered by another user on a page). It can also engage in multi-turn e-mail conversation with the customer placing the order, if it needs to clarify or confirm their requirements.  

- Access and permissions

  The agent runs as just another user in Business Central and is granted access solely to the necessary parts of the product to perform its task. It comes with predefined permissions and a UI role (profile) that can be assigned to it by the configuring user, limiting which parts of the product the agent can access and which UI elements (pages, fields, actions and FactBoxes) it can interact with. 

- User intervention and notification

  The agent will seek user intervention when specific situations arise, for instance, when preparing outbound communications or providing business approval for key operations.  

  The agent is invoked by a built-in e-mail dispatcher, running as a scheduled task, which monitors the company mailbox that’s specified in the agent’s configuration settings. The dispatcher hands over e-mails received from the customers to the sales order taker agent and sends results of the agent's work, such as prepared sales quote with requested items, in response. 

- Transparency and change control

  Business Central maintains full transparency and provides control over changes made by the agent. The agent brings humans in the loop when their attention is required by issuing in-product notifications that are displayed on the role center. This happens before any outbound e-mail communications—such as sending a final sales quote or an order to a customer— when the agent needs users to provide some missing details to get unblocked, or to provide business approval for important changes.  

  For each task performed by the agent, users get a detailed timeline that shows the key steps taken by the agent and human users, including the e-mail conversation. Users can review this information and update the values and actions the agent suggested if needed. Business Central can also display the reasoning used by the agent and citations that have led to suggesting a certain value.

<!--

- **User directives:** Operating based on user directives, the agent utilizes AI to complete necessary steps within the Business Central environment and seeks user intervention when specific situations arise.
- **Configuration settings:** Users can define the list of delegators, channels for receiving orders (for example, email), and select which steps to include or exclude in the process.
- **Controlled access** The agent is granted access solely to the necessary parts of the product to perform its duties. It comes with predefined permissions and UI roles that can be assigned by the configuring user.
- **External Orchestrator:** The agent is invoked by an external orchestrator, Copilot Studio, which monitors the company mailbox (specified in the agent configuration settings). The orchestrator hands over emails received from the customer to the agent and sends results of the agent's work (prepared sales quote with requested items) in response.
- **Transparency and control:** Maintains full transparency and control over changes made by the agent, providing notifications, a task context and history view, and detailed review options.
- **Auditing the agent trail:** Actions done by the agent, including navigating pages, creating and modifying records, and calling actions, carry the agent’s user ID. This user ID appears in the same places and in the same way as with others users, such as in list views, history, posted documents, notifications, and more. Additionally, Business Central records and displays the user (owner or delegator) who delegated the task to the agent.-->

## What is the intended use of the sales order taker agent?

The sales order taker agent is intended to handle the end-to-end sales order capturing process. This process includes taking the customer’s order by e-mail, iterating on the details with the customer via e-mail, preparing the sales quote with the requested items, checking the availability of the items, sending the quote to the customer for approval, and finally converting the quote to a sales order upon receiving customer confirmation.

## How was sales order taker agent evaluated? What metrics are used to measure performance?

We defined a set of seven categories of scenarios and created test cases for these. In total, we have a suite of 50 test cases as otulines in the following table:

|Category|Description|Test case|
|-|-|-|
|Quotes|Precise request for a quote with variations (delivery dates or not, terse/verbose request, complete or incomplete email signature) |Single/multiturn&nbsp;with&nbsp;approval&nbsp;by&nbsp;customer.&nbsp;Up&nbsp;to&nbsp;3&nbsp;items.|
|||Quote request with 4 or more items|
|||Request for quote by item reference. Up to three lines.|
|||Quote sent but not approved by customer.|
|||Quote request from unknown customer.|
|||Quote request for unknown item.|
|Information|Requests for information about items followed by a quote request|Single/multi-turn with quote based on information|
|||Request for information about unknown items|

## What are the limitations of sales order taker agent? How can users minimize the impact of the sales order taker agent limitations when using the system?

- The system has been tested with item names and item descriptions that are both in English. Mixed language input may result in lesser-quality output, as the system will still work based on pure string similarity, but semantic part of the matching may or may not work. 

- Due to limited language support, the system will not be available initially to Canadian customers due to regulatory language compliance as both English and French languages as mandatory.

  - The agent reads inbound emails via Shared inbox on Exchange. Other ways to receive email is not supported. 
  - The agent doesn't read files attached to emails. 

- Supported sales documents: create new Sales Quote, convert quote to order 
- Creation of items, contacts, customers is not supported.
- Very large emails might exceed the number of tokens that can be processed in one request. This will lead the agent to trigger a request for a human to investigate (very similar to how a human is requested to approve that the agent approves an email). 
- If the agent stops working, for example, it loses access to the shared mailbox or calls to the LLM are failing, it notifies the users in the same place that it normally notifies users when, e.g., it needs approval to process an email. 

## What operational factors and settings allow for effective and responsible use of the feature?

Business Central users maintain full transparency and control over the changes made by the sales order taker agent by: 

- Receiving notifications from the agent, when it requires help, or when the process demands human review (e.g. for all outbound messages).
- Understanding task context and history through a 'timeline' view.
- Reviewing detailed changes and suggestions made by the agent within a task
- Adjusting changes and approving task continuation.
- Getting a detailed review of an entity, surfacing all changes and suggestions made by the agent within a specific task, allowing humans to review and adjust these changes and sign off on proceeding with the task.
- Reviewing the agent's KPIs to assess the impact of its work.

## See also


[!INCLUDE[footer-include](includes/footer-banner.md)]
