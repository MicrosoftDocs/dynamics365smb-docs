---
title: Responsible AI FAQ for Autofill (preview)
description: Learn about the AI technology of Autofill in Business Central, considerations, details about how AI is used, tested, evaluated, and limitations.
ms.date: 07/24/2025
ms.custom: 
  - responsible-ai-faqs
ms.topic: faq
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI, chat 
---

<!-- The Report Abuse link in line 73 isn't opening when I try. Please check this. -->


# Responsible AI FAQ for Autofill (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI effect of Copilot’s Autofill feature in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

<!-- [!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/preview-note-d365.md)]-->

## What is Autofill?

Manually entering data can be time-consuming and error-prone, both for casual users of Business Central and expert users who are tasked with entering records throughout their workday.  

Microsoft Copilot is an AI-powered assistant that sparks creativity, boosts productivity, and eliminates tedious tasks. Copilot uses AI to suggest and fill out field values automatically on your page, instead of typing or looking up things across screens. You can choose to keep or discard the suggestions. 

## What are the capabilities of Autofill?

[!INCLUDE[autofill-suggestions-source](includes/autofill-suggestions-source.md)]

> [!IMPORTANT]
> Copilot runs under your user context. It only has access to data that you already have access to. Your assigned permissions and all other security and compliance controls also apply when you use Copilot.

> [!IMPORTANT]
> Web Search is available from version 26.4 and above. The feature requires that you turn on **Bing Search** on the **Copilot & agent capabilities** page. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

## What is the intended use of Autofill?

Autofill is an assistive feature intended to help people enter data into Business Central. It isn't designed to run autonomously and enter data on behalf of others. Since the suggestions aren't automatically saved to Business Central, you must review and accept each field for it to be saved. 

When you choose to keep a suggestion, you're saving the change to Business Central as if you entered that value yourself without the assistance of Copilot.

When you leave the page or record, any suggestions that you didn't choose to keep are automatically discarded. 

Suggested values are displayed directly within the field editing experience, making it easy for you to review each suggestion and choose to keep, discard, or replace the suggestion. 

## How was Autofill evaluated? What metrics are used to measure performance? 

This feature is built in accordance with Microsoft's Responsible AI Standard. Learn more about responsible AI from Microsoft in [Empowering responsible AI practices](https://aka.ms/RAI).

The feature underwent extensive AI testing using Business Central's demonstration data and other fictitious business data. Testing covered various fields and pages from Business Central. Copilot’s output was evaluated for accuracy of suggested values, selection of the appropriate mechanism to suggest a value, grounding of suggested values in database data, and other metrics.

To ensure customer safety and data protection, this feature underwent rigorous testing to detect and deflect harmful content, jailbreaks, and other risks.

## How does Microsoft monitor the quality of generated content?

Microsoft has various automated systems in place to ensure that output from Copilot is of the highest quality. Automated systems also detect abuse, and ensure safety for our customers and their data by filtering harmful content.

Microsoft might disable the Copilot features for selected customers if abuse of the functionality is detected.

Users have the opportunity to provide feedback to every Copilot response and report inaccurate or inappropriate content to help Microsoft improve this feature. If you encounter inappropriate content, report it to Microsoft by using this feedback form: [Report abuse](https://go.microsoft.com/fwlink/?linkid=2249810). We analyze user feedback on the feature and use it to help us improve responses.

You provide feedback by using the **like** (thumbs up) or **dislike** (thumbs down) icon in the information about an individual suggestion or for all suggestions in the group of fields.

## What are the AI limitations of Autofill? How can users minimize the effect of the limitations when using the system?

- **General AI limitations**
  AI systems are valuable tools but they're nondeterministic. The content they generate might not be accurate. It's important to use your judgment to review and verify responses before making decisions that could affect stakeholders like customers and partners. 

- **Geographic and language availability**

  [!INCLUDE [copilot-geo-and-language-availability-en-only](includes/copilot-geo-and-language-availability-en-only.md)]

- **Certain industry, product, and subject limitations**

  Organizations that operate in some business domains, such as medical, drugs, legal, and weapons, might experience lower quality or limited output from Copilot due to the sensitive nature of that domain.

## What data does Autofill collect and how is it used?

Business Central collects the minimum data required for Microsoft to offer the service. 

- Microsoft collects anonymized information about decisions made by Copilot and your choice to keep or discard a suggestion. It doesn't collect suggested field values or other company data used by Copilot to provide suggestions.
- Microsoft doesn't use your business data to train the foundational models for the benefit of others. Learn more in [Dynamics 365 terms for Azure OpenAI-powered features](https://go.microsoft.com/fwlink/?linkid=2236010).
  
## How does Autofill treat data residency?

The Autofill feature relies on Azure OpenAI Service and Bing Search to provide suggestions.

- Azure OpenAI Service  
  Learn more about data residency and Azure OpenAI Service in [Azure OpenAI Service and Business Central data](azure-openai-data.md) and [Copilot data movement across geographies](ai-copilot-data-movement.md).

- Bing Search  
  Service endpoints are available in the US only and Bing Search operates under different terms. If your [!INCLUDE[prod_short](includes/prod_short.md)] environment is deployed to any other Azure geography, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Bing Search service outside your environment’s geographic region or compliance boundary. When you use Autofill to find suggestions for fields of public domain, only the input prompt is sent to the Bing Search service. This information is processed and not stored for more than one day.

  To prevent Autofill from connecting to the Bing Search service, turn off the **Enable Bing Search** toggle on the **Copilot & agent capabilities** page. Learn more about how Copilot searches the web using Bing in [Searching the web with Copilot (preview)](ai-search-web-copilot.md).

## What does Autofill offer for security?

When Autofill is used on fields of public domain, it searches the web powered by Bing Search. To ensure security and safety, [!INCLUDE[prod_short](includes/prod_short.md)] applies various mechanisms such as content filtering and malicious site detection to reduce risk from these websites.

Learn more about how Copilot searches the web in [Searching the web with Copilot (preview)](ai-search-web-copilot.md).

## Related information

[Autofill fields with Copilot](autofill-fields-with-copilot.md)  
[FAQ for Copilot data security and privacy](/dynamics365/faqs-copilot-data-security-privacy?toc=/dynamics365/business-central/toc.json)  
[Azure OpenAI Service and Business Central data](azure-openai-data.md)  
[Copilot data movement across geographies](ai-copilot-data-movement.md)  
