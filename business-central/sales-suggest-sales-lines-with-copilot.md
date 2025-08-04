---
title: Sales line suggestions with Copilot
description: Learn how to suggest lines on sales orders with Copilot.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: how-to
ms.search.keywords: Copilot, AI, sell
ms.search.form:
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.service: dynamics-365-business-central
ms.custom: bap-template
ms.collection: bap-ai-copilot
---

# Suggest lines on sales documents with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to create sales documents faster by letting Copilot suggest the items to add to lines on sales documents for your customers.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Sales line suggestions

Sales line suggestion can assist with creating lines on sales documents such as sales quotes, orders, and invoices based on structured input or natural language. The feature isn't a general-purpose chat, but a highly specific and integrated experience that you can use on sales documents. The feature offers two distinct skills that help you find data about individual products or entire documents.

- Find products

  Information that describes products is stored in multiple places in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, item numbers and descriptions are stored in the **Item** table, multiple barcodes are stored in the **Item Reference** table, and product properties are stored in the **Item Attributes** table. While you might prompt for *Red bicycle*, the actual product might be *Crimson tourer*, where *Bicycle* is a product category and *red* is an attribute.

- Find documents by reference

  People often repeat a previous order, or at least use it as a starting point. But it might be tricky to find the right order in a stack of orders. You might remember some of the order's ID, which can be a company-assigned number or a reference number received from a customer. Being able to use prompts such as *Need last invoice from April* should help you find an order faster.

## Supported languages

[!INCLUDE[copilot-language-support-en-only](includes/copilot-language-support-en-only.md)]

## Prerequisites

- Your administrator activates the **Sales Line Suggestions** capability on the **Copilot & agents capabilities** page. Learn more at [Configure Copilot and agent capabilities](enable-ai.md).

## Examples of prompts

Suggest sales lines with Copilot can handle a wide variety of prompt input. This section offers examples of prompts for various scenarios we tested.

### Sample inquiry to repeat a document

Prompt: *Need all the products from invoice 103031*

### During a phone call, you quickly type a list of required products and quantities, but aren't always exact and sometimes use internal product names

Prompt: *2 Red Kids Biicycle*

The prompt works, even with multiple typos.

### A user copies an inquiry from an inbound communication and pastes it onto the Sales Lines Suggestions page

Prompt: *Hello, I'm interested in buying some accessories for my XXXX Laptop, such as a wireless mouse, a keyboard cover, and a laptop bag. I wonder if you have any recommendations or suggestions for these items. Do you have any special offers or discounts for loyal customers like me? Kind regards, M*

Note that XXXX Laptop isn't included in search.

## Options for matching keywords in prompts

When you search for an item using a FullText index, we extract both primary and extra keywords. For example, we break down the search term "Red Coffee Table" into primary keywords "Coffee" and "Table," and some synonyms and other keywords, such as "Red."

When you enter your prompt in the **Suggest Sales Lines** window, the **Matching** field offers the following options for matching criteria:

- [Permissive](#permissive-matching-criteria) means that all keywords are optional. This option typically generates the most suggestions.
- [Balanced](#balanced-matching-criteria) is a blend of required and optional keywords. This option typically generates fewer suggestions.
- [Precise](#precise-matching-criteria) means that all keywords are required. This option typically generates the fewest suggestions.

The following sections provide examples of how matching works. The examples are based on a prompt for "Red Coffee Table" and you have the following fictitious items:

- Red Coffee Table
- Blue Coffee Table
- Green Coffee Table
- Red Side Table
- Dining Table

### Permissive matching criteria

The primary keywords "Coffee" and "Table" are optional. The extra keyword "Red" is optional. This search returns items such as:

- Red Coffee Table
- Blue Coffee Table
- Green Coffee Table
- Red Side Table
- Dining Table

### Balanced matching criteria

The primary keywords "Coffee" and "Table" are required. The extra keyword "Red" is optional. This search returns items such as:

- Red Coffee Table
- Blue Coffee Table
- Green Coffee Table

### Precise matching criteria

The primary keywords "Coffee" and "Table" are required. The extra keyword "Red" is required. This search returns items such as:

- Red Coffee Table

## Suggest lines on a sales document

This process describes how to suggest lines on a sales order. The steps are the same for sales quotes and invoices.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Order**, and then choose the related link.
1. Open a sales order or create a new one.
1. On the **Lines** FastTab, choose **Suggest sales lines**.
1. In the **Suggested sales lines** window, enter your prompt or select one from the prompt guides.

## Review, save, discard, or regenerate suggestions

After Copilot suggests the items to add to lines, review its suggestions and decide whether they're what you want:

- To discard a single proposed line, select it in the list, and then choose the **Delete Line** action.
- To discard all proposed lines and close the Copilot window, choose the Discard button (trash can) next to the **Keep it** button.
- To transfer the lines shown in the Copilot window, choose **Keep it**. 

There's a **Reliability** field that displays **High (80+)**, **Medium (60-80)**, and **Low (60-)** scores and points you to lines that need attention.

This step confirms that you want to transfer the lines to a sales document. You can delete or edit the transferred lines there as well, or delete the whole document.

## Related information

[FAQ for Sales Line Suggestions with Copilot](faq-sales-suggest-sales-lines-with-copilot.md)
[Configure Copilot and agent capabilities](enable-ai.md)
