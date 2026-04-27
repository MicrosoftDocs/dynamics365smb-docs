---
title: Responsible AI FAQ for Expense Agent (preview)
description: Learn how AI automates expenses processing in Business Central, including setup, capabilities, limitations, and responsible use.
ms.date: 04/20/2026
ms.update-cycle: 180-days
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: altotovi
ms.author: altotovi
ms.reviewer: altotovi
ms.collection:
  - bap-ai-copilot
---
# Responsible AI FAQ for Expense Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of Expense Agent feature in Business Central.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is Expense Agent? 

**Expense Agent** is an AI-powered system in **Microsoft Dynamics 365 Business Central** that streamlines employee expense management. It captures receipts through email or a dedicated web experience, extracts key data, categorizes expenses, and generates draft expense report lines. Employees review and submit their reports via the web experience—no Business Central license is required for these employees—while all data flow securely into Business Central.

> [!IMPORTANT]
> **Safety Note**: Expense Agent only produces draft expense entries and reports; it does not post transactions or make permanent financial changes without human review and approval.

## What can Expense Agent do? 

The Expense Agent streamlines the entire expense lifecycle, from receipt capture to reporting and approval. It provides the following capabilities:  

-	**Receipt processing**: Collects receipts via the dedicated Expense Web experience or automatically from a monitored shared mailbox.
-	**Data extraction and itemization**: Uses Anthropic Claude Sonnet 4.6 model to identify and extract key information such as merchant name, expense date, total amount, currency, and line-item details where applicable.
-	**Categorization**: Uses Anthropic Claude Sonnet 4.6 model to automatically classify expenses according to company-configured categories and subcategories.
-	**Expense grouping and expense report creation**: Uses Anthropic Claude Sonnet 4.6 model to convert extracted receipt data into draft expense lines and organize them into draft expense reports.
-	**Rule Validation**: Validates and enforces internal company-configured policies and rules
-	**Timely pending report emails**: Sends automated notifications of pending reports for review and action.
-	**User review**: Presents draft reports to employees via the Web experience for review, correction, and submission.
-	**Workflow orchestration**: Coordinates the full sequence of receipt intake, extraction, categorization, report creation, submission and approvals as part of a complete end-to-end expense process.

## What is Expense Agent’s intended use(s)?

The Expense Agent helps organizations manage employee expenses more efficiently by automating key steps in the expense reporting process while keeping users in control through review and approval.

It automatically collects receipts from a monitored email mailbox or receipts uploaded by the user via a dedicated web experience. It uses AI to extract key details such as merchant, date, amount, currency, and line items, and suggest categories. The system then uses AI for grouping expenses.

Later it validates them against company rules and creates draft expense reports to be reviewed by the user before submission for approval by another user.

By coordinating receipt intake, data extraction, categorization, draft report generation, and approvals, the Expense Agent system streamlines the full expense workflow, reduces manual effort, and ensures all financial data is verified before submission.

And although the user-facing experience operates outside Business Central, all financial data, audit trails, and posting logic are processed securely within the BC environment—providing a streamlined employee experience without compromising ERP‑grade accuracy, governance, or control.

## How was Expense Agent evaluated? 

Expense Agent uses Anthropic model (Claude Sonnet 4.6) as-is for all AI processing. Expense Agent was evaluated through extensive manual and automated testing to assess both accuracy and safety.

Accuracy testing focuses on the quality of AI‑assisted outputs compared to human judgment across realistic expense scenarios. The evaluation emphasizes how well the agent supports the core expense workflow, including:

-	**Data extraction accuracy**: Measuring how accurately the agent extracts key information from receipts and supporting documents.
-	**Categorization accuracy**: Evaluating how well expenses are assigned to the correct categories and types based on receipt content, and company configuration.
-	**Itemization quality**: Assessing the correctness and completeness of itemized expenses (for example, hotels or multi‑line receipts), ensuring line splits, amounts, and descriptions align with the original document.
-	**Expense report creation accuracy**: Validating that extracted and categorized expenses are grouped correctly into draft expense reports, with all required fields populated and ready for user review.

Results are compared against expected outcomes defined by human reviewers to identify discrepancies and areas for improvement.

In addition to accuracy, Expense Agent undergoes safety evaluation to ensure it behaves responsibly and predictably. For safety testing, each potential harm scenario was tested across hundreds of data files with different unsafe input combinations to ensure robust safety and reliability.

After deployment, Expense Agent performance is continuously monitored using:

-	**User feedback** collected during review and correction of AI‑generated expense data
-	**Automated quality checks** on extraction, categorization, and report completeness
-	**Operational telemetry** to detect recurring issues or degradation in performance

These signals are used to improve the agent’s accuracy over time while maintaining transparency and user control.

## What are the limitations of Expense Agent? 

-	**File Formats & Size Limits**: The agent supports PDF and images (.jpg, .jpeg, .png, .gif, .webp, .heic, .heif) as file types, but for both of them apply the default maximum file size of 10MB (configurable).
-	**Volume Limitations**: Expense Agent processes up to 25 files per upload or email attachment, and up to 50MB as a batch. Complex files may exceed processing limits or timeout, triggering a request for human intervention.
-	**Geographic and language availability**: The Expense Agent user interface and environment currently support English only. Receipt upload is not restricted by language, but receipts in some languages may result in reduced extraction accuracy. Initial regional availability is limited to the US only.
-	**System Limitations & Dependencies**: Only one Expense Agent can be configured per Business Central company. A single expanse user cannot be enabled across multiple Expense Agents. The agent stops processing if AI services fail or mailbox access is lost. The complex approval system like interim or conditional approvals is not supported yet and the post approval process, like posting and reimbursements, is beyond agent’s scope and is handled manually inside Business Central. On-behalf expense submission is not supported yet.
-	**AI Accuracy Limitations**: AI-generated content, such as extracted data, suggested categories, or expense groupings, may be inaccurate; human review is required before submission or approval.

## What operational factors and settings allow for effective and responsible use of Expense Agent?

-	**User Permissions and Controls**: The agent operates under Business Central’s standard security model with additional safeguards. When setting up the agent, administrators assign specific permission sets to define what the agent can access and modify, and they can also configure who may use the agent. The agent can only access data within these predefined boundaries and can't exceed the permissions granted to it.
-	**Review and Approval Process**: Always review drafts before approval. The agent only creates drafts and never posts transactions automatically.
-	**Admin Controls**: Administrators can disable Expense Agent per company at any time. The agent respects all existing Business Central security permissions, and users must review draft expense reports before approval.
-	**Traceability**: All actions are logged under the agent’s user ID, ensuring full traceability. Timely notifications alert users when agent tasks require review or approval.
-	**Monitoring and Feedback**: Pay attention to notifications from Expense Agent when it needs assistance. Provide feedback on suggestions to help improve system accuracy over time.

## How do I provide feedback on Expense Agent?

Your feedback helps improve Expense Agent's accuracy and usefulness. Business Central provides built-in feedback options directly in the interface where you review agent-generated content.

-	**General Feedback**: In the web experience, from the settings menu in the page header, there is a **Help** panel that contains a **Give Feedback** action which can be used to provide general feedback in the form of compliments, reporting issues, or providing suggestions.
-	**Thumbs Up/Down Feedback**: In the web experience, when you navigate to entities created by Expense Agent, you will see **thumbs up** and **thumbs down** icons. Use the thumbs up when you are satisfied with the agent's suggestions. Click thumbs down when you are not happy with the results.
-	**Detailed Feedback**: In each of the above feedback scenarios, a dialog appears allowing you to submit specific feedback to Microsoft. If one or more receipts were attached to an expense, you may have the option to choose to send them along with the feedback. You can also opt to include a screenshot of part or all of the web experience. You can then provide additional details about what went right or wrong in a text field. Please avoid including personal or sensitive information in your feedback.
-	**Permission to Contact**: You may be prompted to grant Microsoft permission to contact you regarding your feedback. 
-	**Privacy Note**: When you submit feedback, it will be used to improve Microsoft products and services. Your organization's IT administrators will be able to view and manage your feedback data.

For technical issues or questions about setup and configuration, contact Microsoft Support through your standard Business Central support channels.

[!INCLUDE[ai-data-collection](../includes/ai-data-collection.md)]

## How does Payables Agent show me what it's doing?

**Clear AI Disclosure**: All content generated or suggested by the agent is clearly marked as AI-generated. You always know when you're reviewing agent-created content versus human-entered data.

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Set up Expense Agent](ExpenseAgentSetupGuide.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Anthropic as a subprocessor for Microsoft Online Services](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/copilot/connect-to-ai-subprocessor.md)
