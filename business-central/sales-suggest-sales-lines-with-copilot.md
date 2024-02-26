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

# Suggest lines on sales documents with Copilot

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

This article explains how to create sales documents faster by letting Copilot suggest the items to add to lines on sales documents for your customers.

## About sales line suggestions with Copilot

Sales line suggestion with Copilot can assist with creating lines on sales documents such as sales quotes, sales orders, and invoices based on structured input or natural language. The Sales lines suggestions is not a general-purpose chat bot, but highly specific and integrated experience available from sales documents and offering two distinct skills. These skills help users find data they are looking for, either individual products or the whole documents.

* Finding products.
The information describing the product is stored in multiple places within [!INCLUDE [prod_short](includes/prod_short.md)] database, for example item number and item description are stored in the **Item** table, but multiple barcodes are stored in the **Item Reference** table, property of product are stored in the **Item Attributes**. While user may express need in *Red bicycle*, the actual product might be *Crimson tourer*, where *Bicycle* is a product category and *red* is an attribute.

* Finding document by reference.
It is common to repeat the past order or at least to have it as a starting point. But it might be tricky to find one if there is a load of orders. Users might remember some id, which can be company assigned number or reference number received from customer. Accepting inquiry inquiries like *Need last invoice from April* should help user to start editing faster.

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

### Sample inquiry to repeat the past document
Prompt: *Need all the products from invoice 103031*

### During phone call user quickly types list of required products and quantities, not always accurate enough or using internal product names
Prompt: *2 Red Kids Biicycle*

Note multiple typos. 

### User copies inquiry from an inbound communication and pastes it to the Sales Lines Suggestions page
Prompt: *Hello, I am interested in buying some accessories for my XXXX Laptop, such as a wireless mouse, a keyboard cover, and a laptop bag. I wonder if you have any recommendations or suggestions for these items. Do you have any special offers or discounts for loyal customers like me? Kind regards, M*

Note that XXXX Laptop is not incuded into search.

## Suggest lines on a sales document

This process describes how to suggest lines on a sales order. The steps are the same for sales quotes and invoices.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order**, and then choose the related link.
1. Open the sales order.
1. On the **Lines** FastTab, choose **Get line suggestions**.
1. In the **Suggest lines with Copilot** window, enter your prompt or select one from prompt guides.

If 

## Review, save, discard, or regenerate suggestions

After Copilot suggests the items to add to lines, review its suggestions and decide whether they're what you want:
* To discard a single proposed line, select it in the list, and then select the **Delete Line* action.
* To discard all proposed lines and close the Copilot window, select the discard button (trash can) next to the Keep it button at the bottom of the window.
* To transfer lines currenctly currently shown in the Copilot window, select **Keep it**. 

There is a **Reliability** field that displays High (80+), Medium (60-80), Low (60-) scores. That points user to lines that require extra attention. 

This step confirms the transfer of the currently showns lines to the corresponding sales document. You can delete or edit transfered lines there as well, you can delete the whole document if needed.

## See also

[Configure Copilot and AI capabilities](enable-ai.md)
