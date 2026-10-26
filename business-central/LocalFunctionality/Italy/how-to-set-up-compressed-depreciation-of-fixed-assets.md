---
title: Set Up Compressed Depreciation of Fixed Assets
description: Learn how to summarize compatible fixed asset depreciation amounts in the general ledger while retaining individual asset entries in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: compressed depreciation, fixed assets, compressed fixed asset depreciation, compressed depreciation set up, Italian version
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up compressed depreciation of fixed assets

Use **Compress Depreciation** to summarize compatible depreciation amounts in the general ledger when you post a fixed asset journal. The entries for individual fixed assets are retained.

For example, a journal with depreciation lines for 100 assets can produce fewer general ledger entries when the grouping values match. Each asset retains its own depreciation entries.

The grouping uses the fixed asset posting type, fixed asset posting group, depreciation book, document number, reason code, posting date, and dimension set. It isn't based directly on the fixed asset subclass.

## Enable compressed depreciation

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Depreciation Books**, and then choose the related link.  
1. On the **Depreciation Book List** page, select the relevant depreciation book, and then choose the **Edit** action.  
1. On the **Depreciation Book Card** page > **General** FastTab, select the **Compress Depreciation** checkbox.

1. Choose the **OK** button.  

> [!NOTE]
> Lines with different posting groups, dates, dimensions, or other grouping values remain separate.

## Related information

- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)
- [Italian Fixed Assets](italian-fixed-assets.md)
- [Set Up Alternate Depreciation Methods](how-to-set-up-alternate-depreciation-methods.md)
- [Create Multiple Fixed Asset Cards](how-to-create-multiple-fixed-asset-cards.md)
- [Print Depreciation Book Reports](how-to-print-depreciation-book-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
