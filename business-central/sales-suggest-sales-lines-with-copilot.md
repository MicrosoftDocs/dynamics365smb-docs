---
title: Suggest sales lines with Copilot
description: Learn how to suggest lines on sales orders with Copilot.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.search.keywords: Copilot, AI, sell
ms.search.form:
ms.date: 02/02/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
ms.collection: bap-ai-copilot
---

# Suggest lines on sales orders with Copilot

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

This article explains how to create sales orders faster by letting Copilot suggest the items to add to lines on sales documents for your customers.

## About sales line suggestions with Copilot

Copilot can assist with creating lines on sales documents such as sales quotes, sales orders, and invoices based on structured input or natural language.

* Take advantage of Copilot's ability to handle versatile input methods.

    Copilot can accept various input methods, including free text, files, or prebuilt prompt suggestions. This flexibility lets you interact with [!INCLUDE [prod_short](includes/prod_short.md)] in ways that are convenient for you.
* Leverage Copilot's intelligent processing.

    Copilot understands your input and uses it to suggest sales lines. This intelligent processing eliminates the need for manual data entry, which reduces errors and saves time. Additionally, Copilot can suggest sales lines based on how often, and how recently, you sell something to the customer on the sales document.

## Prerequisites

* Sales line suggestion with Copilot is enabled and activated. This task is done by an administrator. To learn more about how to enable AI capabilities, go to [Configure Copilot and AI capabilities](enable-ai.md).
* You're familiar with creating sales orders.

## Geographic availability

The following table shows the Microsoft Azure geographic areas in which his feature is available.


|Environment Azure region  |Azure OpenAI Service geography   |Admin action required to unlock Copilot  |
|---------|---------|---------|
|Germany (North, West Central)     | Sweden or Switzerland        |  Yes       |
|Norway (East, West)     | Sweden or Switzerland        | Yes     |
|Singapore     |         |         |
|South Africa (North, West)     |   United States      |   Yes      |
|Switzerland (North, West)     |  Sweden or Switzerland       |    Yes     |
|United Arab Emirates (North, West)     |    United States     |   Yes     |
|United States (Central, East, North Central, South Central, West)     |   United States      |   No      |
|Europe (West, North)     |   Sweden or Switzerland      |   Yes      |
|Asia Pacific     |         |         |
|Australia (South East)     |   United States      |    Yes     |
|South America     |         |         |
|India (Central, South)     |    United States     |   Yes      |
|Japan (East, West)     |    United States     |    Yes     |
|France (Central, South)     |    Sweden or Switzerland     |    Yes     |
|Korea (Central, South)     |    United States     |    Yes     |

## Examples of prompts

The suggest sales lines with Copilot can handle a wide variety of prompt input. This section offers some examples of prompts that we've tested.

## Suggest lines on a sales document

This process describes how to suggest lines on a sales order. The steps are the same for sales quotes and invoices.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order**, and then choose the related link.
1. Open the sales order.
1. On the **Lines** FastTab, choose **Get line suggestions**.
1. In the **Suggest lines with Copilot** window, enter your prompt.  

## Review, save, discard, or regenerate suggestions

After Copilot suggests the items to add to lines, review its suggestions and decide whether they're what you want.

## See also

[Configure Copilot and AI capabilities](enable-ai.md)