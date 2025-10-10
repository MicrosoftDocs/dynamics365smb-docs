---
title: Responsible AI FAQ for summarize (preview)
description: Learn about the AI technology of summarize in Business Central, considerations, details about how AI is used, tested, evaluated, and limitations.
ms.date: 09/14/2025
ms.custom: 
  - responsible-ai-faqs
ms.topic: faq
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI, chat 
---

# Responsible AI FAQ for summarize (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of Copilot’s summarize feature in Business Central.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is summarize?

Business Central users often need an overview of their data and what urgently needs their attention to decide how to proceed with their tasks optimally.

Microsoft Copilot is an AI-powered assistant that sparks creativity, boosts productivity, and eliminates tedious tasks. Copilot uses AI to generate an insightful summary of any record, making it effortless for people to learn what is important or urgent.

## What are the capabilities of summarize?

- A concise summary is displayed as a FactBox on most card and document pages in Business Central. It typically provides the top two or three insightful points as brief sentences.

- From the initial summary, users can select **Show more** to get more information about the record. The Copilot pane opens and generates additional points of interest.

- When any summary is displayed, Copilot makes it easy to review and learn about the facts referenced by the summary. These references are hyperlinked, so that users can quickly view or navigate to the source where they can explore details and take action.

While the summary text is AI-generated, each insight is grounded in factual data from Business Central. Copilot inherits the user's data permissions and can’t read any more data than the user already has access to.

## What is the intended use of summarize?

This feature helps people understand their business data, reduces the time it takes to sift through Business Central’s rich dataset, and makes Business Central easier to use. It isn't designed to make decisions on your behalf, provide recommendations, or advise on how to act or optimize your business.

Summaries don't automatically trigger actions on behalf of the user or the organization, and they don't persist to the database for other automated functions to use.

## How was summarize evaluated? What metrics are used to measure performance?

This feature is built in accordance with Microsoft's Responsible AI Standard. Learn more about responsible AI from Microsoft in [Empowering responsible AI practices](https://aka.ms/RAI).

The feature underwent extensive AI testing using Business Central's demonstration data supplemented with extra, fictitious business data and volume data. Testing primarily covered various fields and pages from Business Central’s base application, with some testing also carried out on custom pages and fields. Copilot’s output was evaluated for accuracy of ranked insights, use of language, grounding of values in database data, and other metrics.

To ensure customer safety and data protection, this feature underwent rigorous testing to detect and deflect harmful content, jailbreaks, and other risks.

## How does Microsoft monitor the quality of generated content?

Microsoft has various automated systems to ensure that output from Copilot is of the highest quality. Automated systems also detect abuse and ensure safety for our customers and their data by filtering harmful content.

Microsoft might turn off Copilot features for specific customers if abuse is detected.
 
Users can provide feedback on every Copilot response and report inaccurate or inappropriate content to help Microsoft improve this feature. If you encounter inappropriate content, report it to Microsoft using this feedback form: [Report abuse](https://go.microsoft.com/fwlink/?linkid=2249810). We analyze user feedback and use it to improve responses.

You provide feedback by using the like (thumbs up) or dislike (thumbs down) icons that are displayed alongside generated content.

## What are the AI limitations of summarize? How can users minimize the impact of the limitations when using the system?

- General AI limitations

  AI systems are valuable tools but they're nondeterministic. The content they generate might not be accurate. It's important to use your judgment
to review and verify responses before making decisions that could affect stakeholders like customers and partners.

- Geographic and language availability

  [!INCLUDE[copilot-language-support](includes/copilot-language-support.md)]

- Certain industry, product, and subject limitations

  Organizations that operate in some business domains, such as medical, drugs, legal, and weapons, might experience lower quality or limited output from Copilot because of the sensitive nature of that domain.

- Summaries about people

  Summaries about people, such as customers, vendors, or employees in Business Central, might result in limited output from Copilot because of other safety mechanisms designed to reduce the risk of inaccuracies. Even though Copilot isn't designed to provide recommendations or conclusions about people, you should use your judgment to review and verify responses before making decisions.

[!INCLUDE[ai-data-collection](includes/ai-data-collection.md)]

## Related information

[Summarize records with Copilot](summarize-with-copilot.md)  
[FAQ for Copilot data security and privacy](/dynamics365/faqs-copilot-data-security-privacy?toc=/dynamics365/business-central/toc.json)  
[Azure OpenAI Service and Business Central data](azure-openai-data.md)  
[Copilot data movement across geographies](ai-copilot-data-movement.md)  
