---
title: AI-powered item marketing text (preview) with Copilot FAQ
description: Get answers to common questions about the AI-generated text capabilities with Copilot.
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: faq 
ms.date: 04/03/2023
ms.custom: bap-template 
author: jswymer
---

# AI-powered item marketing text (preview) with Copilot FAQ

[!INCLUDE[ai-preview](includes/ai-preview.md)]

This article uses questions and answers to explain important aspects about the AI technology behind Copilot and the text it generates.

<!--## [General](#tab/general)-->

## What is Copilot?

Copilot provides AI-generated text suggestions for items in Business Central. It's intended for users who write marketing text for items to help them produce engaging and compelling content. Some key benefits include:

- Decreases the time used on copy writing, which can accelerate time-to-market for items being sold in online shops.
- Unlocks creativity to provide more engaging product descriptions.
- Improves consistency of marketing material for product lines.

Users should consider the AI-generated text as a suggestion that must be reviewed and edited for accuracy before it's publicly available.

## Why isn't Copilot available for marketing text on my items in Business Central?

For Copilot to be available, the following requirements must be met:

- The language you're using in Business Central must be English. Any of the available English locales will work, like English (United States), English (United Kingdom), or English (South Africa).

  To change the language, in the upper-right corner, select the **Settings** icon ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center") > **My Settings** > **Language**. For more information, go to [Change Basic Settings](ui-change-basic-settings.md#language).
- You must be using Business Central online version 22 or later (if you're an existing customer) or a trial.  <!--**22.0.54157.54311 (Preview - Copilot edition)**-->

   To check the version, select the question mark in the upper-right corner, then select **Help & Support**. Under **Troubleshooting**, look for the application version. For information about how to get the correct preview version, go to [Get started with a Business Central preview version](ai-preview-getstarted.md).
- The **Create AI-powered product descriptions with Copilot** feature must be enabled.

   For more information, go to [Enable or disable the "Create AI-powered product descriptions with Copilot" feature](enable-ai.md#enable-or-disable-create-ai-powered-product-descriptions-with-copilot).
- An admin has consented to the terms and conditions.

   For more information, go to [Consent to or reject the preview and privacy terms and conditions for all users](enable-ai.md#consent-to-or-reject-preview-and-privacy-terms-and-conditions-for-all-users).

## Is Copilot available for preview in Business Central on-premises?

No, it's currently not supported in Business Central on-premises.

## How does Copilot work, where does the suggested text come from?

Copilot uses [Microsoft's Azure OpenAI Service](/azure/cognitive-services/openai/overview) to access powerful language models that analyze and generate natural language. These models have been trained on a wide body of text datasets. As a result, Copilot can generate suggested, personalized responses in English based on a minimal amount of input data, like an item's attributes, category, or description. 

## What's the quality of the text suggested by Copilot?

Because the underlying technology behind Copilot uses AI that has been trained on a wide range of sources, the generated content isn't always factual or suitable. Some suggestions may even include questionable or inappropriate content. It's your responsibility to review and edit generated suggestions to ensure it's accurate and appropriate.

For information about inappropriate suggestions, go to [What's done about abusive and harmful text suggestions?](/dynamics365/business-central/ai-faq?&tabs=oversight#whats-done-about-abusive-and-harmful-text-suggestions).

## How can I improve the suggestions I get from Copilot?

There are a few things you can do to get the most out of suggestions from Copilot:

- Add more attributes to an item to promote the specific features and characteristics you're interested in.
- Change the options for tone of voice and emphasis of quality to match your personal preferences.
- Improve the item's description.
- Make sure the item is assigned the most suitable category.

To learn more, go to [Improve and tailor text suggestions](item-marketing-text.md#improve-and-tailor-text-suggestions).

## What if I'm not satisfied with the generated text?

To help us improve the text, select **Is this a good suggestion?** on the **Create with Copilot** page, which you can answer with a thumbs-up (I like it) or thumbs-down (Needs improvement).

![Shows an item card with Marketing Text pane](media/create-with-copilot-window-feedback.png)

## Can admins disable Copilot? If so, how?

Business Central offers admins two ways to disable Copilot in the preview:

- Disagree to the Azure OpenAI privacy notice for all users.

  or

- Turn off the **Create AI-powered product descriptions with Copilot** feature on the **Feature Management** page.

To learn more, go to [Configure AI-powered item marketing text (preview) with Copilot as an admin](enable-ai.md).

## Does Copilot work with languages other than English?

Currently, Copilot only supports English. Inaccurate responses may be returned when users converse with the system in languages other than English.

## Where can I read more about things like data collection, privacy, and what's done about abusive text suggestions?

Go to [Responsible AI FAQ for item marketing text suggestions](faqs-marketing-text.md).
<!--
## [Human oversight](#tab/oversight)

### What's done about abusive and harmful text suggestions?

The Azure OpenAI Service stores prompts and completions from the service to monitor for abusive use and to develop and improve the quality of Azure OpenAI’s content management systems. [Learn more about our content management and filtering.](/azure/cognitive-services/openai/concepts/content-filter)

Authorized Microsoft employees can access your prompt and completion data that has triggered our automated systems for the purposes of investigating and verifying potential abuse; for customers who have deployed Azure OpenAI Service in the European Union, the authorized Microsoft employees will be located in the European Union. This data may be used to improve our content management systems. In the event of a confirmed policy violation, we may ask you to take immediate action to remediate the issue and to prevent further abuse. Failure to address the issue may result in suspension or termination of Azure OpenAI resource access.

For more information, see [Data, privacy, and security for Azure OpenAI Service](/legal/cognitive-services/openai/data-privacy#abuse-and-harmful-content-generation).

### Can I opt out of the logging and human review process?  

As part of providing the Azure OpenAI previews, Microsoft will process and store customer data submitted to the service, as well as output content, for purposes of monitoring for and preventing abusive or harmful uses or outputs of the service; and for developing, testing, and improving capabilities designed to prevent abusive use of or harmful outputs from the service. 

Authorized Microsoft personnel may review data that has triggered our automated systems to investigate and verify potential abuse, and may engage in limited random sampling of terms that aren't flagged by our automated systems to ensure the systems are working properly. Authorized Microsoft personnel may also access and use this data to improve our systems that monitor for and prevent abusive or harmful uses or outputs of the service. Read more on [preview terms](https://go.microsoft.com/fwlink/?linkid=2189520).

## [Privacy](#tab/privacy)

### What data does the capability collect? How is the data used?

The capability collects your answer to the **Is this a good suggestion?** question on the **Create with Copilot** page, which can be either a thumbs-up (I like it) or thumbs-down (Needs improvement).

We use this data to evaluate and improve the quality of the capability. More information on what data is collected is available in the [preview terms](https://go.microsoft.com/fwlink/?linkid=2189520).

![Shows an item card with Marketing Text pane](media/create-with-copilot-window-feedback.png)
---
-->


## See also

[Overview of AI-powered item marketing text with Copilot](ai-overview.md)  
[Configure AI-powered item marketing text with Copilot as an admin](enable-ai.md)  
[Create marketing text to items using Copilot](item-marketing-text.md)  

