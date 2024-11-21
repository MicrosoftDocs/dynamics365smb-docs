---
title: FAQ for sales order agent
description: This FAQ provides information about the AI technology used by sales order agent in Business Central. It provides key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 11/19/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
---
# FAQ for sales order agent 

These frequently asked questions (FAQ) describe the AI impact of sales order agent feature in Business Central.

## What is the sales order agent?

The sales order agent is an integrated copilot with agent capabilities that automates the task of taking sales orders. The agent can handle the entire sales order capturing process. It starts by receiving a customer's order by email. It then identifies the customer from the registered list in Business Central, prepares a quote with the requested items, checks availability of items, sends the quote to the customer for approval, and upon confirmation, converts it to  sales order.

The agent is readily available in the product. You just need to activate it. <!--The agent is also configurable. For example, you can define a list of users who can delegate the process of taking the sales orders. Or, specify the channel for receiving the orders (for example, by e-mail), and select the steps to include or exclude in that process. -->Once you activate the agent, it's ready to process sales orders.  

## What are capabilities of the sales order agent?

To support of and in addition to the task of taking and processing sales orders, the agent has the following capabilities:

- Operational instructions and configuration

  The agent operates based on its instructions and user configuration. It uses AI to identify and carry out the steps needed to complete this task within the Business Central environment.

  The agent is provided with its own set of high-level business instructions. These instructions describe its purpose, the tasks it needs to perform, and other considerations it needs to take when performing the steps. They're defined in the agent code and aren't visible to the users.
  
  The agent is also configurable. For example, you can specify: the users who can delegate the process of taking the sales orders, the channels for receiving the orders (for example, by e-mail), and the steps to include or exclude in the process.

- Task execution and interaction

  To execute its tasks, the sales order agent interacts with the Business Central web client using a logical representation of the UI called the logical UI API.  

  Through the logical UI API, the agent can read data displayed on the product pages and access properties of the UI elements, such as page names/descriptions, fields, actions, and tooltips. It can then combine that data with the user-provided instructions from the agent configuration and the data received via e-mail messages. The agent then uses AI and conventional business knowledge to orchestrate the necessary steps to complete each step and the overall task.

  The agent attempts to overcome errors and adapt when conditions change (for example, when another user enters new data on a page). It can also engage in multi-turn e-mail conversation with the customer placing the order, if it needs to clarify or confirm their requirements.  

- Access and permissions

  The agent runs as its own user in Business Central and is granted access solely to the necessary parts of the product to perform its task. It comes with a predefined permission set and UI role (profile). that limits the parts of the product the agent can access and the UI elements it can interact with, such as page, fields, and actions.
- User intervention and notification

  The agent seeks user intervention when specific situations arise, for instance, when preparing outbound communications or providing business approval for key operations.  

  The agent is invoked by a built-in e-mail dispatcher that runs as a scheduled task and monitors the company mailbox specified in the agent's configuration. The dispatcher hands over e-mails received from the customers to the sales order agent and sends results of the agent's work, such as prepared sales quote with requested items, in response. 

- Transparency and change control

  Business Central maintains full transparency and provides control over changes made by the agent. The agent brings humans in the loop when their attention is required by issuing in-product notifications that are displayed on the role center. For example, a notification happens before any outbound e-mail communications, such as sending a final sales quote or an order to a customer, when the agent needs more details to get unblocked, or when approval for important changes.  

  For each task performed by the agent, users get a detailed timeline that shows the key steps taken by the agent and human users, including the e-mail conversation. Users can review this information and update the values and actions the agent suggested if needed. Business Central can also display the reasoning used by the agent and citations that led to a suggested value.

<!--

- **User directives:** Operating based on user directives, the agent utilizes AI to complete necessary steps within the Business Central environment and seeks user intervention when specific situations arise.
- **Configuration settings:** Users can define the list of delegators, channels for receiving orders (for example, email), and select which steps to include or exclude in the process.
- **Controlled access** The agent is granted access solely to the necessary parts of the product to perform its duties. It comes with predefined permissions and UI roles that can be assigned by the configuring user.
- **External Orchestrator:** The agent is invoked by an external orchestrator, Copilot Studio, which monitors the company mailbox (specified in the agent configuration settings). The orchestrator hands over emails received from the customer to the agent and sends results of the agent's work (prepared sales quote with requested items) in response.
- **Transparency and control:** Maintains full transparency and control over changes made by the agent, providing notifications, a task context and history view, and detailed review options.
- **Auditing the agent trail:** Actions done by the agent, including navigating pages, creating and modifying records, and calling actions, carry the agent’s user ID. This user ID appears in the same places and in the same way as with others users, such as in list views, history, posted documents, notifications, and more. Additionally, Business Central records and displays the user (owner or delegator) who delegated the task to the agent.-->

## What is the intended use of the sales order agent?

The sales order agent is intended to handle the end-to-end sales order capturing process. This process includes:

- Taking the customer’s order by e-mail
- Iterating on the details with the customer via e-mail
- Preparing the sales quote with the requested items
- Checking the availability of the items
- Sending the quote to the customer for approval
- Converting the quote to a sales order upon receiving customer confirmation.

## How was the sales order agent evaluated? What metrics are used to measure performance?

We defined a set of categories and scenarios and created test cases for each as described in the following table. In total, we have a suite of 50 test cases.

|Category|Scenario|
|-|-|
|Quotes<br><br>Precise request for a quote with variations (delivery dates or not, terse/verbose request, complete or incomplete email signature) |Single/multi-turn with approval by customer. Up to three items.|
||Quote request with four or more items|
|||Request for quote by item reference. Up to three lines.|
||Quote sent but not approved by customer.|
||Quote request from unknown customer.|
||Quote request for unknown item.|
|Information<br><br>Requests for information about items followed by a quote request|Single and multi-turn with quote based on information|
||Request for information about unknown items|

## What are the limitations of sales order agent? How can users minimize the impact of the sales order agent limitations when using the system?

- Languages

  - The system was tested with the content (emails and product localization) provided in US English. 
  - Mixed language input might result in lower-quality output because the system relies on pure string similarity, and the semantic part of the matching might not work properly. 
  - Due to limited language support, the system isn't initially available to Canadian customers because regulatory language compliance mandates support for both English and French. 

- E-mailing

  - The agent reads inbound emails via a shared inbox on Microsoft Exchange. Learn more in [Set up email](admin-how-setup-email.md). Other ways to receive email aren’t supported.
  - The agent doesn't read files attached to emails.  
  - Large emails might exceed the number of tokens that can be processed in one request. This condition leads the agent to trigger a request for a human to investigate (similar to how a human is requested to approve whether the agent approves an email). 
  - E-mail messages generated by the agent might contain incorrect information. The agent is designed to ask a human user to review and edit every outbound message if necessary.  

- Entities and data the agent can work with

  - The agent can only create sales quote and sales order documents. It can't create or work with the other sales documents (such as blank orders, invoices, or credit memos) or documents in other areas of the product (such as purchase or service orders).
  - The agent doesn't create new items, contacts, or customers. It only works with the entities that are already registered in Business Central.  
  - Posting of documents isn't supported.  

- Other limitations

  - If the agent stops working, it notifies the users in the same place that it normally notifies users when it needs approval to process an email. Examples are if the agent loses access to the shared mailbox or calls to the LLM (large language models) are failing.
  - Delegated administrators can't activate the agent.  
  - It's only possible to configure and use one sales order agent per Business Central company.  

## What operational factors and settings allow for effective and responsible use of the feature?

- Access control and permissions

  Like with any other user in Business Central, the sales order agent can be granted access exclusively to the specific parts of the product required to perform its designated tasks. The agent comes with predefined permissions and a user interface (UI) role, also known as a profile, that an administrator or configuring user can assign to the agent. This assignment restricts the agent's access to certain areas of the product. It defines the type of access (for example, whether the agent is only allowed to read specific data or also update or delete it) and determines which UI elements—such as pages, fields, actions, and FactBoxes—it can interact with.  

  We strongly encourage using the permission sets and the profile included with the sales order agent, which can be assigned on the Agent card. This practice ensures that the agent only has access to the functionalities necessary for its role, enhancing both security and efficiency within the system.

- Transparency and notifications

  Business Central users can maintain full transparency and control over the changes made by the sales order agent by using other experiences, which enable them to:

  - Receive notifications on the role center that come from the agent when it requires help or when the process demands human review. For example, review is required for all inbound and outbound messages, approvals, adding missing data, and similar reasons.
  - Get a better understanding of the specific task context and history (“timeline” view), including key steps involved in it.
  - Get a detailed review of each entity created by the agent (for example, a sales quote or sales order that surfaces all changes and suggestions made by the agent within a specific task. This behavior allows humans to review and adjust changes, and then sign out on proceeding with the task.
  - Get an overview of the agent's KPIs (Key Performance Indicators) that summarize the impact of the agent's work. For example, you can get an overview of the number of sales quotes or orders created by the agent and the total amount of these orders.

  Make sure you attend to the notifications raised by the agent to review and approve its work.  
- All actions done by the agent, including creating and modifying records and calling actions, carry the agent's user ID. This user ID appears in the same places and in the same way as with other users, such as in list views, history, posted documents, notifications, and more.  
- Approval workflows can be used to add an extra layer of control to the tasks performed the agent, as they do with other user. You can set up approval workflows to make the agent create a request for approval for a specific change, for example, to mark the quote as released. The change isn't allowed until another user approved the request. Learn more in [Use Approval Workflows](across-how-use-approval-workflows.md).

## Is this capability extensible?

Currently, this capability isn't extensible by partners. 
<!--

Business Central users maintain full transparency and control over the changes made by the sales order agent by: 

- Receiving notifications from the agent, when it requires help, or when the process demands human review (e.g. for all outbound messages).
- Understanding task context and history through a 'timeline' view.
- Reviewing detailed changes and suggestions made by the agent within a task
- Adjusting changes and approving task continuation.
- Getting a detailed review of an entity, surfacing all changes and suggestions made by the agent within a specific task, allowing humans to review and adjust these changes and sign off on proceeding with the task.
- Reviewing the agent's KPIs to assess the impact of its work.-->

## Related information


[!INCLUDE[footer-include](includes/footer-banner.md)]
