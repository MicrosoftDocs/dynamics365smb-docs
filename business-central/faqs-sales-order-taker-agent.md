---
title: FAQ for Sales Order Agent
description: This FAQ provides information about the AI technology used by Sales Order Agent in Business Central. It provides key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.custom: 
  - responsible-ai-faqs
ms.topic: faq
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
---
# FAQ for Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of the Sales Order Agent feature in Business Central.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->

## What is Sales Order Agent?

Sales Order Agent is an integrated AI agent that automates the task of handling requests for sales quotes and sales orders from customers. The agent can manage the entire sales order capturing process, from receiving a customer's order by email, locating the customer among the registered customers in Business Central, checking item availability, preparing a quote with the requested items, following up with the customer on any changes needed to finalize the quote, receiving quote approval, and converting it to a sales order.

Learn more in [Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md).

## What are the capabilities of Sales Order Agent?

The agent supports handling requests for sales quotes and sales orders from customers with the following capabilities:

- Agent configuration

  The agent is available directly within Business Central. You can configure and activate the agent to help your team or organization improve the sales process. For example, you can specify the users who can participate in the process of reviewing and approving the sales documents created by the agent. You can also specify the mailbox for receiving the customer requests and settings for searching your items and involving the users to review the agent's work.

  Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md).

- Task execution and interaction

  The agent operates based on its instructions and user configuration. The instructions describe its purpose, tasks, and high-level considerations for how to perform the flow. These instructions are defined in the agent code and aren't visible to users. The agent uses AI to identify and carry out the steps needed to complete its task within the Business Central environment. Learn more in [Sales Order Agent overview](sales-order-agent.md).

  The agent is invoked by a built-in email dispatcher that runs as a scheduled task and monitors the company mailbox specified in the agent's configuration. The dispatcher hands over emails received from the customers to Sales Order Agent and sends results of the agent's work, such as prepared sales quote with requested items, in response.
  
- Access and permissions

  The agent runs as its own user in Business Central and is granted access only to the necessary parts of the product. It comes with a predefined permission set and UI role (profile) that limits the parts of the product and UI elements (such as pages, fields, and actions) it can access.

- Transparency and change control

  The agent seeks user intervention in specific situations, such as preparing outbound communications or providing business review and approval for key operations.

  Business Central maintains full transparency and provides control over changes made by the agent. The agent brings humans in the loop when their attention is required by issuing in-product notifications that are displayed on the role center. For example, a notification occurs before any outbound email communications to a customer, when the agent needs more details to get unblocked, or when approval is needed for important changes.  

  For each task performed by the agent, users get a detailed timeline that shows the key steps taken by the agent and human users, including the email conversation. Users can review this information and update the values and actions the agent suggested if needed. Business Central can also display the reasoning used by the agent and citations that led to a suggested value.

## What is the intended use of Sales Order Agent?

Sales Order Agent is intended to handle the end-to-end sales order capturing process. This process includes:

- Taking the customer’s order by email.
- Iterating on the details with the customer via email.
- Checking the availability of the items.
- Preparing the sales quote with the requested items.
- Sending the quote to the customer for approval.
- Converting the quote to a sales order upon receiving customer confirmation.

## How was Sales Order Agent evaluated? What metrics are used to measure performance?

We defined a set of categories and scenarios and created test cases for each as described in the following table. In total, we have a suite of 50 test cases.

|Category|Scenario|
|-|-|
|Quotes<br><br>Precise request for a quote with variations (delivery dates or not, terse/verbose request, complete or incomplete email signature) |<ul><li>Single/multi-turn with approval by customer. Up to three items.</li><li>Quote request for four or more items.</li><li>Request for quote by item reference. Up to three lines.</li><li>Quote sent but not approved by customer.</li><li>Quote request from unknown customer.</li><li>Quote request for unknown item.</li></ul>|
|Information<br><br>Requests for information about items followed by a quote request|<ul><li>Single and multi-turn with quote based on information.</li><li>Request for information about unknown items.</li></ul>|

## What are the limitations of Sales Order Agent? How can users minimize the impact of the Sales Order Agent limitations when using the system?

- Languages

  - [!INCLUDE[soa-language-support](includes/soa-language-support.md)]
  - Mixed language input might result in lower-quality output because the system relies on pure string similarity, and the semantic part of the matching might not work properly.

- Emailing

  - The agent reads inbound emails via a shared inbox on Microsoft Exchange. Learn more in [Set up email](admin-how-setup-email.md). Other ways to receive email aren't supported.
  - The agent only uses the email body to get the details of the request; it doesn't process files attached to emails.  
  - Large emails might exceed the number of tokens that can be processed in one request. This condition leads the agent to trigger a request for a human to investigate (similar to how a human is requested to approve whether the agent approves an email). 
  - Email messages generated by the agent might contain incorrect information. The agent is designed to ask a human to review and edit every outbound message if necessary.  

- Entities and data the agent can work with

  - The agent is designed to work with sales quotes and sales orders. It can't create or work with other sales documents (such as blank orders, invoices, or credit memos) or documents in other areas of the product (such as purchase or service orders).
  - The agent doesn't create new items, contacts, or customers. It only works with the entities that are already registered in Business Central. The agent is designed to ask a human user to provide additional information or perform the task manually, when it can't find this data in Business Central.
  - The agent doesn't post documents.
  - Based on more customer requests, the agent can make changes to the sales quotes, but not to the sales orders.
  - The agent is designed to work with sales lines of type "Item"; other sales line types, such as Resource, Charge (Item), Allocation Account, and Fixed Asset, aren't supported.
  - At this stage, the agent supports the creation of up to 15 item lines per sales document. Increasing the number of lines might result in lower-quality output.
  - How you name your products can affect agent output. For example, using cryptic abbreviations versus friendly names can reduce output quality.

- When adding items to a sales document, the use of the item's **Variant Code** isn't currently supported. It leaves the **Variant Code** field empty.

- Pricing and discount requests

   Business Central has an advanced price/discount calculation logic, often extended by ISV solutions. Therefore, the most reliable way to get the item price is to create a sales document—for example, a quote. For this reason, the agent is designed *not* to provide or update any pricing and discount information by email. Prices and default discounts are calculated by Business Central's own business logic and included with a sales quote document. Requests for changing discounts and pricing aren't accepted by the agent. Instead, they're surfaced to the users for applying them manually. 

- Other considerations

  - Delegated administrators can't activate the agent.  
  - It's only possible to configure and use one Sales Order Agent per Business Central company.
  - The agent uses the regional settings specified by its user account.
  - While the agent can recognize and interact with the custom fields and actions introduced by customizations and ISV solutions, which are added to the agent's profile and permissions, the results might vary in quality and should be thoroughly tested. Improving reliability of working with the custom elements might require adjustments to the agent's instructions, which is currently not supported. 
  
## What operational factors and settings allow for effective and responsible use of the feature?

- Access control and permissions

  Sales Order Agent can be granted access exclusively to specific parts of the product required to perform its designated tasks. The agent comes with predefined permissions and a user interface (UI) role, also known as a profile, that an administrator or configuring user can assign to the agent. This assignment restricts the agent's access to certain areas of the product. It defines the type of access (for example, whether the agent is only allowed to read specific data or also update or delete it) and determines which UI elements—such as pages, fields, actions, and FactBoxes—it can interact with.  

  We strongly encourage using the permission sets and the profile included with the Sales Order Agent, which can be assigned on the Agent card. This practice ensures that the agent only has access to the functionalities necessary for its role, enhancing both security and efficiency within the system.

  Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md).

- Transparency and notifications

  Business Central users can maintain full transparency and control over the changes made by Sales Order Agent by using other experiences that enable them to:

  - Receive notifications on the role center that come from the agent when it requires help or when the process demands human review. For example, review is required for all inbound and outbound messages, approvals, adding missing data, and similar reasons.
  - Get a better understanding of the specific task context and history (“timeline” view), including key steps involved in it.
  - Get a detailed review of each entity created by the agent (for example, a sales quote or sales order that surfaces all changes and suggestions made by the agent within a specific task. This behavior allows humans to review and adjust changes, and then sign out on proceeding with the task.
  - Get an overview of the agent's key performance indicators (KPIs) that summarize the impact of the agent's work. For example, you can get an overview of the number of sales quotes or orders created by the agent and the total number of these orders.

    Make sure you attend to the notifications raised by the agent to review and approve its work.  
- All actions done by the agent, including creating and modifying records and calling actions, carry the agent's user ID. This user ID appears in the same places and in the same way as it does with other users, such as in list views, history, posted documents, notifications, and more.  
- Approval workflows can be used to add an extra layer of control to the tasks done by the agent, as they do with other users. You can set up approval workflows to make the agent create a request for approval for a specific change—for example, to mark the quote as released. The change isn't allowed until another user approves the request. Learn more in [Use Approval Workflows](across-how-use-approval-workflows.md).

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## Is this capability extensible?

Currently, this capability isn't extensible by partners.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)  
[Configure Copilot and agent capabilities](enable-ai.md) 

[!INCLUDE[footer-include](includes/footer-banner.md)]
