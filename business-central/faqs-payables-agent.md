---
title: FAQ for Payables Agent
description: Learn how AI automates purchase invoice creation in Business Central, including setup, capabilities, limitations, and responsible use.
ms.date: 11/23/2025
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

Payables Agent is an autonomous AI-powered agent in Microsoft Dynamics 365 Business Central that automates vendor invoice processing. It operates independently to monitor your designated email inbox for PDF invoice attachments, extracts the invoice data, matches vendors, suggests account classifications, and creates draft purchase documents for your review.

The system combines document processing technology with generative AI to help finance teams reduce manual data entry and speed up accounts payable workflows. When you receive a vendor invoice via email, Payables Agent autonomously processes the PDF attachment, identifies the vendor from your existing vendor list, analyzes each line item to suggest appropriate accounting treatments, and creates a complete draft purchase invoice ready for your approval.

> [!IMPORTANT]
> **Safety Note**: Payables Agent never performs severe or irreversible actions. It creates drafts only and never automatically posts invoices or makes permanent changes to your financial data without explicit human approval.

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

- **Vendor Creation**: When no existing vendor match is found, offers to create new vendor records based on invoice information, subject to your review and approval.

- **Draft Creation**: Generates complete draft purchase invoices with all extracted data and AI suggestions, ready for your review and approval.

- **Human Oversight**: Stops processing and requests your assistance whenever it encounters uncertainty, such as unidentifiable vendors or unclear line item classifications. The agent escalates high-risk actions like vendor creation or unusual account assignments for mandatory human approval.

- **Agent Identity**: Payables Agent operates with its own unique user identity in Business Central. All actions taken by the agent are clearly attributed to this agent user, providing complete audit trails and traceability.

## What is Payables Agent's intended use?

Payables Agent is intended to automate routine vendor invoice processing for Business Central customers, with the primary objective of creating accurate draft purchase invoices from vendor invoices received via email. The system is designed to handle standard business invoices from known vendors, where it can reliably extract invoice data and match it to existing vendors and accounting codes.

The agent is designed for finance teams that regularly process vendor invoices and want to reduce manual data entry while maintaining full control over their accounting records. All drafts created by Payables Agent require human review and approval before posting.

**High-Risk Actions**: The agent treats vendor creation and converting drafts to purchase invoices as high-risk actions that require mandatory human approval before proceeding.

## How was Payables Agent evaluated? What metrics are used to measure performance?

Payables Agent was evaluated through extensive manual and automated testing covering both accuracy and safety.

For accuracy testing, the agent was tested on hundreds of invoice scenarios covering different vendors, invoice formats, and line-item complexities. The testing measured how accurately the system extracted invoice data, matched vendors, and suggested appropriate account classifications compared to human reviewers.

For safety testing, the agent’s responses were evaluated to potentially harmful content, adversarial inputs, and attempts to manipulate the AI system. This included testing with malicious invoice content and user instructions designed to bypass safety measures.

The agent performance is monitor through user feedback and automated quality checks on all processed invoices.

## What are the limitations of Payables Agent? How can users minimize the impact of these limitations?

- **File Format and Language Support:** The agent works with PDF invoices only - other file formats are not supported. The invoices must arrive via email to monitored mailboxes; users cannot upload files directly. The agent only supports English.

- **AI-Generated Content Accuracy**: Payables Agent writes suggestions in a clear way, but the account classifications and vendor matches it generates can be inaccurate. The system cannot understand business context or evaluate accuracy the way humans can, so you should always review what it suggests and use your judgment before approving any draft.

- **Data Dependencies**: Account suggestions improve with historical transaction data. Companies with limited transaction history will receive fewer automated suggestions since the agent learns from past invoices and accounting decisions.

- **Volume Limitations**: Payables Agent processes up to 100 emails per day and up to 50 emails in one batch. PDF attachments must be 5MB or smaller and contain a maximum of 10 pages. High-volume processing may experience delays during peak usage periods.

To address these limitations, always review drafts before approval, and maintain good vendor and chart of accounts data in Business Central.

### What operational factors and settings allow for effective and responsible use of Payables Agent?

- **Email Configuration**: Set up a dedicated email address for vendor invoices that Payables Agent monitors. This helps ensure only legitimate business invoices are processed and provides clear audit trails.

- **User Permissions and Controls**: Payables Agent operates under Business Central's standard security model with additional autonomous agent safeguards. When setting up the agent, administrators assign specific user profiles and permission sets that define exactly what the agent can access and modify. Users can configure which other users can delegate invoice processing tasks to the agent. The agent can only access data within these predefined boundaries and cannot exceed the permissions granted to it.

- **Review and Approval Process**: Always review drafts before approval. Payables Agent creates drafts but never automatically posts invoices. The system provides detailed information about its suggestions and reasoning to help you make informed decisions.

- **Data Quality**: Maintain accurate vendor information and chart of accounts in Business Central. The system's suggestions improve when your master data is complete and up-to-date.

- **Monitoring and Feedback**: Pay attention to notifications from Payables Agent when it needs assistance. Provide feedback on suggestions to help improve system accuracy over time.

- **User Control Mechanisms**: Users can stop agent tasks at any point during processing and can skip the automatic email verification step for faster processing when desired. The agent provides clear notifications when it needs assistance or approval.

- **Admin Controls**: Administrators can disable Payables Agent at any time per company. The feature respects all existing Business Central security permissions and approval workflows.

## How do I provide feedback on Payables Agent?

Your feedback helps improve Payables Agent's accuracy and usefulness. Business Central provides built-in feedback options directly in the interface where you review agent-generated content.

- **Thumbs Up/Down Feedback**: When you navigate to a draft created by Payables Agent, you will see thumbs up and thumbs down icons next to lines populated by the AI. Use the thumbs up when you are satisfied with the agent's suggestions. Click thumbs down when you are not happy with the results.

- **Detailed Feedback**: When you select thumbs down, a dialog appears allowing you to submit specific feedback to Microsoft. You can categorize the issue as: inaccurate, offensive/inappropriate for work or other. You can then provide additional details about what went wrong in a text field. Please avoid including personal or sensitive information in your feedback.

- **Privacy Note**: When you submit feedback, it will be used to improve Microsoft products and services. Your organization's IT administrators will be able to view and manage your feedback data.

For technical issues or questions about setup and configuration, contact Microsoft Support through your standard Business Central support channels.

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## How does Payables Agent show me what it is doing?

- **Autonomous Agent Interface**: Payables Agent uses a dedicated side panel in Business Central that is specifically designed for autonomous agent interactions. This panel is distinct from other Business Central features and clearly identifies when you are interacting with an AI agent.

- **Real-Time Visibility**: As the agent works, you can see its progress, reasoning, and decisions in the side panel. The system explains why it made specific vendor matches or account suggestions.

- **Complete Timeline**: After processing, you get a detailed timeline view showing every step the agent took, including when it received the email, extracted data, made decisions, and created drafts. This provides full transparency into the agent's autonomous actions.

- **Clear AI Disclosure**: All content generated or suggested by the agent is clearly marked as AI-generated. You always know when you are reviewing agent-created content versus human-entered data.

## Related information

[Payables Agent overview](payables-agent.md)  
[Set up Payables Agent](payables-agent-setup.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  