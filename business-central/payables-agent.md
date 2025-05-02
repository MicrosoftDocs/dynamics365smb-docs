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

The Payables Agent helps Business Central users automate the processing of vendor invoices. The agent monitors mailboxes for incoming vendor invoices and uses AI to analyze the content of the invoices. It speeds up registration and processing of invoices by interpreting the invoice content and presents it to users in a draft. In doing so, the Payables Agent uses AI to suggest invoice details. Ideally, users will have to do very few or no corrections to the suggested invoice information before they finalize the draft and it becomes a real purchase invoice, ready for approval and posting.

> [!TIP]
> Watch a short video in the Dynamics Business Central channel on YouTube at [Get started with the Payables Agent for Dynamics 365 Business Central](https://www.youtube.com/watch?v=6icbmbLc_Og).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->
## Functionality
The functionality of this preview does not represent the full vision of the Payables Agent. We are in the early stages of the Payables Agent and many more features and AI is intended to be added to it. In time, the agent is intended to assist with:
* Purchase order matching
* Approval flows
* Anomaly detection
* And many other things to support in the accounts payables processes and accounting.

### Activation and configuration

The agent is readily available in the product. To activate it, you specify the email inbox you want the agent to monitor. Additionally, designate the users authorized to use the agent to process vendor invoices, enabling the agent to act on behalf of a company, department, or team&mdash;not just an individual user.

## Payables Agent process flow
The end-to-end process handled by the Payables Agent is illustrated in the figure below, which is followed by more details of the steps. The actual flow might vary depending on factors such as clarity of analysed invoice details and existing purchase invoice history, blocking issues, and so on.

![Shows the Sales Order Agent flow](media/payables-agent-flow.png)

1. **Vendor or employee:** Sends email to a mailbox monitored by the agent. Alternatively, an employee forwards a vendor invoice to the mailbox.
1. **Payables Agent:** Picks up unread emails that have PDF attachments from the mailbox and imports the PDF into **Inbound E-Documents** in Business Central.
1. **Payables Agent:** Extacts invoice information from the PDF using the Azure Document Intelligence.
1. **Payables Agent:** Identifies a vendor in Business Central based on the extracted invoice information.
1. **Agent supervisor:** May be called upon to assist the agent with identifying the vendor if the agent cannot confidently identify the right vendor.
1. **Payables Agent:** Uses AI to suggest invoice details based on the extracted invoice information.
1. **Agent supervisor:** May be called upon to review, confirm or change the suggested invoice details in a purchase document draft, depending on agent configuration settings and the agent's confidence in the suggestions.
1. **Payables Agent:** Finalizes the purchse document draft into a purchase invoice. Users can now see the invoice in the **Purchase Invoices** list.

### Email monitoring

The agent relies on an internal email dispatcher running as a background task to continuously monitor a designated mailbox for incoming vendor invoices in the form of PDF documents. The dispatcher triggers the agent to perform tasks and subsequently imports the PDF document into **Inbound E-Documents**.

### OCR (Optical Character Recognition) analysis of vendor invoices

For every imported PDF document that constitute a vendor invoice in **Inbound E-Documents**, the PDF is sent for OCR (Optical Character Recognition) analysis with Azure Document Intelligence and the result is stored in the same E-Document record. 

The agent helps with categorizing imported PDF documnents where it is uncertain if the PDF is actually a vendor invoice. These can easily be identified in **Inbound E-Documents** via the **For review** view and from the **For review** cue on the **Accounts Payables Administrator** and **Business Manager** role centers. 

### Suggesting invoice details
A PDF document which, with high confidence, is considered a valid vendor invoice, is now processed by the agent which will start by identifying the vendor for which to create the purchase invoice draft. In this process, the agent may need the assistance of a user if the agent cannot confidently identify the correct vendor. 

Once the vendor has been identified the processing of the invoice details can commence. Here, the agent uses a variety of different methods to arrive at the best possible suggestions. For example, the agent may consider a mix of AI, the history of vendor invoices, potential mapping of text to G/L accounts, Item References, Recurring Purchase Lines, and more. All of the agents suggestions for the specific vendor invoice will be recorded in a draft related to the specific **Inbound E-Document**. This draft can be reached either from the **Inbound E-Document** when not interacting with the agent, and will also be reffered and linked to when interacting with the agent, when there is a need to involve a user. 

### Drafts of the suggested vendor invoice
The draft page is called **Purchase document draft** and represents the place in the process where suggestions are presented to the user by the agent, and where the agent explains why certain suggestions have been made. This is helpful for users to learn about the agents reasoning and can help users make descision whether to adjust the suggestions before finalizing the draft.

Once a draft has been finalized it will be linked to the purchase invoice that is created and no longer be editable. However, the draft will be kept as long as the purchase invoice exists.

> [!NOTE]
> Even though a regular purchase invoice entity in Business Central can be considered a draft until it is posted, the **Purchase document draft** page has been introduced as an intermediary stage to 1) present users with a option to make corrections before finalizing the draft into a real unposted purchase invoice, and to 2) have a designated stage to review AI generated content.

## General agent operations

The Payables Agent is designed to run autonomously in the background, using AI to perform its tasks while keeping users informed about key steps and involving them when necessary. Involvement might be needed in specific scenarios, for instance to review suggested vendor invoice drafts, based on configured preferences.

Conceptually, the agent interacts with Business Central functionality in a manner similar to how Business Central users interact with it. The agent is provided with general instructions, expressed in natural language, outlining how the process of vendor invoices should be handled. It then uses UI metadata, such as captions, tooltips, and other properties, combined with the data presented on Business Central pages and its own instructions, to determine each step required to complete the task. Starting from the designated Role Center, the agent navigates the pages, invokes UI actions, and enters data as a user would. This approach allows a high degree of flexibility and adaptability for the agent to achieve its goal because the agent’s interaction surface and steps aren’t hardcoded. Instead, AI determines them based on the context of each step.

This flexibility enables the agent to discover and interact with relevant custom fields and actions. It can also attempt to automatically resolve validation errors by processing displayed error messages and adjusting the input accordingly.

### Customer and Business Central user involvement

Users can inspect the agent's steps and the imported PDF invoices and suggested purchase invoice drafts. They can easily identify the data entered by the agent compared to data generated by Business Central's own business logic and imported data from the OCR analysis, and change the purchase invoice draft if needed.

The agent involves designated Business Central users if it is unsure how to proceed with registering the invoice. For example if the vendor could not be identified with confidence.

### How the agent processes requests

The agent monitors mailboxes and SharePoint/OneDrive folders and looks for PDF documents. This is achieved via the **E-Documents Connector for Microsoft 365** which will automatically be set up when the agent is configured (learn more in [Set up Payables Agent](payables-agent-setup.md)). You determine if you want to monitor mailboxes and/or folders in SharePoint and OneDrive. Regardless of the source the agent will import the PDF into **Inbound E-Documents** extract invoice information with Azure Document Intelligence. Then, the agent will create an AI generated draft of its interpretation of the invoice, and the draft is now ready for further processing by a user.

Some steps require the user's intervention, like selecting the correct vendor to use for the invoice if the vendor could not be identified confidently by the agent. Learn more in [Agent process flow](#agent-process-flow).

> [!NOTE]
> While the agent is in preview, it is recommended to use a designated mailbox for receiving vendor invoices. If a mailbox is used by multiple agents (i.e. shared with the Sales Order Agent) it will cause conflict of ownership of incoming emails.

## Permissions and profiles

The agent operates within the permissions and profile (role) assigned to it by the administrator. Permissions define which areas of the product (tables) the agent has access to. The profile outlines the UX elements (pages and actions) the agent can engage with during its work. Default permissions and the profile are assigned to the agent out of the box; however, administrators can update these permissions as needed.

## Billing for use

The Sales Order Agent uses Microaoft Copilot Studio messages for AI interactions, which incur charges based on interaction complexity. Before using the agent, set up a billing model for your Business Central environment. Learn more in [Manage consumption-based billing](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-consumption-billing).

## Next steps

- [Set up the Sales Order Agent](sales-order-agent-setup.md)
- [Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
