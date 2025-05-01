---
title: Payables Agent overview (preview)
description: Learn about the Payables Agent in Business Central.
ms.date: 07/01/2025
ms.topic: overview
author: dmc-dk
ms.author: soalex
ms.reviewer: jswymer
ms.collection:
  - bap-ai-copilot
ms.search.form: 4400, 4410
---
# Payables Agent overview (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The Payables Agent helps Business Central users automate the processing of vendor invoices. The agent monitors mailboxes and SharePoint- and OneDrive folders for incoming vendor invoices and uses AI to analyze the content of the invoices. It speeds up registration and processing of invoices by interpreting the invoice content and presents it to users in a draft. In doing so, the Payables Agent suggests line and header information according to what the company has done previously and assisted by AI interpretation of what the best way to register the invoice details. Ideally, users will have to do very few or no corrections to the suggested invoice information before they finalize the draft and it becomes a real purchase invoice, ready for approval and posting.

> [!TIP]
> Watch a short video in the Dynamics Business Central channel on YouTube at [Get started with the Sales Order Agent for Dynamics 365 Business Central](https://www.youtube.com/watch?v=6icbmbLc_Og).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->
## Functionality

### Activation and configuration

The agent is readily available in the product. To activate it, you specify the email inbox and/or the SharePoint folder you want the agent to monitor. Additionally, specify your preferences for certain aspects of the agent's behavior and designate the users authorized to use the agent to process vendor invoices, enabling the agent to act on behalf of a company, department, or team&mdash;not just an individual user.

### Permissions and profiles

The agent operates within the permissions and profile (role) assigned to it by the administrator. Permissions define which areas of the product (tables) the agent has access to. The profile outlines the UX elements (pages and actions) the agent can engage with during its work. Default permissions and the profile are assigned to the agent out of the box; however, administrators can update these permissions as needed.

### Operation

The Payables Agent is designed to run autonomously in the background, using AI to perform its tasks while keeping users informed about key steps and involving them when necessary. Involvement might be needed in specific scenarios, for instance to review suggested vendor invoice drafts, based on configured preferences.

Conceptually, the agent interacts with Business Central functionality in a manner similar to how Business Central users interact with it. The agent is provided with general instructions, expressed in natural language, outlining how the process of vendor invoices should be handled. It then uses UI metadata, such as captions, tooltips, and other properties, combined with the data presented on Business Central pages and its own instructions, to determine each step required to complete the task. Starting from the designated Role Center, the agent navigates the pages, invokes UI actions, and enters data as a user would. This approach allows a high degree of flexibility and adaptability for the agent to achieve its goal because the agent’s interaction surface and steps aren’t hardcoded. Instead, AI determines them based on the context of each step.

This flexibility enables the agent to discover and interact with relevant custom fields and actions. It can also attempt to automatically resolve validation errors by processing displayed error messages and adjusting the input accordingly.

### Email and SharePoint monitoring

The agent relies on an internal email dispatcher running as a background task to continuously monitor a designated mailbox for incoming vendor invoices in the form of PDF documents. The dispatcher triggers the agent to perform tasks and subsequently imports the PDF document into **Inbound E-Documents**.

### OCR (Optical Character Recognition) analysis of vendor invoices

For every imported PDF document that constitute a vendor invoice in **Inbound E-Documents**, the PDF is sent for OCR (Optical Character Recognition) analysis with Azure Document Intelligence and the result is stored in the same E-Document record. 

The agent helps with categorizing imported PDF documnents where it is uncertain if the PDF is actually a vendor invoice. These can easily be identified in **Inbound E-Documents** via the **For review** view and from the **For review** cue on the **Accounts Payables Administrator** and **Business Manager** role centers. 

### Processing invoice details
A PDF document which, with high confidence, is considered a valid vendor invoice, is now processed by the agent which will start by identifying the vendor for which to create the purchase invoice draft. In this process, the agent may need the assistance of a user if the agent cannot confidently identify the correct vendor. 

Once the vendor has been identified the processing of the invoice details can commence. Here, the agent uses a variety of different methods to arrive at the best possible suggestions. For example, the agent may consider a mix of AI, the history of vendor invoices, potential mapping of text to G/L accounts, Item References, Recurring Purchase Lines, and more. All of the agents suggestions for the specific vendor invoice will be recorded in a draft related to the specific **Inbound E-Document**. This draft can be reached either from the **Inbound E-Document** when not interacting with the agent, and will also be reffered and linked to when interacting with the agent, when there is a need to involve a user. 

### Drafts of the suggested vendor invoice
The draft page is called **Purchase document draft** and represents the place in the process where suggestions are presented to the user by the agent, and where the agent explains why certain suggestions have been made. This is helpful for users to learn about the agents reasoning and can help users make descision whether to adjust the suggestions before finalizing the draft.

### Customer and Business Central user involvement

Users can inspect the agent's steps and the created sales documents. They can easily identify the data entered by the agent compared to data generated by Business Central's own business logic and provide more input if needed, such as adding discounts or updating shipping costs.

If the customer decides to update the quote by sending another email listing required changes, the agent assists with these changes by locating the quote and making the requested updates. Once the customer confirms the quote's accuracy, the agent converts it into a sales order, which is then also shared with the customer via email, following user's confirmation. 

The agent always involves designated Business Central users to review and approve all outgoing messages, before they're sent to the customers.

## How the agent processes requests

The agent monitors a designated mailbox for incoming customer emails about item inquiries. The mailbox is specified in the Sales Order Agent configuration (learn more in [Set up Sales Order Agent](sales-order-agent-setup.md)). When the agent identifies a potential request in an email, it starts to prepare a sales quote. For example, it verifies whether the customer is registered in Business Central. It then checks item availability, creates a sales quote, and prepares an email response to the customer that includes the quote as a PDF attachment.

Some steps require your intervention, like reviewing email correspondence and assisting the agent as needed. Until an order is created, the agent handles back-and-forth email exchanges with the customer to resolve missing details and allow modifications to the original request. Learn more in [Agent process flow](#agent-process-flow).

### Identifying customers/contacts and related documents

The agent ensures that a request from one customer can't be about another customer's requests. When the agent processes a request, it first identifies the customer in Business Central using the sender's email address. The agent searches for the email among the registered Business Central contacts, sales quotes and orders, and then looks up the customer linked to that email:

- If a customer is found, the agent filters to use only sales quotes and orders that belong to the customer.

  This behavior ensures that the agent only creates and updates documents belonging to the customer that sent the email

- If a contact is found but it's not a customer, the agent filters to use only documents belonging to the contact. Quotes can be sent to contacts that aren't registered as a customer.
- If no contact is found, the agent filters out all documents, and it might request user intervention because it can't find the document.

To prevent the agent from requesting intervention and to assist with reviewing incoming messages, the agent verifies whether the contact is registered and displays a notification on the incoming message review page if it isn't. To resolve this issue, you can either register a new contact/customer or update the contact information of an existing contact/customer. The agent generates the notification to indicate that the contact email wasn't found.

### Finding products/items

The agent analyzes incoming emails to detect parameters for preparing a new sales quote or updating an existing one. Apart from the items themselves, parameters might include the item attributes, quantities, units of measure, requested delivery date, external document number, and more. The agent then searches for these items in Business Central's inventory, within a wide range of related tables.

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

Although the agent can find products based on vague and incomplete descriptions, its effectiveness is influenced by the quality of product information in Business Central. You can improve the agent's ability to find products by enhancing descriptions, attributes, categories, and extended text of your inventory items.

> [!NOTE]
> It might take up to 15 minutes for newly entered data to become searchable as the system re-indexes the tables in the background.

When it finds the items, the agent checks the items' availability by analyzing multiple parameters, such as required quantity, delivery date, location, scheduled and planned receipts and more.

## Agent process flow

### Partcipants

Processing a sales quote request into an order involves three participants:

- Customer who requests a sales quote via email.

    Here's an example of an email:

    > Hello,
    >
    > We are in the process of purchasing furniture for our lodge, and after reviewing your website I would like to request a quote for the following items:
    >
    > - 2 Antwerp tables
    > - 4 Berlin chairs
    > - 4 Rome chairs
    >
    > Could you please provide a sales quote? We will need the items delivered by March 2nd. Additionally, please note our purchase order number: DC1011234.
    >
    > Thank you,
    >
    > [Name]

- Sales order agent, which monitors the mailbox, handles the incoming request, and creates the quote and order
- Business Central user who reviews agent tasks

### General flow

The general flow is illustrated in the figure, which is followed by more details of the steps. The actual flow might vary depending on factors such as follow-up requests, changes or cancellations in review, blocking issues, and so on.

![Shows the Sales Order Agent flow](media/soa-flow.svg)

1. **Customer:** Sends email to Business Central mailbox asking for a sales quote for items.
1. **Sales order agent:** Picks up unread email from inbox and creates a task with a step for reviewing the incoming request.
1. **Reviewer:** Reviews/confirms the step with email.  
1. **Sales order agent:**
    1. Finds the contact or customer.
    1. Finds the requested items and verifies their availability. Learn more in [Item availability in Sales Order Agent (preview)](sales-order-agent-item-availability.md)
    1. Creates the sales quote.
    1. Adds review step with a reply email with attached sales quote as pdf.
1. **Reviewer:** Reviews/confirms email and sales quotes. 
1. **Sales order agent:** Sends email and sales quote PDF to customer.
1. **Customer:** Review sales quote and sends email requesting order.
1. **Sales order agent:** Picks up email and adds review step.
1. **Reviewer:** Reviews/confirms the confirmation email for a sale order.
1. **Sales order agent:**
    1. Converts quote to order.
    1. Adds review task with outgoing email confirming order.
1. **Reviewer:** Reviews/confirms outgoing email.
1. **Sales order agent:** Sends email to customer.

## Billing for use

The Sales Order Agent uses Microaoft Copilot Studio messages for AI interactions, which incur charges based on interaction complexity. Before using the agent, set up a billing model for your Business Central environment. Learn more in [Manage consumption-based billing](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-consumption-billing).

## Next steps

- [Set up the Sales Order Agent](sales-order-agent-setup.md)
- [Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
