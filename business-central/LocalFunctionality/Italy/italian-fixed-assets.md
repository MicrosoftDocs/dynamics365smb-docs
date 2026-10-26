---
title: Italian Fixed Assets in Business Central
description: Learn about the features available for managing fixed assets in Italy, including depreciation methods and automated processes in Business Central.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: Italian fixed assets, fixed asset, anticipated depreciation, accelerated depreciation, reduced depreciation, automatic fixed asset creation, Italian version
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Italian fixed assets

Fixed assets are properties owned by a company and used in the production of its income. Assets can be either tangible or intangible, and can be either durable or non-durable. Cars, machines, and furniture are examples of tangible assets. Startup costs and licenses are examples of intangible assets.  

The following features are added to the fixed assets functionality:  

- There are several types of depreciation available, including the following: anticipated, accelerated, and reduced.  
- Automatic creation of multiple fixed asset cards from an invoice.  
- A **Depreciation Book** report that displays depreciation by fixed asset type.  

Anticipated depreciation uses the additional percentages that you define in the **Anticipated %** field on depreciation table lines. Enable **Calc. Anticipated Depreciation** on the depreciation book, and select **Use Anticipated Depr.** when calculating depreciation.

Accelerated depreciation uses a higher depreciation rate to shorten an asset's depreciation period. Define the applicable percentage in **Accelerated/Reduced %** on the depreciation table lines.

Reduced depreciation uses a lower rate and can lengthen the depreciation period. Define the applicable percentage in the same **Accelerated/Reduced %** field.

> [!IMPORTANT]
> Confirm which methods and rates apply to your assets under the requirements for the relevant fiscal year. The configured depreciation percentages don't establish whether a tax treatment is legally available.

## Related information

- [Fixed Assets](../../fa-manage.md)
- [Italy Local Functionality](italy-local-functionality.md)
- [Set Up Alternate Depreciation Methods](how-to-set-up-alternate-depreciation-methods.md)
- [Create Multiple Fixed Asset Cards](how-to-create-multiple-fixed-asset-cards.md)
- [Set Up Compressed Depreciation of Fixed Assets](how-to-set-up-compressed-depreciation-of-fixed-assets.md)
- [Print Depreciation Book Reports](how-to-print-depreciation-book-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
