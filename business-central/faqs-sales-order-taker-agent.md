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

- **User directives:** Operating based on user directives, the agent utilizes AI to complete necessary steps within the Business Central environment and seeks user intervention when specific situations arise.
- **Configuration settings:** Users can define the list of delegators, channels for receiving orders (for example, email), and select which steps to include or exclude in the process.
- **Controlled access** The agent is granted access solely to the necessary parts of the product to perform its duties. It comes with predefined permissions and UI roles that can be assigned by the configuring user.
- **External Orchestrator:** The agent is invoked by an external orchestrator, Copilot Studio, which monitors the company mailbox (specified in the agent configuration settings). The orchestrator hands over emails received from the customer to the agent and sends results of the agent's work (prepared sales quote with requested items) in response.
- **Transparency and control:** Maintains full transparency and control over changes made by the agent, providing notifications, a task context and history view, and detailed review options.
- **Auditing the agent trail:** Actions done by the agent, including navigating pages, creating and modifying records, and calling actions, carry the agent’s user ID. This user ID appears in the same places and in the same way as with others users, such as in list views, history, posted documents, notifications, and more. Additionally, Business Central records and displays the user (owner or delegator) who delegated the task to the agent.

## What is the intended use of the sales order taker agent?

Sales Order Taker agent is intended to handle the end-to-end sales order capturing process, from taking the customer’s order by e-mail, preparing the quote with requested items, checking the availability of the items, sending the quote to the customer for approval, and finally converting the quote to a sales order upon receiving customer confirmation.

## How was sales order taker agent evaluated? What metrics are used to measure performance?

[Provide evidence of system or feature accuracy and performance, and, when applicable, a description of the extent to which these results are generalizable across use cases that were not part of the evaluation.]

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
