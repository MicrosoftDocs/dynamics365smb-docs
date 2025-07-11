---
title: FAQ for Payables Agent
description: Learn how AI automates purchase invoice creation in Business Central, including setup, capabilities, limitations, and responsible use.
ms.date: 06/04/2025
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
---
# FAQ for Payables Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of Payables Agent feature in Business Central.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->

## What is the Payables Agent? 

The Payables Agent is an integrated copilot with agent capabilities that automates the task of creating purchase invoices. It starts by receiving a vendor's invoice attached to an e-mail. The agent analyzes the email attachment content, identifies the vendor from the registered list in Business Central, and prepares a draft purchase invoice with the requested invoice lines. It also offers the capability to help with vendor creation as part of this process. 

The agent is readily available in the Business Central; you just need to activate it. The agent is also configurable, allowing you to define the name of the agent, a list of other users who can delegate the process of taking the purchase invoices to it, the channel for receiving the invoices (for example, by e-mail), and the steps you want to include or exclude in that process. Once the agent is activated, it's ready to process invoices.

## What are the capabilities of the Payables Agent?

The Payables Agent operates in Business Central using AI to identify and complete tasks based on its instructions and user configuration. The agent acts as a user with access limited to the necessary parts of the product. Learn more about its capabilities in [Payables Agent overview](payables-agent.md).

- Agent instructions

  The agent gets high-level business instructions that define its purpose, outline the tasks it performs, and specify more considerations. These instructions are set in the agent code and aren't visible to users.

- Configuration

  When you set up the Payables Agent, you can:
  
  - Define which users delegate tasks to the agent.
  - Set channels for receiving orders, like email.
  - Select which steps of the order-taking process to include or exclude, like converting a purchase document draft into a purchase invoice.
  - Assign predefined permissions and a UI role (profile) to control which parts of the product and UI elements the agent can access.

- Task execution and interaction

  A built-in email dispatcher runs as a scheduled task and monitors the company mailbox specified in the agent’s configuration. The dispatcher forwards email attachments from vendors to the Payables Agent, which prepares a draft purchase invoice based on the attachment data.

  The agent interacts with the Business Central web client using the logical UI API. The agent can:
  
  - Read data displayed on product pages.
  - Access properties of UI elements, such as names, descriptions, fields, actions, and tooltips.
  - Combine this data with user-provided instructions and email data.
  - Use AI and business knowledge to orchestrate the steps needed to complete each task.

- Integration with other services

  The agent uses Azure Document Intelligence to analyze email attachments with Optical Character Recognition (OCR). It matches vendor invoice lines to accounts or items by using mapping tables, historical data, and an LLM that matches line descriptions to G/L account names from the customer's database.

- Human intervention and transparency

  The agent asks you to take action in specific situations, like when it can't find a matching vendor or G/L account, or when you need to approve a business decision. It shows notifications in the role center to let you know when your attention is needed.

  For each task, you can view a detailed timeline that shows key steps taken by the agent and by people, including when you receive the initial email. You can review and update the agent’s suggested values and actions as needed.

<!--
The agent operates based on its instructions and user configuration. It uses AI to identify and carry out the steps needed to complete this task within the Business Central environment. The agent is provided with its own set of high-level business instructions, which describe its purpose, outline the task it needs to perform, and additional considerations it needs to take when performing the steps. These instructions are defined in the agent code and are not visible to the users. When configuring the Payables Agent, users can define the list of other users who can delegate their tasks to the agent, channels for receiving orders (for example, email), and select which steps of the order taking process should be included or excluded (for example, whether to convert generated purchase document draft into a purchase invoice). To execute its tasks, the payables agent interacts with the Business Central web client using a logical representation of the UI called the logical UI API. Through that logical UI API, the agent can read the data displayed on the product pages and access properties of the UI elements (for example, names and descriptions of the pages, fields, actions, and tooltips). It can then combine that data with the instructions provided by the users during agent configuration, along with data received via e-mail messages, and then use AI with its conventional business knowledge to orchestrate the steps needed to complete each step and the overall task. The agent integrates with Azure Document Intelligence for performing OCR analysis on the source e-mail attachment, and for matching vendor’s invoice lines with accounts or items it uses both mapping tables and historical data from the customer’s database and integrates with an LLM to match the line descriptions with names of G/L accounts from the customer’s database. 

The agent runs as just another user in Business Central and is granted access solely to the necessary parts of the product to perform its task. It comes with predefined permissions and a UI role (profile) that can be assigned to it by the configuring user, limiting which parts of the product the agent can access and which UI elements (pages, fields, actions and FactBoxes) it can interact with. The agent will seek user intervention when specific situations arise, for instance, when a matching vendor or G/L account can’t be found or when providing business approval for key operations is necessary.  

The agent is invoked by a built-in e-mail dispatcher, running as a scheduled task, which monitors the company mailbox that’s specified in the agent’s configuration settings. The dispatcher hands over e-mail attachments received from the vendors to the Payables Agent. The Payables Agent prepares a draft for the purchase invoice based on the data in the attachment. Business Central maintains full transparency and provides control over changes made by the agent.

The agent brings humans in the loop when their attention is required by issuing in-product notifications that are displayed on the role center. This happens when the agent needs users to provide some missing details to get unblocked, or to provide business approval for important changes. For each task performed by the agent, users get a detailed timeline that shows the key steps taken by the agent and human users, including the receiving of the initial e-mail. Users can review this information and update the values and actions the agent suggested if needed.-->

## What is the intended use of the Payables Agent?

The Payables Agent handles the entire purchase invoice extraction and processing. It takes the vendor's invoice attached in an email, analyzes the data in the attachment, prepares a purchase document draft, and converts the draft to a purchase invoice.

## How was the Payables Agent evaluated? What metrics are used to measure performance?

The Payables Agent was tested for accuracy and safety.

- Accuracy was tested using 150 test cases with unique PDF invoices that exhibit varying degrees of completeness and complexity.
- Safety was tested using 240 test cases that covered categories such as cross-domain prompt injection attacks (XPIA), self-harm, sexual, and violence.

## What are the limitations of the payables agent? How can users minimize the impact of payables agent’s limitations when using the system?

### Languages

- [!INCLUDE[copilot-language-support-en-only](includes/copilot-language-support-en-only.md)].
- Due to limited language support, the system isn't initially available to Canadian customers because regulatory language compliance mandates support for both English and French.

### Email

- The agent reads inbound email from a shared inbox on Microsoft Exchange. Learn more in [Set up email](admin-how-setup-email.md). The agent doesn't support other ways to receive email.
- The agent doesn't process the email body&mdash;it processes only attachments.
- The agent processes only PDF attachments up to 5 MB.
- The agent processes only PDF attachments up to 10 pages. This limitation might be enforced only from public preview onward.
- Email messages generated by the agent might contain incorrect information. The agent asks a human user to review and edit every outbound message if necessary.

### Entities and data the agent works with

- The agent only creates purchase document drafts and purchase invoices. It can't create or work with other purchase documents like purchase orders or purchase credit memos, or documents in other areas of the product like sales or service orders.
- The agent doesn't create new items, contacts, or G/L accounts. It only works with entities already registered in Business Central. However, the agent can be instructed to create new vendors in cases where the vendor of a received invoice is unknown or unmatched.
- The agent doesn't post any documents.

### Additional limitations

- If the agent stops working, it notifies the users in the same place that it normally notifies users when it needs approval to process an email. For example, the agent stops if it loses access to the shared mailbox or calls to the LLM (large language models) are failing.
- When calling an LLM to match invoice lines with G/L Accounts, payables agent matches only with G/L Accounts that allow direct posting and that are of type "Income Statement".
- When the agent calls an LLM to match invoice lines with G/L Accounts, it first checks the list of income statement G/L Accounts that allow direct posting. If this list exceeds the limit of 20,000 AI tokens (a limit that customers can't currently configure), the agent doesn't call the LLM. Instead, it notifies users in the same place where it normally notifies them when approval is needed to process an email.
- Delegated administrators can't activate the agent.
- It's only possible to configure and use one payables agent per Business Central company.

## What operational factors and settings allow for effective and responsible use of payables agent?

<!--Like any other user in Business Central, the Payables Agent can be granted access exclusively to the specific parts of the product required to perform its designated tasks. The agent comes with predefined permissions and a user interface (UI) role, also known as a profile, that can be assigned to the agent by the configuring user or administrator. This assignment restricts the agent's access to certain areas of the product. It defines the type of access (for example, whether the agent is only allowed to read specific data or also update or delete it) and determines which UI elements—such as pages, fields, actions, and FactBoxes—it can interact with.

We strongly encourage using the permission sets and the profile included with the payables agent, which can be assigned on the Agent card. This ensures that the agent only has access to the functionalities necessary for its role, enhancing both security and efficiency within the system.

Business Central users can maintain full transparency and control over the changes made by the payables agent by using additional experiences, which enable them to:

- Receive notifications on the role center that come from the agent when it requires help, or when the process demands human review (for example, for all inbound messages, approvals, adding missing data and similar reasons).
- Get a better understanding of the specific task context and history (“timeline” view), including key steps involved in it.
- Get a detailed review of each entity created by the agent (for example, a purchase document draft or a purchase invoice that surfaces all changes and suggestions made by the agent within a specific task. This allows humans to review and adjust changes and then sign off on proceeding with the task.
- Get an overview of the agents’ KPIs (Key Performance Indicators) that summarize the impact of the agent's work, for example, the number of purchase document drafts or purchase invoices created by the agent.

Make sure you attend to the notifications raised by the agent to review and approve its work.

All actions done by the agent, including creating and modifying records and calling actions, carry the agent’s user ID. This user ID appears in the same places and in the same way as with other users, such as in list views, history, posted documents, notifications, and more.


Additionally, in Business Central, you can set up and use approval workflows to add an extra layer of control to the tasks performed by different users, including agents. Approval workflows can be set up to make the agent create a request for approval for a specific change (for example, to mark the quote as released), and the change isn’t allowed until the request is approved by another user. Learn more in [Use Approval Workflows](across-use-workflows.md).-->

- Access control and permissions

  Like any other user in Business Central, the Sales Order Agent can be granted access exclusively to the specific parts of the product required to perform its designated tasks. The agent comes with predefined permissions and a user interface (UI) role, also known as a profile, that an administrator or configuring user can assign to the agent. This assignment restricts the agent's access to certain areas of the product. It defines the type of access (for example, whether the agent is only allowed to read specific data or also update or delete it) and determines which UI elements—such as pages, fields, actions, and FactBoxes—it can interact with.  

  We strongly encourage using the permission sets and the profile included with the Sales Order Agent, which can be assigned on the Agent card. This practice ensures that the agent only has access to the functionalities necessary for its role, enhancing both security and efficiency within the system.

  Learn more in [Set up Payables Agent](payables-agent-setup.md).

- Transparency and notifications

  Business Central users can maintain full transparency and control over the changes made by the Sales Order Agent by using other experiences that enable them to:

  - Receive notifications on the role center that come from the agent when it requires help or when the process demands human review. For example, review is required for all inbound and outbound messages, approvals, adding missing data, and similar reasons.
  - Get a better understanding of the specific task context and history ("timeline" view), including key steps involved in it.
  - Get a detailed review of each entity created by the agent (for example, a sales quote or sales order that surfaces all changes and suggestions made by the agent within a specific task. This behavior allows humans to review and adjust changes, and then sign out on proceeding with the task.
  - Get an overview of the agent's KPIs (Key Performance Indicators) that summarize the impact of the agent's work. For example, you can get an overview of the number of sales quotes or orders created by the agent and the total number of these orders.

    Make sure you attend to the notifications raised by the agent to review and approve its work.  
- All actions done by the agent, including creating and modifying records and calling actions, carry the agent's user ID. This user ID appears in the same places and in the same way as it does with other users, such as in list views, history, posted documents, notifications, and more.  
- Approval workflows can be used to add an extra layer of control to the tasks done by the agent, as they do with other users. You can set up approval workflows to make the agent create a request for approval for a specific change, for example, to mark the quote as released. The change isn't allowed until another user approves the request. Learn more in [Use Approval Workflows](across-how-use-approval-workflows.md).

## Is this capability extensible?

No. Microsoft creates and maintains the Payables Agent, and its code isn't extensible by other solutions or plugins.

## Related information

[Payables Agent overview](payables-agent.md)  
[Set up Payables Agent](payables-agent-setup.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  