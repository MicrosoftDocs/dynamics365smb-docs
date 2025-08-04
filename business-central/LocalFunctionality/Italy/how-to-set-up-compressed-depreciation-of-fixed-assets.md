---
title: compressed depreciation of fixed assets [IT]
description: You can compress fixed asset depreciation into subclasses and choose to display only the total sum by subclass.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: compressed depreciation, fixed assets, compressed fixed asset depreciation, compressed depreciation set up, Italian version
ms.date: 05/21/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up compressed depreciation of fixed assets

You can compress fixed asset depreciation into subclasses and choose to display only the total sum by subclass. You can choose to post only the depreciation totals of assets that are grouped by category. This is particularly important for companies that have multiple fixed assets divided into many individual items.  

When you calculate depreciation, one line is generated for each fixed asset. For example, posting depreciations for 100 assets generates 100 lines that are posted to both the general ledger and fixed asset ledger entries.  

## Process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.  
1. On the **Depreciation Book List** page, select the relevant depreciation book, and then choose the **Edit** action.  
1. To post only the depreciation totals of assets that are grouped by category, on the **Depreciation Book Card** page > **General** FastTab, select the **Compress Depreciation** checkbox.  

    > [!NOTE]  
    > Multiple depreciation lines are then compressed in the general ledger and are displayed in a single entry that is divided by fixed asset categories.  

1. Choose the **OK** button.  

## Related information

- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)
- [Italian Fixed Assets](italian-fixed-assets.md)
- [Set Up Alternate Depreciation Methods](how-to-set-up-alternate-depreciation-methods.md)
- [Create Multiple Fixed Asset Cards](how-to-create-multiple-fixed-asset-cards.md)
- [Print Depreciation Book Reports](how-to-print-depreciation-book-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
