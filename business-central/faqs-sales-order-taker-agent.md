---
title: FAQ for Sales Order Agent
description: This FAQ provides information about the AI technology used by Sales Order Agent in Business Central. It provides key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 11/19/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
---
# FAQ for Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of Sales Order Agent feature in Business Central.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is the Sales Order Agent?

The Sales Order Agent is an integrated copilot with agent capabilities that automates the task of taking sales orders. The agent can handle the entire sales order capturing process. It starts by receiving a customer's order by email. It then identifies the customer from the registered list in Business Central, prepares a quote with the requested items, checks availability of items, sends the quote to the customer for approval, and upon confirmation, converts it to  sales order.

The agent is available in the product and ready to use after activation. It's configurable, allowing you to:

- Define users who can delegate the sales order process.
- Specify the order receiving channel, for example, email
- Select the steps to include or exclude.

Once you activate the agent, it's ready to process sales orders.  

## What are capabilities of the Sales Order Agent?

The agent supports taking and processing sales orders with the following capabilities:

- Operational instructions and configuration

  The agent operates based on its instructions and user configuration. It uses AI to identify and carry out the steps needed to complete this task within the Business Central environment.

  The agent has its own set of high-level business instructions that describe its purpose, tasks, and considerations. These instructions are defined in the agent code and aren't visible to users.
  
  The agent is also configurable. For example, you can specify: the users who can delegate the process of taking the sales orders, the channels for receiving the orders (for example, by email), and the steps to include or exclude in the process.

- Task execution and interaction

  To execute its tasks, the Sales Order Agent interacts with the Business Central web client using a logical representation of the UI called the logical UI API.  

  Through the logical UI API, the agent can read data displayed on the product pages and access properties of the UI elements, such as page names/descriptions, fields, actions, and tooltips. It can then combine that data with the user-provided instructions from the agent configuration and the data received via e-mail messages. The agent then uses AI and conventional business knowledge to orchestrate the necessary steps to complete each step and the overall task.

  The agent tries to overcome errors and adapt to changing conditions, like when another user enters new data on a page. It can also engage in multi-turn email conversations with customers to clarify or confirm requirements.

- Access and permissions

  The agent runs as its own user in Business Central and is granted access only to the necessary parts of the product. It comes with a predefined permission set and UI role (profile) that limits the parts of the product and UI elements (such as pages, fields, actions) it can access.

- User intervention and notification

  The agent seeks user intervention in specific situations, such as preparing outbound communications or providing business approval for key operations.

  The agent is invoked by a built-in e-mail dispatcher that runs as a scheduled task and monitors the company mailbox specified in the agent's configuration. The dispatcher hands over e-mails received from the customers to the Sales Order Agent and sends results of the agent's work, such as prepared sales quote with requested items, in response.

- Transparency and change control

  Business Central maintains full transparency and provides control over changes made by the agent. The agent brings humans in the loop when their attention is required by issuing in-product notifications that are displayed on the role center. For example, a notification happens before any outbound e-mail communications, such as sending a final sales quote or an order to a customer, when the agent needs more details to get unblocked, or when approval for important changes.  

  For each task performed by the agent, users get a detailed timeline that shows the key steps taken by the agent and human users, including the e-mail conversation. Users can review this information and update the values and actions the agent suggested if needed. Business Central can also display the reasoning used by the agent and citations that led to a suggested value.

## What is the intended use of the Sales Order Agent?

The Sales Order Agent is intended to handle the end-to-end sales order capturing process. This process includes:

- Taking the customer’s order by e-mail
- Iterating on the details with the customer via e-mail
- Preparing the sales quote with the requested items
- Checking the availability of the items
- Sending the quote to the customer for approval
- Converting the quote to a sales order upon receiving customer confirmation.

## How was the Sales Order Agent evaluated? What metrics are used to measure performance?

We defined a set of categories and scenarios and created test cases for each as described in the following table. In total, we have a suite of 50 test cases.

|Category|Scenario|
|-|-|
|Quotes<br><br>Precise request for a quote with variations (delivery dates or not, terse/verbose request, complete or incomplete email signature) |<ul><li>Single/multi-turn with approval by customer. Up to three items.</li><li>Quote request with four or more items</li><li>Request for quote by item reference. Up to three lines.</li><li>Quote sent but not approved by customer</li><li>Quote request from unknown customer.</li><li>Quote request for unknown item.</li></ul>|
|Information<br><br>Requests for information about items followed by a quote request|<ul><li>Single and multi-turn with quote based on information</li><li>Request for information about unknown items</li></ul>|

## What are the limitations of Sales Order Agent? How can users minimize the impact of the Sales Order Agent limitations when using the system?

- Languages

  - The system was tested with the content (emails and product localization) provided in US English. 
  - Mixed language input might result in lower-quality output because the system relies on pure string similarity, and the semantic part of the matching might not work properly.
  - Due to limited language support, the system isn't initially available to Canadian customers because regulatory language compliance mandates support for both English and French.

- E-mailing

  - The agent reads inbound emails via a shared inbox on Microsoft Exchange. Learn more in [Set up email](admin-how-setup-email.md). Other ways to receive email aren't supported.
  - The agent doesn't read files attached to emails.  
  - Large emails might exceed the number of tokens that can be processed in one request. This condition leads the agent to trigger a request for a human to investigate (similar to how a human is requested to approve whether the agent approves an email). 
  - E-mail messages generated by the agent might contain incorrect information. The agent is designed to ask a human user to review and edit every outbound message if necessary.  

- Entities and data the agent can work with

  - The agent can only create sales quote and sales order documents. It can't create or work with the other sales documents (such as blank orders, invoices, or credit memos) or documents in other areas of the product (such as purchase or service orders).
  - The agent doesn't create new items, contacts, or customers. It only works with the entities that are already registered in Business Central.  
  - Posting of documents isn't supported.

- **Variant Code** isn't currently supported
  
    If you can ship a product in two different colors, for example, the agent finds the product but leaves the **Variant Code** field empty. You need to fill in the field manually.

    How you name your products can affect output. For example, using cryptic abbreviations versus friendly names can reduce output quality.

    For products, the following table lists the tables and fields that Agent searches.

    |Table|Fields|
    |-|-|
    |Items|No.<br>Description<br>Description 2<br>Search Description<br>GTIN<br>Vendor Item Number|
    |Item Variant|Code<br>Description<br>Description 2|
    |Item Reference|Reference No.<br>Description<br>Description 2|
    |Item Attributes|Name<br>Value|
    |Item Category| Code<br>Description<br>Parent Category - 1 Level|
    |Item Translation|Language<br>Description<br>Description 2|
    |Item Identifier|Code|
    |Extended text Line|Text|

- Finding products

  Although the agent can find products based on vague, incomplete, or inaccurate descriptions, its effectiveness is influenced by the quality of product information in Business Central. You can improve the agent's ability to find products by enhancing descriptions, attributes, categories, and extended text.

- Pricing

  <!-- needs clarification-->Because Business Central has advanced, and often adjusted, price/discount calculation logic, the most reliable way to get price is to create sales document, for example quote. This is exactly what agent tries to do.

- Other limitations

  - If the agent stops working, it notifies the users in the same place that it normally notifies users when it needs approval to process an email. Examples are if the agent loses access to the shared mailbox or calls to the LLM (large language models) are failing.
  - Delegated administrators can't activate the agent.  
  - It's only possible to configure and use one Sales Order Agent per Business Central company.

## What operational factors and settings allow for effective and responsible use of the feature?

- Access control and permissions

  Like with any other user in Business Central, the Sales Order Agent can be granted access exclusively to the specific parts of the product required to perform its designated tasks. The agent comes with predefined permissions and a user interface (UI) role, also known as a profile, that an administrator or configuring user can assign to the agent. This assignment restricts the agent's access to certain areas of the product. It defines the type of access (for example, whether the agent is only allowed to read specific data or also update or delete it) and determines which UI elements—such as pages, fields, actions, and FactBoxes—it can interact with.  

  We strongly encourage using the permission sets and the profile included with the Sales Order Agent, which can be assigned on the Agent card. This practice ensures that the agent only has access to the functionalities necessary for its role, enhancing both security and efficiency within the system.

- Transparency and notifications

  Business Central users can maintain full transparency and control over the changes made by the Sales Order Agent by using other experiences, which enable them to:

  - Receive notifications on the role center that come from the agent when it requires help or when the process demands human review. For example, review is required for all inbound and outbound messages, approvals, adding missing data, and similar reasons.
  - Get a better understanding of the specific task context and history (“timeline” view), including key steps involved in it.
  - Get a detailed review of each entity created by the agent (for example, a sales quote or sales order that surfaces all changes and suggestions made by the agent within a specific task. This behavior allows humans to review and adjust changes, and then sign out on proceeding with the task.
  - Get an overview of the agent's KPIs (Key Performance Indicators) that summarize the impact of the agent's work. For example, you can get an overview of the number of sales quotes or orders created by the agent and the total amount of these orders.

  Make sure you attend to the notifications raised by the agent to review and approve its work.  
- All actions done by the agent, including creating and modifying records and calling actions, carry the agent's user ID. This user ID appears in the same places and in the same way as with other users, such as in list views, history, posted documents, notifications, and more.  
- Approval workflows can be used to add an extra layer of control to the tasks performed the agent, as they do with other user. You can set up approval workflows to make the agent create a request for approval for a specific change, for example, to mark the quote as released. The change isn't allowed until another user approved the request. Learn more in [Use Approval Workflows](across-how-use-approval-workflows.md).

## Is this capability extensible?

Currently, this capability isn't extensible by partners.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)  
[Configure Copilot and AI capabilities](enable-ai.md) 

[!INCLUDE[footer-include](includes/footer-banner.md)]
