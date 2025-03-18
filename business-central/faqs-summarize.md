---
title: Responsible AI FAQ for summarize (preview)
description: Learn about the AI technology of summarize in Business Central, considerations, details about how AI is used, tested, evaluated, and limitations.
ms.date: 03/10/2025
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI, chat 
---

# Responsible AI FAQ for summarize (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of
Copilot’s summarize feature in Business Central.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is Summarize?

Business Central users often need to get an overview of their data and what most urgently need their attention, in order to decide how to proceed with their tasks in the most optimal way.

Microsoft Copilot is an AI-powered assistant that sparks creativity, boosts productivity, and eliminates tedious tasks. Copilot uses AI to generate an insightful summary of any record, making it effortless for people to learn what is important or urgent.

## What are the capabilities of Summarize?

- A concise summary is displayed as a FactBox on most card and document pages in Business Central. This typically provides the top two or three insightful points as brief sentences.

- From the initial summary, users can ask for more insights, where Copilot displays more points in the Copilot pane. Users can ask follow-up questions to learn how to use Business Central to take action based on those insights.

- No matter where the summary is displayed, Copilot makes it easy to review and explore the datapoints referenced in the summary, where
  this data is hyperlinked and can be previewed or help you navigate to the source where you can view the details or take action.

While the summary text is AI-generated, each insight is grounded in real data from Business Central. Copilot inherits the user’s data permissions and can’t read any more data than the user already has access to.

## What is the intended use of Summarize?

This is an assistive feature intended to help people understand their business data, reduce the time it takes to sift through Business Central’s rich dataset, and make Business Central easier to use. It isn’t designed to make decisions, provide recommendations or advise on how to act or optimize your business.

Summaries are not used to automatically trigger action on behalf of the user or the organization, and they are not persisted to the database for other automated functions to use.

## How was Summarize evaluated? What metrics are used to measure performance?

This feature is built in accordance with Microsoft's Responsible AI Standard. Learn more about responsible AI from Microsoft.

The feature underwent extensive AI testing using Business Central's demonstration data supplemented with additional, fictitious business data and volume data. Testing primarily covered various fields and pages from Business Central’s base application, with some testing also carried out on custom pages and fields. Copilot’s output was evaluated for accuracy of ranked insights, use of  language, grounding of values in database data, and other metrics.

To ensure customer safety and data protection, this feature underwent rigorous testing to detect and deflect harmful content, jailbreaks, and other risks.

## How does Microsoft monitor the quality of generated content?

Microsoft has various automated systems in place to ensure that output from Copilot is of the highest quality. Automated systems also detect abuse, and ensure safety for our customers and their data by filtering harmful content.

Microsoft might disable Copilot features for specific customers if abuse is detected.
 
Users have the opportunity to provide feedback to every Copilot response and report inaccurate or inappropriate content to help Microsoft improve this feature. If you encounter inappropriate content, you can also report it to Microsoft by using this feedback form: Report abuse. We analyze user feedback on the feature and use it to help us improve responses.

You provide feedback by using the like (thumbs up) or dislike (thumbs down) icons that are displayed alongside generated content.

## What are the AI limitations of Summarize? How can users minimize the impact of the limitations when using the system?

- General AI limitations

AI systems are valuable tools but they're nondeterministic. The content they generate might not be accurate. It's important to use your judgment
to review and verify responses before making decisions that could affect stakeholders like customers and partners.

- Geographic and language availability

  This Copilot feature is available in all supported Business Central countries/regions. However, the feature uses Microsoft Azure OpenAI
  Service, which is currently available for Business Central in some geographies. If your environment is located in a country/region where
  Azure OpenAI Service isn't available, administrators must allow data to move across geographies. Learn more at Copilot data movement across geographies.
  
  This feature was validated and is supported in English language. While it can be used in other languages, it might not function as intended. Language quality might vary based on the user's interaction or system settings, which might impact accuracy and the user experience.
  
  Learn more about geographic and language availability at [Copilot international availability](https://aka.ms/bapcopilot-intl-report-external).

- Certain industry, product, and subject limitations

  Organizations that operate in some business domains, such as medical, drugs, legal, and weapons, might experience lower quality or limited output from Copilot due to the sensitive nature of that domain. 

- Summaries about people

  Summaries about people, such as customers, vendors or employees in Business Central, may result in limited output from Copilot due to additional safety mechanisms designed to reduce risk of inaccuracies. Even though Copilot is not designed to provide recommendations or conclusions about people, your should use your judgment to review and verify responses before making decisions.

## What data does Summarize collect and how is it used?

Business Central collects the minimum data required for Microsoft to offer the service.

- Microsoft collects anonymized information about decisions made by Copilot and your interactions with the feature. It doesn't collect summary texts or other company data used or collected by  Copilot to generate summaries.

- Microsoft doesn't use your business data to train the foundational models for the benefit of others. Learn more in [Dynamics 365 terms for Azure OpenAI-powered features](https://go.microsoft.com/fwlink/?linkid=2236010).

## Related information

[FAQ for Copilot data security and privacy](https://review.learn.microsoft.com/en-us/dynamics365/faqs-copilot-data-security-privacy?toc=/dynamics365/business-central/toc.json)  
[Azure OpenAI Service and Business Central data](https://review.learn.microsoft.com/en-us/dynamics365/business-central/azure-openai-data)  
[Copilot data movement across geographies](https://review.learn.microsoft.com/en-us/dynamics365/business-central/ai-copilot-data-movement)  
