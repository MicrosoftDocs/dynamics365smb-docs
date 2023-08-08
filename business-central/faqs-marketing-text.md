---
title: FAQ for item marketing text suggestions
description: This FAQ provides information about the AI technology used in Business Central, along with key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 08/08/2023
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
---

# FAQ for item marketing text suggestions

These frequently asked questions (FAQ) describe the AI impact of the [!INCLUDE[feature-marketing-text-suggestions](includes/feature-marketing-text-suggestions.md)] feature in Business Central.

## What is item marketing text suggestions?

The [!INCLUDE[feature-marketing-text-suggestions](includes/feature-marketing-text-suggestions.md)] feature provides writing assistance for users responsible for authoring marketing text (also known as *copy*) on items in Business Central.

The feature is available on any item card in Business Central. To use it, just open an item and then select **Marketing Text** > **Create with Copilot**. This action automatically generates a text suggestion that's engaging, creative, and specific to the item that's shown. Suggestions are based on various inputs, including:

- The item's attributes, category, and name.
- Personal writing style preferences, like tone of voice, emphasized quality, format and length.

You can change the value of these input options to influence the outcome of the AI-generated text. Before you save a suggestion, you can easily review and edit it for accuracy or try another suggestion.

Some key benefits of this feature include:

- Decreases the time used on copy writing, which can accelerate time-to-market for items being sold in online shops.
- Unlocks creativity to provide more engaging product descriptions.
- Improves consistency of marketing material for product lines.

## What are the system's capabilities?

The [!INCLUDE[feature-marketing-text-suggestions](includes/feature-marketing-text-suggestions.md)] feature uses [Microsoft's Azure OpenAI Service](/azure/cognitive-services/openai/overview) to access powerful language models that analyze and generate natural language. These models have been trained on a wide body of text datasets. As a result, Copilot can generate suggested, personalized responses in English based on a minimal amount of input data, like an item's attributes, category, or description. 

## What is the system's intended use?

This feature is intended to assist users in creating marketing text for items in Business Central. Writers use the feature to quickly get compelling and engaging text suggestions, which are then reviewed and edited for accuracy. 

## How was item marketing text evaluated? What metrics are used to measure performance?

- The feature underwent substantial testing before it was released.
- It relies on user feedback to report inappropriate content and improve the functionality.

  - If you encounter inappropriate generated content, report it to Microsoft by using this feedback form: [Report abuse](https://msrc.microsoft.com/report/abuse?ThreatType=URL&IncidentType=Responsible%20AI&SourceUrl=https://dynamics.microsoft.com/supply-chainmanagement/overview/). 

    Microsoft might disable the Copilot-driven features for selected customers if abuse of the functionality is detected. 

  - We track user feedback on [!INCLUDE[feature-marketing-text-suggestions](includes/feature-marketing-text-suggestions.md)] to help us improve suggestions. 

    You provide feedback by using **Is this a good suggestion?** option on the **Create with Copilot** page in Business Central and selecting either a thumbs-up (I like it) or thumbs-down (Needs improvement). We gather the telemetry of these gestures for each AI output that you submit feedback for.

- The Azure OpenAI Service stores prompts and completions from the service to monitor for abusive use and to develop and improve the quality of Azure OpenAI's content management systems. [Learn more about our content management and filtering.](/azure/cognitive-services/openai/concepts/content-filter)

   Authorized Microsoft employees can access your prompt and completion data that has triggered our automated systems for the purposes of investigating and verifying potential abuse; for customers who have deployed Azure OpenAI Service in the European Union, the authorized Microsoft employees are located in the European Union. This data may be used to improve our content management systems. In the event of a confirmed policy violation, we may ask you to take immediate action to remediate the issue and to prevent further abuse. Failure to address the issue may result in suspension or termination of Azure OpenAI resource access.

   For more information, see [Data, privacy, and security for Azure OpenAI Service](/legal/cognitive-services/openai/data-privacy#abuse-and-harmful-content-generation).

## What are the limitations of [!INCLUDE[feature-marketing-text-suggestions](includes/feature-marketing-text-suggestions.md)]? How can users minimize the impact of the [!INCLUDE[feature-marketing-text-suggestions](includes/feature-marketing-text-suggestions.md)] limitations when using the system?

- Because the underlying technology behind the feature uses AI that has been trained on a wide range of sources, the generated content isn't always factual or suitable. Some suggestions may even include questionable or inappropriate content. It's your responsibility to review and edit generated suggestions to ensure it's accurate and appropriate.
- The feature only supports English. Inaccurate responses may be returned when users converse with the system in languages other than English.

## What operational factors and settings allow for effective and responsible use of the system?

There are a few things you can do to get the most out of the feature:

- Add more attributes to an item to promote the specific features and characteristics you're interested in.
- Change the options for tone of voice and emphasis of quality to match your personal preferences.
- Improve the item's description.
- Make sure the item is assigned the most suitable category.

To learn more, go to [Improve and tailor text suggestions](item-marketing-text.md#improve-and-tailor-text-suggestions).

> [!TIP]
> Always review the suggestions for accuracy before saving them and publishing them for public consumption.

## See also

- [Overview of AI-powered item marketing text (preview) with Copilot](ai-overview.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]