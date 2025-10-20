---
title: FAQ for suggest item substitutions with Copilot
description: This FAQ provides information about an AI feature in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: faq
ms.search.form:
ms.date: 10/13/2025
ms.update-cycle: 180-days
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: responsible-ai-faqs
---

# FAQ for suggest item substitutions with Copilot

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of the sales line suggestions feature in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is suggest item substitutions with Copilot?

In a business landscape that changes fast, companies often need to evolve the portfolio of products they sell. Whether it's adding new products, changing existing products, or adding entire product lines and categories, it's often time consuming to create and manage product (item) information.  

Reusing information from similar items can be a good option and Copilot can help you to identify similar items. An extra benefit is that suggest item substitution also reduces the risk of creating duplicated entries on the Items list page.

## What are the capabilities of suggest item substitutions with Copilot?

* Substitutions

You can store similar or interchangeable products on the **Item Substitution Entry** page. Copilot helps to add this information for current products by searching for similar ones in the database.

## What is the intended use of suggest item substitutions with Copilot?

* Substitutions

Intended to suggest item substitutions based on the description of the current item.  

Because the average number of items (products/services) for [!INCLUDE [prod_short](includes/prod_short.md)] customers is 10.000, finding the right ones might be tough without prior experience or knowledge. The way [!INCLUDE [prod_short](includes/prod_short.md)] stores data doesn’t make things easier because you need to do multiple search or filtering exercises on the different pages that store product data.

To assist you in finding items, Copilot extracts keywords, other search terms, and synonyms from the product (item) description, and uses embeddings to find similar items in the database.

## How was suggest item substitutions with Copilot evaluated? What metrics are used to measure performance?

The feature underwent extensive testing with numerous prompts in US English representing both typical use and use by bad actors. Testing was based on [!INCLUDE [prod_short](includes/prod_short.md)] demonstration data and a large labeled product catalog available as open source.

This feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## What are the limitations of suggest item substitutions with Copilot? How can users minimize the impact of the suggest item substitutions with Copilot limitations when using the system? 

Find products works best in the English language. While you can use this feature in any of the languages that [!INCLUDE [prod_short](includes/prod_short.md)] supports, item searches in other languages might be less accurate.

If your industry or domain overlaps with what Microsoft considers sensitive topics (such as drugs, violence, adult entertainment, and so on) Copilot might defer to neutral, curated responses, or give inaccurate responses.

Suggest item substitutions only fills in the **Substitute Type**, **Substitute No.**, and **Description** fields. The **Variant Code** field isn't currently supported. If you can ship a product in two different colors, for example, Copilot finds the needed product but leaves the **Variant Code** field empty. You need to fill in the field manually.  

Catalog items aren't currently supported.

The maximum number of results is currently limited to 10.

How you name your products can affect the output. For example, using cryptic abbreviations versus friendly names can reduce output quality.

For products, the following table lists the tables and fields that Copilot searches.

|Table  |Fields  |
|---------|---------|
|Items     | * No.<br>* Description<br>* Description 2<br>* Search Description<br>* GTIN<br>* Vendor Item Number        |
|Item Variants    |* Code<br>* Description<br>* Description 2<br>         |
|Item Reference     |* Reference No.<br>* Description<br>* Description 2         |
|Item Attributes     |* Name<br>* Value         |
|Item Category     |* Code<br>* Description<br>* Parent Category - 1 level         |
|Item Translation     |* Language<br>* Description<br>* Description 2         |
|Item Identifier     |* Code         |
|Extend Text Line     |* Text         |

## In which geographies and languages is Suggest item substitutions available?

* Available geographies

This Copilot feature is available in all supported [Business Central countries/regions](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). However, for customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing their data to move across boundaries for Business Central to connect to Azure OpenAI service. Learn more at [Copilot data movement across geographies](ai-copilot-data-movement.md).

* Available languages

[!INCLUDE [copilot-language-support-en-only](includes/copilot-language-support-en-only.md)]

## What operational factors and settings allow for effective and responsible use of the feature?

AI-powered suggestions might sometimes be incorrect or incomplete. You should always review the accuracy of Copilot's suggestions before you choose whether to keep them. Copilot’s suggestions aren't saved to the [!INCLUDE [prod_short](includes/prod_short.md)] database until you choose the **Keep it** button and exit the Copilot window. You can edit and correct any suggestions before you choose to keep it, or after they're inserted in item substitution page.

## What is expected of administrators and end-users when using Suggest item substitutions?

Each individual user chooses whether or not to use suggest item substitutions. Even when the feature is enabled by administrators and available, you can choose to use it always, sometimes, or never.

Administrators make the overall decision on whether to use Copilot capabilities in [!INCLUDE [prod_short](includes/prod_short.md)]. If administrators enable Copilot, they should be sure to grant access to the appropriate users.

> [!NOTE]
> * We don't support this feature in [!INCLUDE [prod_short](includes/prod_short.md)] on-premises or private cloud.
> * Partner's can't extend this feature. That means partner developers can't modify, replace, or extend it.

## Is Copilot the only means to create item substitution entries? 

No, use of Copilot is optional. [!INCLUDE [prod_short](includes/prod_short.md)] offers non-AI-powered ways to insert item substitution entries. Organizations can use both approaches at the same time.

## How do I give feedback about AI-generated content?

Each time Copilot provides suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the Like and Dislike buttons. Your feedback remains anonymous and we use this data to improve the quality of the service.

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Responsible AI FAQs for Dynamics 365 Business Central](responsible-ai-overview.md)
