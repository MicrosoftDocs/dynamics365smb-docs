---
title: Undepreciable fixed assets in Russia
description: Russian localization lets you manage fixed assets that aren't subject to depreciation.
author: DianaMalina
ms.topic: article
ms.search.keywords: undepreciable, fixed assets, Russia, depreciation
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Undepreciable fixed assets

The undepreciable fixed assets feature enables you to repay fixed assets with the whole amount of their acquisition at the time of their release. It also automatically creates quantity records for these fixed assets in order to keep records of their existence and movements in quantitative terms.  

Create a depreciation book to keep records of the quantities of fixed assets that are repaid at the time of release for the amount that they were acquired for. For more information, see [Set Up a Quantity Book](how-to-set-up-a-quantity-book.md).  

## Set up an undepreciable fixed asset

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.

1. In the **Fixed Asset Card** window, on the **Depreciation** FastTab, select the **Undepreciable FA** field.

1. Choose the **OK** button.

## Create a purchase order for an undepreciable fixed asset

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
1. Create an order, select the vendor, and fill in the required header fields.
1. Add a line with **Type** set to **Fixed Asset**, select the asset in **No.**, and enter the quantity, direct unit cost, and depreciation book.
1. Choose the **Post** action.
1. Choose the **OK** button.

## Create a release order for an undepreciable fixed asset

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Releases**, and then choose the related link.
1. Create or open a release. Fill in the posting date and a line for the acquired asset, including the depreciation book and quantity.
1. In the **FA Release Act** window, choose the **Post** action.
1. Choose the **OK** button.

## Related information

[Fixed Assets](../../fa-manage.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
