---
title: Straight-Line Depreciation of Fixed Assets in the UK
description: Define 13 accounting periods to calculate straight-line depreciation in the UK version. Calculate daily depreciation and distribute it across these periods appropriately.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: straight line depreciation, fixed assets
ms.search.form: 5610, 5611, 5619
ms.date: 02/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Define accounting periods for straight-line depreciation of fixed assets

You can define 13 accounting periods to calculate straight line depreciation. You must calculate depreciation daily and distribute across the relevant periods. You can also define these accounting periods in the **FA - Projected Value** report.  

> [!NOTE]  
> To calculate depreciation using both the older adults (360 days) and the new methods (365 or 366 days), create separate depreciation books; one for the old method, and one for the new method. Attach these books to the relevant assets.  

### Define accounting periods to calculate straight line depreciation

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.  
1. To open a new **Depreciation Book Card** page, choose the **New** action.  
1. On the **General** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Choose the **OK** button.  

## Define accounting periods in the FA - Projected Value report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA - Projected Value**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

> [!NOTE]
> You can turn on the **Use Accounting Period** toggle if you want the periods between start date and ending date to correspond to the accounting periods you specified on the **Accounting Periods** page. The **Number of Days** field is cleared and made read-only on the FA - Projected Value report. If you don't turn on the toggle, the projected value amounts are calculated based on a 360 day year.

## Related information

- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)
- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
