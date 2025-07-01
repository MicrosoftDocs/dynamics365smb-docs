---
title: Suggest substitute items with Copilot
description: Assign substitute items faster with assistance from Copilot.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 04/01/2025
ms.custom: bap-template
ms.collection:
  - bap-ai-copilot
ms.search.form: 30, 31, 5716_Primary
---

# Suggest substitute items with Copilot

[!INCLUDE [preview-banner](includes/preview-banner.md)]

This article explains how to find and assign substitute items faster by letting Copilot suggest the items to add.

[!INCLUDE [production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## About item substitution suggestions

To ensure they can fulfill orders quickly, businesses often assign similar items to each other so they can use them as substitutes. For example, substitutes are good to have when the item that was originally requested is out of stock. Finding and assigning the right items to use as substitutes can be time consuming, and that's where Copilot can help. The suggest item substitutions capability for Copilot can speed up the process of finding similar items.

Information about products is stored in multiple places in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, item numbers and descriptions are stored in the Item table, multiple barcodes are stored in the Item Reference table, and item properties are stored in the Item Attributes table. Copilot uses a large language model combined with embedded search to comb through this information and suggest items that might be good substitutes. While you might prompt for *Red bicycle*, the actual product might be *Crimson Tourer**, where *Bicycle* is an item category and *Red* is an attribute.

## Available languages

[!INCLUDE [copilot-geo-and-language-availability](includes/copilot-geo-and-language-availability.md)]

## Prerequisites

- Your administrator must activate the **Create product information** capability on the **Copilot & agent capabilities** page. [Learn more about how to configure Copilot and agent capabilities](enable-ai.md).
- You're familiar with creating and managing product (item) information.

## Suggest item substitutions on item substitution entries

This process describes how to get Copilot to suggest substitute items.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
2. Select the item you want Copilot to find substitutes for.
3. Choose the **Substitutions** action.
4. On the **Item Substitution Entry** page, choose **Suggest with Copilot**.
5. Review the suggestions. To learn more, go to [Review, save, discard, or regenerate suggestions](#review-save-discard-or-regenerate-suggestions).

## Adjust the search

By default, the capability uses the item description as search criteria, which you can adjust if you want to fine-tune the search results. To edit the prompt, select the :::image type="content" source="media/edit-pencil.png" alt-text="Edit the prompt."::: icon in the Copilot window. For example, you can add more details to the prompt such as colors, sizes, or other item attributes.

## Review, save, discard, or regenerate suggestions

After Copilot suggests the items to add, review the suggestions and decide whether they're what you want:

- To discard a single proposed line, select it in the list, and then choose the **Delete Line** action.
- To discard all proposed lines and close the Copilot window, choose **Discard** (trash can).
- To transfer the lines shown in the Copilot window, choose **Insert all**. This step confirms that you want to transfer the lines to the **Item Substitution Entry** page. You can delete or edit the transferred lines there as well. The **Score** field that displays **High (85+)**, **Medium (83-85)**, and **Low (79-83)** scores and points you to lines that need attention.

## Related information

[FAQ for suggest item substitutions with Copilot](faq-suggest-item-substitutions-with-copilot.md)  
[Troubleshoot Copilot and agent capabilities](ai-copilot-troubleshooting.md)  
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)
