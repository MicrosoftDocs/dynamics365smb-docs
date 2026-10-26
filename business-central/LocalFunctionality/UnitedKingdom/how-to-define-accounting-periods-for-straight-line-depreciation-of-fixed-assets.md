---
title: Straight-Line Depreciation of Fixed Assets in the UK
description: Define 13 accounting periods for straight-line fixed asset depreciation in the UK version, and calculate projected values for those periods.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: straight line depreciation, fixed assets
ms.search.form: 5610, 5611, 5619
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Define accounting periods for straight-line depreciation of fixed assets

You can define 13 accounting periods to calculate straight-line depreciation. You must calculate depreciation daily and distribute it across the relevant periods. The **FA - Projected Value** report can use the periods you define on the **Accounting Periods** page.

> [!NOTE]  
> To calculate depreciation by using both a 360-day year and a 365- or 366-day year, create separate depreciation books for the two methods. Attach these books to the relevant assets.

## Define accounting periods to calculate straight-line depreciation

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Depreciation Books**, and then choose the related link.
1. To open a new **Depreciation Book Card** page, choose the **New** action.  
1. Fill in the fields as necessary, and turn on **Use Accounting Period** on the depreciation book. Define the periods on the **Accounting Periods** page. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Choose the **OK** button.  

## Define accounting periods in the FA - Projected Value report  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **FA - Projected Value**, and then choose the related link.
1. On the **Options** FastTab, select the **Depreciation Book** that has **Use Accounting Period** turned on. Specify **First Depreciation Date** and **Last Depreciation Date**, and fill in the other fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

> [!NOTE]
> The report reads **Use Accounting Period** from the selected depreciation book. When the setting is on, **Number of Days** is cleared and made read-only. When the setting is off, you can specify the period length in **Number of Days**. The fiscal year length depends on the depreciation book settings, rather than always being 360 days.

## Related information

- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)
- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
