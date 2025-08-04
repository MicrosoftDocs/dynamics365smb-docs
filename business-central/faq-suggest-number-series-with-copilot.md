---
title: FAQ for Suggest Number Series with Copilot
description: This FAQ provides information about the AI technology used in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: faq
ms.search.form:
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: responsible-ai-faqs
---

# FAQ for Suggest Number Series with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI effect of the suggest number series feature in [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What is suggest number series with Copilot?

Suggest number series can help you create number series for all entities and documents in [!INCLUDE [prod_short](includes/prod_short.md)] based on structured input or natural language.

* Examples of entities are customers, vendors, and items.
* Examples of documents are quotes, orders, and invoices.

The feature isn't a general-purpose chat, but a highly specific and integrated experience that you can use to administrate number series. The feature offers two distinct skills that can help you create new or modify existing number series.

## What are the capabilities of suggest number series?

* Create new number series

   Use natural language to effortlessly set up new number series. Provide examples or masks to define how you envision your setup, and have Copilot draft suggestions for you to build upon.

* Modify existing number series

   Have Copilot help you maintain your existing number series. Extending number series can feel tedious. With Copilot, you can use natural language to modify number series and build upon the suggestions from Copilot.

* Prepare new number series for the next year

   Get ready for the next fiscal year by creating new number series ahead of time.

## What is the intended use of the suggest number series?

The suggest number series capability is intended for system administrators who set up and maintain number series in [!INCLUDE [prod_short](includes/prod_short.md)]. It's a tool to transform requirements written in natural language into the number series structure in [!INCLUDE [prod_short](includes/prod_short.md)].

## How was suggest number series evaluated? What metrics are used to measure performance?

The feature underwent extensive testing where numerous prompts in US English representing both typical use and use by bad actors. Testing was based on [!INCLUDE [prod_short](includes/prod_short.md)] demonstration data and a large labeled product catalog available as open source.

This feature is built in accordance with Microsoft's Responsible AI Standard. [Learn more about responsible AI from Microsoft](https://aka.ms/RAI).

## What are the limitations of suggest number series? How can users minimize the effect of the limitations when using the system?

The feature works best when you use terminology known to [!INCLUDE [prod_short](includes/prod_short.md)]. Using alternative terminology might produce results that aren't useful.

* Available geographies

   This Copilot feature is available in all supported [Business Central countries/regions](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). However, for customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing their data to move across boundaries for [!INCLUDE [prod_short](includes/prod_short.md)] to connect to Azure OpenAI service. Learn more at [Copilot data movement across geographies](ai-copilot-data-movement.md).

* Available languages

   [!INCLUDE [copilot-language-support-en-only](includes/copilot-language-support-en-only.md)]

## What operational factors and settings allow for effective and responsible use of the feature?

AI-powered suggestions might be incorrect or incomplete. You should always review the accuracy of Copilot's suggestions before you choose whether to keep them. Copilot’s suggestions aren't saved to the [!INCLUDE [prod_short](includes/prod_short.md)] database until you choose the **Keep it** button and exit the Copilot window. You can edit and correct any suggestions before you choose to keep it, or after they're inserted as No. Series.

### What is expected of administrators and end-users when using suggest number series?

Each individual user chooses whether or not to use suggest number series. Even if an administrator enables the feature and it's available, you can choose to use it always, sometimes, or never.  

Administrators make the overall decision on whether to use Copilot capabilities in [!INCLUDE [prod_short](includes/prod_short.md)]. If administrators enable Copilot, they should be sure to grant access to the appropriate users.

> [!NOTE]
> * We don't support this feature in [!INCLUDE [prod_short](includes/prod_short.md)] on-premises or private cloud.
> * Partner's can't extend this feature. That means partner developers can't modify, replace, or extend it.

## Is Copilot the only means to create number series?  

No, the use of Copilot is optional. [!INCLUDE [prod_short](includes/prod_short.md)] offers non-AI-powered ways to create number series. Organizations can use both approaches at the same time. To learn more, go do [Create number series](ui-create-number-series.md).

## How do I give feedback about AI-generated content?  

Each time Copilot provides suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the **Like** and **Dislike** buttons. Your feedback remains anonymous and we use this data to improve the quality of the service.

## Related information

[Configure Copilot and agent capabilities](enable-ai.md)  
[Responsible AI FAQs for Dynamics 365 Business Central](responsible-ai-overview.md) 
