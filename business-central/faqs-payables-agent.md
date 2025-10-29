---
title: FAQ for Payables Agent
description: Learn how AI automates purchase invoice creation in Business Central, including setup, capabilities, limitations, and responsible use.
ms.date: 10/29/2025
ms.update-cycle: 180-days
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

These frequently asked questions (FAQ) describe the AI impact of Payables Agent feature in Business Central.

## What is the Payables Agent?

The Payables Agent is an integrated copilot with agent capabilities that automates the task of creating purchase invoices. It starts by receiving a vendor's invoice attached to an email. The agent analyzes the email attachment content, identifies the vendor from the registered list in [!INCLUDE [prod_short](includes/prod_short.md)], and prepares a draft purchase invoice with the requested invoice lines. It also offers the capability to help with vendor creation as part of this process.

The agent is readily available in [!INCLUDE [prod_short](includes/prod_short.md)]; you just need to activate it. You can also configure the agent to suit your business:

- Define the name of the agent.
- Build a list of users who can delegate the process of taking purchase invoices to it. 
- Specify the channel the agent uses to receive invoices, for example, by e-mail, and the steps you want to include or exclude in that process.

After you activate the agent, it's ready to process invoices.

## What are the capabilities of the Payables Agent?

The Payables Agent uses AI to identify and complete tasks based on its instructions and user configuration. The agent acts as a user with access limited to the necessary parts of the product. Learn more about its capabilities in [Payables Agent overview](payables-agent.md).

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

  The agent interacts with the [!INCLUDE [prod_short](includes/prod_short.md)] web client using the logical UI API. The agent can:
  
  - Read data displayed on product pages.
  - Access properties of UI elements, such as names, descriptions, fields, actions, and tooltips.
  - Combine this data with user-provided instructions and email data.
  - Use AI and business knowledge to orchestrate the steps needed to complete each task.

- Integration with other services

  The agent uses Azure Document Intelligence to analyze email attachments with Optical Character Recognition (OCR). It matches vendor invoice lines to accounts or items by using mapping tables, historical data, and an LLM that matches line descriptions to G/L account names from the customer's database.

- Human intervention and transparency

  The agent asks you to take action in specific situations, like when it can't find a matching vendor or G/L account, or when you need to approve a business decision. It shows notifications in the role center to let you know when your attention is needed.

  For each task, you can view a detailed timeline that shows key steps taken by the agent and by people, including when you receive the initial email. You can review and update the agent’s suggested values and actions as needed.

## What is the intended use of the Payables Agent?

The Payables Agent handles the entire purchase invoice extraction and processing. It takes the vendor's invoice attached in an email, analyzes the data in the attachment, prepares a purchase document draft, and converts the draft to a purchase invoice.

## How was the Payables Agent evaluated? What metrics are used to measure performance?

The Payables Agent was tested for accuracy and safety.

- Accuracy was tested using 150 test cases with unique PDF invoices that exhibit varying degrees of completeness and complexity.
- Safety was tested using 240 test cases that covered categories such as cross-domain prompt injection attacks (XPIA), self-harm, sexual, and violence.

## What are the limitations of the Payables Agent? How can users minimize the impact of the Payables Agent’s limitations when using the system?

### Languages

- [!INCLUDE[copilot-language-support-en-only](includes/copilot-language-support-en-only.md)].
- Due to limited language support, the system isn't initially available to Canadian customers because regulatory language compliance mandates support for both English and French.

### Email

- The agent reads inbound email from a shared inbox on Microsoft Exchange. Learn more in [Set up email](admin-how-setup-email.md). The agent doesn't support other ways to receive email.
- The agent doesn't process the email body&mdash;it processes only attachments.
- The agent processes only PDF attachments up to 5 MB.
- The agent processes only PDF attachments up to 10 pages.
- The agent processes only email messages with up to 10 PDF attachments.
- The agent processes a maximum 100 email messages every 24 hours in a single mailbox.
- The agent processes a maximum 500 PDF attachments every 24 hours in a single mailbox.
- Email messages that the agent generates might contain incorrect information. The agent asks a human user to review and edit every outbound message if necessary.

### Entities and data the agent works with

- The agent only creates purchase document drafts and purchase invoices. It can't create or work with other purchase documents like purchase orders or purchase credit memos, or documents in other areas of the product like sales or service orders.
- The agent doesn't create new items, contacts, or G/L accounts. It only works with entities already registered in Business Central. However, the agent can be instructed to create new vendors in cases where the vendor of a received invoice is unknown or unmatched.
- The agent doesn't post any documents.

### Additional limitations

- If the agent stops working, it notifies the users in the same place that it normally notifies users when it needs approval to process an email. For example, the agent stops if it loses access to the shared mailbox or calls to the LLM (large language models) are failing.
- When calling an LLM to match invoice lines with G/L Accounts, the agent matches only with G/L Accounts that allow direct posting and that are of type "Income Statement".
- When the agent calls an LLM to match invoice lines with G/L Accounts, it first checks the list of income statement G/L Accounts that allow direct posting. If this list exceeds the limit of 20,000 AI tokens (a limit that customers can't currently configure), the agent doesn't call the LLM. Instead, it notifies users in the same place where it normally notifies them when approval is needed to process an email.
- Delegated administrators can't activate the agent.
- It's only possible to configure and use one Payables Agent per company in [!INCLUDE [prod_short](includes/prod_short.md)].

## What operational factors and settings allow for effective and responsible use of the Payables Agent?

- Access control and permissions

  Like any other user in [!INCLUDE [prod_short](includes/prod_short.md)], the Payables Agent can be granted access exclusively to the specific parts of the product required to perform its designated tasks. The agent comes with predefined permissions and a user interface (UI) role, also known as a profile, that an administrator or configuring user can assign to the agent. This assignment restricts the agent's access to certain areas of the product. It defines the type of access (for example, whether the agent is only allowed to read specific data or also update or delete it) and determines which UI elements—such as pages, fields, actions, and FactBoxes—it can interact with.  

  We strongly encourage using the permission sets and the profile included with the Payables Agent, which can be assigned on the Agent card. This practice ensures that the agent only has access to the functionalities necessary for its role, enhancing both security and efficiency within the system.

  Learn more in [Set up Payables Agent](payables-agent-setup.md).

- Transparency and notifications

  You can maintain full transparency and control over the changes made by the Payables Agent by using other experiences that enable them to:

  - Receive notifications on the role center that come from the agent when it requires help or when the process demands human review. For example, review is required for all inbound and outbound messages, approvals, adding missing data, and similar reasons.
  - Get a better understanding of the specific task context and history ("timeline" view), including key steps involved in it.
  - Get a detailed review of each entity created by the agent (for example, a sales quote or sales order that surfaces all changes and suggestions made by the agent within a specific task). This behavior allows humans to review and adjust changes, and then sign out on proceeding with the task.
  - Get an overview of the agent's KPIs (Key Performance Indicators) that summarize the impact of the agent's work. For example, you can get an overview of the number of sales quotes or orders created by the agent and the total number of these orders.

    Make sure you attend to the notifications raised by the agent to review and approve its work.  
- All actions done by the agent, including creating and modifying records and calling actions, carry the agent's user ID. This user ID appears in the same places and in the same way as it does with other users, such as in list views, history, posted documents, notifications, and more.  
- Approval workflows can be used to add an extra layer of control to the tasks done by the agent, as they do with other users. You can set up approval workflows to make the agent create a request for approval for a specific change, for example, to mark the quote as released. The change isn't allowed until another user approves the request. Learn more in [Use Approval Workflows](across-how-use-approval-workflows.md).

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## Is this capability extensible?

No. Microsoft creates and maintains the Payables Agent, and its code isn't extensible by other solutions or plugins.

## Related information

[Payables Agent overview](payables-agent.md)  
[Set up Payables Agent](payables-agent-setup.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  