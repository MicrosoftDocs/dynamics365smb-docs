---
title: Marketing text suggestions with Copilot overview
description: Get an overview of the AI content-generating capabilities in Business Central.  
author: jswymer 
ms.author: jswymer 
ms.reviewer: jswymer
ms.topic: overview 
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.custom: bap-template 
ms.collection:
  - bap-ai-copilot
---
# Marketing text suggestions with Copilot overview

<!--[!INCLUDE[ai-preview](includes/ai-preview.md)]-->

This article gives an overview the AI-powered capability provided by Copilot in Business Central.

## What is AI-powered item marketing text with Copilot

Copilot provides AI-powered writing assistance for Business Central users responsible for authoring marketing text (product descriptions) on items sold in online shops, like Shopify. With the click of a button, Copilot generates text that's engaging and creative, and that highlights key attributes of the specific item. With a bit of reviewing and editing, it's ready to publish.

Copilot uses Microsoft Azure OpenAI Service to access language models that recognize, predict, and generate text that's based on trained datasets. Learn more at [Microsoft Azure OpenAI Service](/azure/cognitive-services/openai/overview).

<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=aeb1c87f-2489-41f8-a3cf-28ed5e4196e4]

*The video doesn't exactly reflect how the feature currently works or looks in the product. The feature has changed since the video was produced. But it gives you a general idea of the feature and what you can use it for.*
  
## Where it's used

Copilot is available on item cards in Business Central. In Business Central, items are like products in other applications and shops. Each item can be managed from a card where you enter details about the item, like its dimensions, cost, or picture. This card also includes a box for entering marketing text. This marketing text can be published to your online shop to promote the item. Here's where Copilot comes in. By just selecting the **Draft with Copilot** action on the item card, Copilot will generate an intelligent draft text for you. Once you get the first draft, you can run Copilot again and again until you get a draft you like. When you have suggestion you like, you review and edit it for accuracy, then save it.

If Business Central is set up to connect to your online store on Shopify, you can take this text even further by publishing it with the item directly to your store by selecting **Add to Shopify**.

## Why and how to use it

AI-generated text can help you accelerate the time-to-market of products in online shops by limiting time used on copy writing. Some key benefits include:

- Helps users overcome writer's block by getting them started with an intelligent draft.
- Unlocks creativity to provide more engaging product descriptions.
- Improves consistency of marketing content for product lines.

You should consider the AI-generated text as a *suggestion only*. Suggestions can, in some cases, contain mistakes and even inappropriate text, so human oversight and review are required. Before you make the text publicly available, you must review it for accuracy and make appropriate changes.

## Supported languages

[!INCLUDE[copilot-language-support.md](includes/copilot-language-support.md)]

## Current limitations

Poor suggestions can result when vague or generic product names are used and specifics about an item are missing, like key attributes or a category.

<!-- Partner extensibility of the AI capability by using AL code isn't supported.-->

## Next steps

To get started, you'll need a Business Central (v23.1 and later) environment that's enabled with Copilot.

- If you're an existing Business Central customer, your Business Central admin will have to set up an environment that's enabled for marketing text suggestions. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

- If you're not a Business Central customer but want to try it out, you can sign up for a free trial. Learn more in [Sign up for a free Dynamics 365 Business Central trial](trial-signup.md).

Once you have an environment or trail that ready, go to [Add marketing text to items with Copilot](item-marketing-text.md).  

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Add marketing text to items with Copilot](item-marketing-text.md)  
[FAQ for marketing text suggestions](faqs-marketing-text.md)  
[Get Started with the Shopify Connector](shopify/get-started.md)  
