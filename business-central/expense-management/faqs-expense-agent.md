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
ai-usage: ai-assisted
---
# Responsible AI FAQ for Expense Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI effect of Expense Agent in [!INCLUDE [prod_short](../includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is Expense Agent?

**Expense Agent** is an AI-powered system in **Microsoft Dynamics 365 Business Central** that streamlines employee expense management. It captures receipts through email or a dedicated web experience, extracts key data, categorizes expenses, and generates draft expense report lines. Employees review and submit their reports via the web experience—no Business Central license is required for these employees—while all data flow securely into Business Central.

> [!IMPORTANT]
> **Safety Note**: Expense Agent only produces draft expense entries and reports; it doesn't post transactions or make permanent financial changes without human review and approval.

## What can Expense Agent do? 

The Expense Agent streamlines the entire expense lifecycle, from receipt capture to reporting and approval. It provides the following capabilities:  

-	**Receipt processing**: Collects receipts via the dedicated Expense Web experience or automatically from a monitored shared mailbox.
-	**Data extraction and itemization**: Uses Anthropic Claude Sonnet 4.6 model to identify and extract key information such as merchant name, expense date, total amount, currency, and line-item details where applicable.
-	**Categorization**: Uses Anthropic Claude Sonnet 4.6 model to automatically classify expenses according to company-configured categories and subcategories.
-	**Expense grouping and expense report creation**: Uses Anthropic Claude Sonnet 4.6 model to convert extracted receipt data into draft expense lines and organize them into draft expense reports.
-	**Rule Validation**: Validates and enforces internal company-configured policies and rules
-	**Timely pending report emails**: Sends automated notifications of pending reports for review and action.
-	**User review**: Presents draft reports to employees via the Web experience for review, correction, and submission.
-	**Workflow orchestration**: Coordinates the full sequence of receipt intake, extraction, categorization, report creation, submission, and approvals as part of a complete end-to-end expense process.

## What is Expense Agent’s intended use?

The Expense Agent helps organizations manage employee expenses more efficiently by automating key steps in the expense reporting process while keeping users in control through review and approval.

It automatically collects receipts from a monitored email mailbox or receipts uploaded by the user via a dedicated web experience. It uses AI to extract key details such as merchant, date, amount, currency, and line items, and suggest categories. The system then uses AI for grouping expenses.

Later, it validates them against company rules and creates draft expense reports that you can review before you submit it for approval by another user.

Although the user-facing experience operates outside of [!INCLUDE [prod_short](../includes/prod_short.md)], all financial data, audit trails, and posting logic are processed securely within the [!INCLUDE [prod_short](../includes/prod_short.md)] environment.

## How was Expense Agent evaluated?

Expense Agent uses Anthropic model (Claude Sonnet 4.6) as-is for all AI processing. Expense Agent was evaluated through extensive manual and automated testing to assess both accuracy and safety.

Accuracy testing focuses on the quality of AI‑assisted outputs compared to human judgment across realistic expense scenarios. The evaluation emphasizes how well the agent supports the core expense workflow, including:

-	**Data extraction accuracy**: Measure how accurately the agent extracts key information from receipts and supporting documents.
-	**Categorization accuracy**: Evaluate how well expenses are assigned to the correct categories and types based on receipt content, and company configuration.
-	**Itemization quality**: Assess the correctness and completeness of itemized expenses (for example, hotels or multi‑line receipts), ensuring line splits, amounts, and descriptions align with the original document.
-	**Expense report creation accuracy**: Validate that extracted and categorized expenses are grouped correctly into draft expense reports, with all required fields populated and ready for user review.

Results are compared against expected outcomes defined by human reviewers to identify discrepancies and areas for improvement.

In addition to accuracy, Expense Agent undergoes safety evaluation to ensure it behaves responsibly and predictably. For safety testing, each potential harm scenario was tested across hundreds of data files with different unsafe input combinations to ensure robust safety and reliability.

After deployment, Expense Agent performance is continuously monitored using:

-	**User feedback** collected during review and correction of AI‑generated expense data
-	**Automated quality checks** on extraction, categorization, and report completeness
-	**Operational telemetry** to detect recurring issues or degradation in performance

These signals are used to improve the agent’s accuracy over time while maintaining transparency and user control.

## What are the limitations of Expense Agent? 

-	**File Formats & Size Limits**: The agent supports PDF and images (.jpg, .jpeg, .png, .gif, .webp, .heic, .heif) as file types, but for both of them apply the default maximum file size of 10 MB (configurable).
-	**Volume Limitations**: Expense Agent processes up to 25 files per upload or email attachment, and up to 50MB as a batch. Complex files might exceed processing limits or timeout, triggering a request for human intervention.
-	**Geographic and language availability**: The Expense Agent user interface and environment currently support English only. Receipt upload isn't restricted by language, but receipts in some languages might result in reduced extraction accuracy. Initial regional availability is limited to the US only.
-	**System Limitations & Dependencies**: Only one Expense Agent can be configured per Business Central company. A single expanse user can't be enabled across multiple Expense Agents. The agent stops processing if AI services fail or mailbox access is lost. Complex approval systems with interim or conditional approvals isn't yet supported. Also, the post approval process, like posting and reimbursements, is beyond agent’s scope and is handled manually in [!INCLUDE [prod_short](../includes/prod_short.md)]. On-behalf expense submission isn't supported yet.
-	**AI Accuracy Limitations**: AI-generated content, such as extracted data, suggested categories, or expense groupings, might be inaccurate; human review is required before submission or approval.

## What operational factors and settings allow for effective and responsible use of Expense Agent?

-	**User Permissions and Controls**: The agent operates under Business Central’s standard security model with extra safeguards. When setting up the agent, administrators assign specific permission sets to define what the agent can access and modify, and they can also configure who might use the agent. The agent can only access data within these predefined boundaries and can't exceed the permissions granted to it.
-	**Review and Approval Process**: Always review drafts before approval. The agent only creates drafts and never posts transactions automatically.
-	**Admin Controls**: Administrators can disable Expense Agent per company at any time. The agent respects all existing Business Central security permissions, and users must review draft expense reports before approval.
-	**Traceability**: All actions are logged under the agent’s user ID, ensuring full traceability. Timely notifications alert users when agent tasks require review or approval.
-	**Monitoring and Feedback**: Pay attention to notifications from Expense Agent when it needs assistance. Provide feedback on suggestions to help improve system accuracy over time.

## How do I provide feedback on Expense Agent?

Your feedback helps improve Expense Agent's accuracy and usefulness. Business Central provides built-in feedback options directly in the interface where you review agent-generated content.

-	**General Feedback**: In the web experience, from the settings menu in the page header, there's a **Help** panel that contains a **Give Feedback** action that can be used to provide general feedback in the form of compliments, reporting issues, or providing suggestions.
-	**Thumbs Up/Down Feedback**: In the web app, when you go to entities created by Expense Agent there are **thumbs up** and **thumbs down** icons. Use the thumbs up icon when you're satisfied with the agent's suggestions. Use thumbs down when you aren't happy with the results.
-	**Detailed Feedback**: In each of the feedback scenarios, a dialog appears allowing you to submit specific feedback to Microsoft. If one or more receipts were attached to an expense, you can choose to send them along with the feedback. You can also opt to include a screenshot of part or all of the web app. You can then provide more details about what went right or wrong in a text field. Avoid including personal or sensitive information in your feedback.
-	**Permission to Contact**: You might be prompted to grant Microsoft permission to contact you regarding your feedback. 
-	**Privacy Note**: When you submit feedback, we use it to improve Microsoft products and services. Your organization's IT administrators can view and manage your feedback data.

For technical issues or questions about setup and configuration, contact Microsoft Support through your standard Business Central support channels.

[!INCLUDE[ai-data-collection](../includes/ai-data-collection.md)]

## How does Payables Agent show me what it's doing?

**Clear AI Disclosure**: All content generated or suggested by the agent is clearly marked as AI-generated. You always know when you're reviewing agent-created content versus human-entered data.

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)  
[Set up Expense Agent](ExpenseAgentSetupGuide.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Anthropic as a subprocessor for Microsoft Online Services](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/copilot/connect-to-ai-subprocessor.md)
