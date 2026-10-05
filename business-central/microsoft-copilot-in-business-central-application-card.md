---
title: Application Card for Microsoft Copilot in Business Central
description: Learn about the AI technology used by Microsoft Copilot in Business Central, including how it uses Business Central data, its limitations, and responsible AI considerations.
author: jswymer
ms.author: jswymer
ms.topic: faq
ms.custom: bap-template
ai-usage: ai-assisted
ms.date: 10/02/2026
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot
  - get-started
---
# Application Card: Microsoft Copilot in Business Central

## What is an Application Card?

Microsoft's Application and Platform Cards are intended to help you understand how our AI technology works, the choices application owners can make that influence application performance and behavior, and the importance of considering the whole application, including the technology, the people, and the environment. Application Cards are created for AI applications and Platform Cards are created for AI platform services. These resources can support the development or deployment of your own applications and can be shared with users or stakeholders impacted by them.

As part of its commitment to responsible AI, Microsoft values [six core principles](https://www.microsoft.com/ai/principles-and-approach/?msockid=3da790040c776d6f2b5485e40de56c06#ai-principles): fairness, reliability and safety, privacy and security, inclusiveness, transparency, and accountability. The [Responsible AI Standard](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/final/en-us/microsoft-brand/documents/Microsoft-Responsible-AI-Standard-General-Requirements.pdf?culture=en-us&country=us) embeds these principles and guides teams in designing, building, and testing AI applications. Application and Platform Cards play a key role in operationalizing these principles by offering transparency around capabilities, intended uses, and limitations. For further insight, explore Microsoft's [Responsible AI Transparency Report](https://cdn-dynmedia-1.microsoft.com/is/content/microsoftcorp/microsoft/msc/documents/presentations/CSR/Responsible-AI-Transparency-Report-2026.pdf) and Code of Conduct, which outline how [enterprise customers](/legal/ai-code-of-conduct) and [individuals](https://www.microsoft.com/servicesagreement) can engage with AI responsibly.

## Overview

**Microsoft Copilot in Business Central** brings the Microsoft Copilot conversational experience into Dynamics 365 Business Central. Users can interact with Copilot from Business Central and ask natural-language questions about information relevant to their work. The experience combines capabilities provided by Microsoft Copilot with Business Central-specific grounding, application context, and tools that enable Copilot to retrieve and explain Business Central information.

Microsoft Copilot provides the underlying conversational experience and shared AI capabilities. Business Central extends that experience by providing product-specific context and access to Business Central capabilities. Depending on the scenario, this context can include the Business Central company, page or record the user is working with, and other application context. Business Central-specific tools retrieve information using the identity and permissions of the signed-in Business Central user.

This application card focuses on **what Business Central adds to the Microsoft Copilot experience**. For shared Microsoft Copilot capabilities and Responsible AI information that aren't specific to Business Central, see [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

## Key terms

The following list provides a glossary of key terms related to Microsoft Copilot in Business Central:

**Application context**: Information about where a user is working in Business Central that can help Microsoft Copilot interpret a request. Depending on the scenario, this context can include information about the current company, page, record, installed extensions, or other relevant Business Central application state.

**Business Central grounding**: The process of providing Microsoft Copilot with relevant information retrieved from Business Central so that a response can be based on the user's business data rather than only on the general knowledge of the underlying AI model.

**Business Central tool**: A Business Central-specific capability that Microsoft Copilot can invoke to retrieve information or perform a supported Business Central operation. Tools operate within the Business Central application and security boundaries.

**Citation**: A reference in a Copilot response to Business Central information used to support the response. Where supported, citations or links allow users to inspect the underlying Business Central information.

**Grounding**: The process of supplying an AI system with relevant information from an authoritative source to help it generate a response that is appropriate to the user's request.

**Microsoft Copilot**: The Microsoft AI experience that provides the conversational interface, orchestration, and shared AI capabilities used by Microsoft Copilot in Business Central. Learn about capabilities that aren't specific to Business Central in [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

## Key features or capabilities

The key features and capabilities outlined here describe what Microsoft Copilot in Business Central is designed to do and how it performs across supported tasks.

- **Ask questions about Business Central data**: Users can ask natural-language questions about information in Business Central. Business Central-specific capabilities retrieve relevant application data and provide it to Microsoft Copilot as grounding for the response.

- **Use Business Central application context**: Microsoft Copilot uses context supplied by Business Central to better understand what the user is asking about. For example, context about the page or record the user is viewing can allow the user to ask a question without repeating information that's already apparent from where they're working.

- **Retrieve information within the user's permissions**: Business Central-specific capabilities use the identity and permissions of the signed-in user when accessing Business Central information. Using Microsoft Copilot doesn't grant a user additional access to Business Central data.

- **Provide references to Business Central information**: Where supported, responses can include citations or links to relevant Business Central information. These references help users inspect the underlying records and verify AI-generated responses.

- **Combine Business Central with Microsoft Copilot capabilities**: The Business Central integration is part of the broader Microsoft Copilot experience. Depending on the user's Microsoft Copilot capabilities and entitlements, the experience can also use capabilities provided by Microsoft Copilot outside Business Central.

## Intended uses

You can use Microsoft Copilot in Business Central in multiple business scenarios. Some examples of use cases include:

- **Find business information using natural language**: Ask about customers, vendors, documents, or other supported Business Central information without first navigating to the page where the information is stored. This capability reduces the time required to locate information and helps users who aren't familiar with the Business Central navigation structure.

- **Ask questions in the context of the current task**: Ask questions related to the context when working with a supported Business Central page or record. Providing application context reduces the amount of information you need to repeat in the prompt.

- **Understand Business Central information**: Ask Microsoft Copilot to help explain or summarize supported Business Central information. Inspect the underlying Business Central records when accuracy is important.

- **Navigate to relevant Business Central information**: Where supported, use citations and links in responses to help move from a conversational answer to the underlying Business Central information.

Microsoft Copilot in Business Central is designed to assist users rather than replace professional judgment or established business controls. Verify AI-generated information before relying on it for financial, regulatory, legal, or other consequential decisions.

## Models and training data

Microsoft Copilot in Business Central uses the AI models and services provided by Microsoft Copilot to power the conversational experience. Business Central doesn't independently select or train the foundation models used by the shared Microsoft Copilot experience, and it doesn't use customer data from this experience to train those models.

Learn more about the models that power Microsoft Copilot and the data used to train the foundation models behind the experience in [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

Business Central provides product-specific application context, grounding, and tools that enable Microsoft Copilot to work with Business Central information. Some tools that Microsoft Copilot invokes in Business Central can use AI that's configured by Business Central settings, such as [semantic search](/dynamics365/business-central/dev-itpro/developer/semantic-search-feature-key). Microsoft Copilot doesn't control the model selection or configuration for these Business Central capabilities. This Application Card focuses on those Business Central-specific aspects rather than duplicating model and training-data information maintained for Microsoft Copilot.

## Performance

Microsoft Copilot in Business Central performs best when the user's question aligns with Business Central information that Copilot can access through its capabilities. Performance depends on the availability and quality of relevant Business Central data, the user's permissions, the application context available to Copilot, and whether the requested Business Central entity or operation is supported.

The primary intended input is natural-language text. Expected outputs include conversational text and, where supported, references or links to Business Central information. Business Central can also provide application context and retrieved business data to Microsoft Copilot as part of processing the user's request.

Different users can receive different results for similar questions because Business Central data access is governed by the identity and permissions of the signed-in user. Results can also vary depending on the company, page, record, extensions, personalization, and other application context available in the user's Business Central environment.

## Limitations

Understanding Microsoft Copilot in Business Central's limitations is crucial to determine whether it's used within safe and effective boundaries. The Business Central integration has product-specific limitations in addition to the limitations of the shared Microsoft Copilot experience.

For general limitations of Microsoft Copilot, including limitations associated with generative AI and generated responses, see [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

Business Central-specific considerations include:

- **Not all Business Central information is necessarily available**: Microsoft Copilot can only use Business Central information exposed through supported Business Central capabilities. Not every table, page, field, calculation, extension, or business process is necessarily available to the experience.

- **Results depend on user permissions**: The permissions of the signed-in user constrain Business Central data access. Two users asking the same question can therefore receive different results because they have access to different information.

- **Application context can be incomplete or ambiguous**: Microsoft Copilot might not always have enough Business Central context to determine which record, company, or business concept the user means. Provide additional context when a question could have multiple interpretations.

- **Customizations and extensions can affect results**: Business Central environments can contain extensions, custom fields, and customized business processes. The extent to which Microsoft Copilot can access these customizations can vary.

- **Grounded responses still require verification**: Business Central grounding can provide relevant application information to Microsoft Copilot, but the generated response can still be inaccurate, incomplete, or misleading. Inspect the underlying Business Central information before relying on a response for an important business decision.

- **Citations don't guarantee correctness**: A citation can help you inspect the Business Central information associated with a response, but the presence of a citation doesn't guarantee that the generated interpretation of that information is correct.

## Evaluations

Performance and safety evaluations assess whether AI applications are operating reliably and securely by examining factors such as the quality of generated responses and potential Responsible AI risks. The following evaluations were conducted with safety components already in place, which are also described in [Safety components and mitigations](#safety-components-and-mitigations).

Microsoft Copilot undergoes performance, quality, risk, and safety evaluations as part of the shared Microsoft Copilot application. For information about those evaluations, including the evaluation approaches and metrics used for Microsoft Copilot, see [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

The Business Central integration introduces product-specific grounding, application context, tools, permissions, and citations. The following sections therefore focus only on evaluations that are specific to the Business Central integration.

### Performance and quality evaluations

#### Performance and quality evaluation methods

### Risk and safety evaluations

Microsoft Copilot undergoes risk and safety evaluations for the shared Microsoft Copilot experience. For information about those evaluations, see [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

<!-- This section should document only risk and safety evaluations performed specifically for risks introduced by the Business Central integration.

Business Central-specific risk evaluation can include risks associated with inappropriate disclosure of Business Central information, permission-boundary failures, incorrect grounding, misleading citations, and any capability that can execute Business Central actions. -->

#### Risk and safety evaluation methods

### Custom evaluations

<!-- Relevant Business Central-specific evaluation areas can include tool selection, task completion, permission enforcement, grounding, citations, multi-turn behavior, localization, and application-context handling.

Don't infer evaluation metrics, thresholds, datasets, or results from the evaluations documented for Microsoft Copilot. -->

## Safety components and mitigations

Microsoft Copilot includes safety components and mitigations that apply to the shared Microsoft Copilot experience. Learn more about these common safeguards in [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card).

The following safeguards address risks that are specific to the Business Central integration:

- **Business Central permission enforcement**: Business Central-specific capabilities access application data by using the identity and permissions of the signed-in user. Using Microsoft Copilot doesn't grant the user additional access to Business Central data.

- **Grounding in Business Central information**: Business Central-specific capabilities retrieve relevant application information that Microsoft Copilot can use when answering Business Central questions. Grounding helps connect responses to information in the customer's Business Central environment.

- **References to source information**: Where supported, responses provide citations or links that allow users to inspect the underlying Business Central information. Users should use these references to verify important responses.

- **Human oversight for Business Central information**: Users should review AI-generated responses and verify important information against the underlying Business Central records before using it for business decisions.

- **Read-oriented capability boundary**: For the experience covered by the current scope of this Application Card, Business Central capabilities are intended to retrieve and explain information rather than independently modify Business Central data.

## Best practices for deploying and adopting Microsoft Copilot in Business Central

Responsible AI is a shared commitment between Microsoft and its customers. While Microsoft builds AI applications and platform services with safety, fairness, and transparency at the core, customers play a critical role in deploying and using these technologies responsibly within their own contexts. To support this partnership, we offer the following best practices for deployers and end users to help customers implement responsible AI effectively.

### Deployers and end users should

- **Exercise caution and evaluate outcomes when using Microsoft Copilot in Business Central for consequential decisions or in sensitive domains**: AI-generated responses can be inaccurate or incomplete. Users should verify important information against the underlying Business Central records and apply appropriate human oversight before using a response for a consequential business decision.

- **Evaluate legal and regulatory considerations**: Customers need to evaluate potential legal and regulatory obligations when using AI services and solutions. Microsoft Copilot in Business Central might not be appropriate for every industry, business process, or scenario.

### End users should

- **Exercise human oversight when appropriate**: Microsoft Copilot can make mistakes even when a response is grounded in Business Central information. Review responses and verify that they match the underlying Business Central records and the requirements of the task.

- **Be aware of the risk of overreliance**: Don't assume that a fluent or well-structured response is correct. Citations and Business Central links can help verify information, but users remain responsible for evaluating the response before acting on it.

- **Provide sufficient business context**: If Microsoft Copilot can't determine which customer, vendor, document, company, or other business concept a question refers to, provide that information explicitly. Clearer context can improve the relevance of the response.

- **Use citations to verify information**: When Microsoft Copilot provides a reference to Business Central information, inspect the referenced record or page when accuracy matters.

- **Provide feedback**: Use the feedback mechanisms available in Microsoft Copilot to report inaccurate, inappropriate, or unhelpful responses. Use the applicable Business Central support channels for Business Central-specific issues.

### Deployers should

- **Apply least-privilege access in Business Central**: Review Business Central permissions and make sure users have access only to the information required for their roles. Microsoft Copilot uses the user's Business Central access when retrieving Business Central information.

- **Evaluate the experience in the organization's environment**: Business Central environments can differ because of extensions, customizations, permissions, data volumes, localization, and business processes. Organizations should evaluate Microsoft Copilot against representative scenarios before relying on it for important workflows.

- **Review Microsoft Copilot requirements and controls**: Review [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card) and related Microsoft Copilot documentation for considerations that apply to the shared Microsoft Copilot experience.

- **Reevaluate controls when enabling action-taking capabilities**: Capabilities that create, modify, or delete Business Central data or execute actions introduce risks beyond information retrieval. Administrators should review the applicable controls, permissions, confirmation mechanisms, and Responsible AI documentation before enabling such capabilities.

## Learn more about Microsoft Copilot in Business Central

For additional guidance or to learn more about the responsible use of Microsoft Copilot in Business Central, we recommend reviewing the following documentation.

### Microsoft Copilot

- [Application card: Microsoft Copilot (for organizations)](/microsoft-365/copilot/microsoft-365-copilot-application-card)
- [Microsoft Copilot documentation](/copilot/)

The Microsoft Copilot Application Card is the authoritative source for shared Microsoft Copilot information, including the models used by the experience, general performance and safety evaluations, common safety components and mitigations, and general limitations. This Application Card supplements that information with details specific to the Business Central integration.

### Business Central

- [Use Microsoft Copilot](chat-with-copilot.md)
- [Configure Copilot and agent capabilities](enable-ai.md)
- [Business Central security and permissions](/dynamics365/business-central/dev-itpro/security/security-and-protection)
- [Business Central privacy and data handling](/dynamics365/business-central/dev-itpro/security/privacyfaq)

### Learn more about responsible AI

- [Microsoft AI principles](https://www.microsoft.com/ai/responsible-ai)
- [Microsoft responsible AI resources](https://www.microsoft.com/en-us/ai/responsible-ai-resources)
- [Microsoft Azure Learning courses on responsible AI](/training/browse/?terms=responsible%20ai) 