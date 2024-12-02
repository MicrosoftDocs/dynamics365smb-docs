---
title: Suggest item substitutions with Copilot
description: Assign substitute items faster with assistance from Copilot.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 12/02/2024
ms.custom: bap-template
ms.collection:
  - bap-ai-copilot
ms.search.form: 30, 31, 5716_Primary
---

# Find item substitutions faster with Copilot

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to create item substitution entries faster by letting Copilot suggest the items to add.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## About suggest item substitutions with Copilot

To ensure they can fulfill orders quickly, businesses often assign similar items to each other so they can use them as substitutes. For example, when the original item requested is out of stock. The suggest item substitutions with Copilot feature can speed up the process of finding similar items. The feature uses our large language model combined with embedded search.

Information about products is stored in multiple places in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, item numbers and descriptions are stored in the Item table, multiple barcodes are stored in the Item Reference table, and item properties are stored in the Item Attributes table. While you might prompt for *Red bicycle*, the actual product might be *Crimson Tourer**, where *Bicycle* is an item category and *Red* is an attribute.

## Available languages

[!INCLUDE [copilot-geo-and-language-availability](includes/copilot-geo-and-language-availability.md)]

## Prerequisites

- The suggest item substitutions feature is activated. An administrator must complete this task. [Learn more about how to configure Copilot and AI capabilities](enable-ai.md).
- You're familiar with creating and managing product (item) information.

## Suggest item substitutions on item substitution entries

This process describes how to get suggestions for substitute items.

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
2. Select the item you want to find substitutes for.
3. Choose the **Substitutions** action.
4. On the **Item Substitution Entry** page, choose **Suggest with Copilot**.
5. Review the suggestions. To learn more, go to [Review, save, discard, or regenerate suggestions](#review-save-discard-or-regenerate-suggestions).

## Adjust the search

By default, suggest item substitutions with Copilot uses the item description as search criteria, which you can adjust to fine-tune search results.

## Review, save, discard, or regenerate suggestions

After Copilot suggests the items to add, review its suggestions and decide whether they're what you want:

- To discard a single proposed line, select it in the list, and then choose the **Delete Line** action.
- To discard all proposed lines and close the Copilot window, choose **Discard** (trash can).
- To transfer the lines shown in the Copilot window, choose **Insert all**.
The **Score** field that displays **High (85+)**, **Medium (83-85)**, and **Low (79-83)** scores and points you to lines that need attention.
This step confirms that you want to transfer the lines to Item Substitution Entry. You can delete or edit the transferred lines there as well.

## Related information

[FAQ for suggest item substitutions with Copilot](faq-suggest-item-substitutions-with-copilot.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[Responsible AI FAQ for bank reconciliation assist](faqs-bank-reconciliation.md)
