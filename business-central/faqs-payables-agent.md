---
title: Payables Agent Frequently Asked Questions
description: Learn how AI automates purchase invoice creation in Business Central, including setup, capabilities, limitations, and responsible use.
ms.date: 09/27/2026
ai-usage: ai-assisted
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
# FAQ for Payables Agent

These frequently asked questions (FAQ) describe the AI impact of Payables Agent feature in Business Central.

## What is the Payables Agent?

Payables Agent is an autonomous AI-powered agent in Microsoft Dynamics 365 Business Central that automates vendor invoice processing. It operates independently to monitor your designated email inbox for PDF invoice attachments, extracts the invoice data, matches vendors, proposes purchase order matches and account classifications, and creates draft purchase documents for your review.

The system combines document processing technology with generative AI to help finance teams reduce manual data entry and speed up accounts payable workflows. When you receive a vendor invoice through email, Payables Agent processes the PDF attachment, identifies the vendor, analyzes each line, and prepares a purchase document draft for review.

> [!IMPORTANT]
> Payables Agent doesn't post purchase invoices. After review, the agent can create a vendor when instructed and can finalize a purchase document draft into an unposted purchase invoice. Review the new vendor and the unposted invoice according to your organization's controls.

## What can Payables Agent do?

Payables Agent handles the end-to-end process of converting vendor invoices into draft purchase documents:

- **Email Processing**: Monitors your designated payables email inbox for incoming PDF invoice attachments and automatically begins processing valid invoices.

- **Document Extraction**: Uses Azure Document Intelligence to extract text, amounts, dates, line items, and vendor details from PDF invoices.

- **Vendor Identification**: Matches vendors using multiple approaches:

  - Exact matching with government registration numbers (VAT registration numbers, Global Location Numbers)

  - Name and address similarity matching

  - AI-powered vendor search that analyzes vendor details and searches historical transactions and your vendor list when exact matching fails

- **Account Classification**: Suggests appropriate accounting treatments for each invoice line:

  - Matches line descriptions to general ledger accounts based on your chart of accounts and transaction history

  - Recommends deferral templates when items should be deferred over time

  - Identifies items that match your existing inventory

- **Purchase order matching**: Proposes purchase order lines for invoice lines when an order is available. Business Central validates vendor, line, unit-of-measure, currency, quantity, receipt, and price conditions and allocates the invoice quantity.

- **Vendor creation**: When no existing vendor match is found, offers to create a new vendor record based on invoice information after you review and confirm the instruction. The new vendor is blocked until a relevant user reviews and unblocks it.

- **Draft creation**: Generates purchase document drafts with extracted data and suggestions for your review. After review, the agent can finalize a draft into an unposted purchase invoice.

- **Human oversight**: Stops processing and requests your assistance when it encounters uncertainty, such as an unidentified vendor or an unclear line classification. Review the proposed values and confirm how the agent should continue.

- **Agent Identity**: Payables Agent operates with its own unique user identity in Business Central. All actions taken by the agent are clearly attributed to this agent user, providing complete audit trails and traceability.

## What is Payables Agent's intended use?

Payables Agent is intended to automate routine vendor invoice processing for Business Central customers, with the primary objective of creating accurate draft purchase invoices from vendor invoices received via email. The system is designed to handle standard business invoices from known vendors, where it can reliably extract invoice data and match it to existing vendors and accounting codes.

The agent is designed for finance teams that regularly process vendor invoices and want to reduce manual data entry while maintaining control over their accounting records. Review the draft before the agent finalizes it. Then review the resulting unposted purchase invoice before a user posts it.

Review confirmation in the agent task is separate from a Business Central approval workflow. Payables Agent doesn't provide vendor approval or purchase invoice approval workflows.

## How was Payables Agent evaluated? What metrics are used to measure performance?

Payables Agent was evaluated through extensive manual and automated testing covering both accuracy and safety.

For accuracy testing, the agent was tested on hundreds of invoice scenarios covering different vendors, invoice formats, and line-item complexities. The testing measured how accurately the system extracted invoice data, matched vendors, and suggested appropriate account classifications compared to human reviewers.

For safety testing, the agent’s responses were evaluated to potentially harmful content, adversarial inputs, and attempts to manipulate the AI system. This included testing with malicious invoice content and user instructions designed to bypass safety measures.

The agent performance is monitor through user feedback and automated quality checks on all processed invoices.

## What are the limitations of Payables Agent? How can users minimize the impact of these limitations?

- **File Format and Language Support:** The agent works with PDF invoices only, and doesn't support other file formats. The agent only processes emails that have PDF attachments. Emails without PDF attachments are not processed for invoice creation. The invoices must arrive via email to monitored mailboxes. Users can't upload files directly.

- **Geographic and language availability:** [!INCLUDE[copilot-geo-and-language-availability](includes/copilot-geo-and-language-availability.md)]

- **Email Attachment Limits:** The agent skips emails with more than 10 attachments. To ensure proper processing, limit each email to 10 or fewer attachments.

- **AI-generated content accuracy**: Payables Agent writes suggestions in a clear way, but the account classifications and vendor matches it generates can be inaccurate. The system can't understand business context or evaluate accuracy the way humans can, so always review its suggestions and use your judgment before finalizing a draft.

- **Purchase order matching**: Review **Order line match** and **Warnings** on every matched draft line. The warnings are deterministic Business Central validations, not AI confidence. The agent might not autonomously select multiple order lines for one invoice line, but you can select multiple compatible lines in Business Central.

- **Order and receipt restrictions**: Matching doesn't support **Charge (Item)** lines or order lines with prepayments. Vendor, currency, unit of measure, and line details must be compatible. Automatic receipt posting isn't available for item-tracked lines, directed put-away and pick locations, or lines with existing posted receipts. Learn more in [Match purchase invoice drafts to purchase orders](match-purchase-invoice-drafts-to-orders.md).

- **Data Dependencies**: Account suggestions improve with historical transaction data. Companies with limited transaction history receive fewer automated suggestions since the agent learns from past invoices and accounting decisions.

- **Volume limitations:** Payables Agent processes up to 100 emails per day and up to 50 emails in one batch. PDF attachments must be 20 MB or smaller and contain a maximum of 10 pages. High-volume processing might experience delays during peak usage periods.

To address these limitations, review drafts before finalization and maintain accurate vendor, item, purchase order, and chart of accounts data in Business Central.

### What operational factors and settings allow for effective and responsible use of Payables Agent?

- **Email Configuration**: Set up a dedicated email address for vendor invoices that Payables Agent monitors. This helps ensure only legitimate business invoices are processed and provides clear audit trails.

- **User Permissions and Controls**: Payables Agent operates under Business Central's standard security model with extra autonomous agent safeguards. When setting up the agent, administrators assign specific user profiles and permission sets that define exactly what the agent can access and modify. Users can configure which other users can delegate invoice processing tasks to the agent. The agent can only access data within these predefined boundaries and can't exceed the permissions granted to it.

- **Review Process**: Review drafts before finalization. Payables Agent can finalize a reviewed draft into an unposted purchase invoice, but it doesn't post the invoice. Business Central approval workflows are separate from the agent review.

- **Data Quality**: Maintain accurate vendor information and chart of accounts in Business Central. The system's suggestions improve when your master data is complete and up-to-date.

- **Monitoring and Feedback**: Pay attention to notifications from Payables Agent when it needs assistance. Provide feedback on suggestions to help improve system accuracy over time.

- **User Control Mechanisms**: Users can stop agent tasks during processing and can skip the automatic email verification step when appropriate. The agent provides notifications when it needs assistance or review.

- **Admin Controls**: Administrators can disable Payables Agent at any time per company. The feature respects all existing Business Central security permissions and approval workflows.

## How do I provide feedback on Payables Agent?

Your feedback helps improve Payables Agent's accuracy and usefulness. Business Central provides built-in feedback options directly in the interface where you review agent-generated content.

- **Thumbs Up/Down Feedback**: When you navigate to a draft created by Payables Agent, you see thumbs up and thumbs down icons next to lines populated by the AI. Use the thumbs up when you're satisfied with the agent's suggestions. Select thumbs down when you aren't happy with the results.

- **Detailed Feedback**: When you select thumbs down, a dialog appears allowing you to submit specific feedback to Microsoft. You can categorize the issue as: inaccurate, offensive/inappropriate for work, or other. You can then provide more details about what went wrong in a text field. Avoid including personal or sensitive information in your feedback.

- **Privacy Note**: When you submit feedback, it's used to improve Microsoft products and services. Your organization's IT administrators are able to view and manage your feedback data.

For technical issues or questions about setup and configuration, contact Microsoft Support through your standard Business Central support channels.

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## How does Payables Agent show me what it's doing?

- **Autonomous Agent Interface**: Payables Agent uses a dedicated side panel in Business Central that is designed for autonomous agent interactions. This panel is distinct from other Business Central features and clearly identifies when you're interacting with an AI agent.

- **Real-Time Visibility**: As the agent works, you can see its progress, reasoning, and decisions in the side panel. The system explains why it made specific vendor matches or account suggestions.

- **Complete Timeline**: After processing, you get a detailed timeline view showing every step the agent took, including when it received the email, extracted data, made decisions, and created drafts. The timeline provides full transparency into the agent's autonomous actions.

- **Clear AI Disclosure**: All content generated or suggested by the agent is clearly marked as AI-generated. You always know when you're reviewing agent-created content versus human-entered data.

## Related information

- [Payables Agent overview](payables-agent.md)
- [Set up Payables Agent](payables-agent-setup.md)
- [Match purchase invoice drafts to purchase orders](match-purchase-invoice-drafts-to-orders.md)
- [Configure Copilot and agent capabilities](enable-ai.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]