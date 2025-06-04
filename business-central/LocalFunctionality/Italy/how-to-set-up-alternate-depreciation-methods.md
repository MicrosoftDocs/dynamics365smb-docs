---
title: How to set up alternate depreciation methods
description: Learn how to set up alternate depreciation methods, such as anticipated, accelerated, and reduced depreciation.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: alternate depreciation methods, anticipated depreciation, accelerated depreciation, reduced depreciation, depreciation table, Italian version
ms.date: 05/21/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up alternate depreciation methods

Alternate depreciation methods are as follows:  

- Anticipated depreciation
- Accelerated depreciation
- Reduced depreciation

You must create depreciation tables to set up these depreciation methods.  

## Steps to set up alternate depreciation methods

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Tables**, and then choose the related link.  
1. On the **Depreciation Table List** page, choose the **New** action.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|The code for the depreciation table.|  
    |**Description**|The description for the depreciation table.|  
    |**Period Length**|The length of the period to which each of the depreciation table lines apply.|  
    |**Total No. of Units**|The total number of units that the asset is expected to produce in its lifetime.|  

1. On the **Lines** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Period Depreciation %**|The depreciation percentage to apply to the period.|  
    |**No. of Units in Period**|The number of units produced by the asset to which this depreciation table applies.|  
    |**Anticipated %**|The anticipated depreciation percentage.|  
    |**Accelerated/Reduced %**|The actual depreciation percentage.|  

1. In the **Total Depreciation %** field, enter the total depreciation percentage.  
1. Choose the **OK** button.  

## Related information

- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)
- [Italian Fixed Assets](italian-fixed-assets.md)
- [Create Multiple Fixed Asset Cards](how-to-create-multiple-fixed-asset-cards.md)
- [Set Up Compressed Depreciation of Fixed Assets](how-to-set-up-compressed-depreciation-of-fixed-assets.md)
- [Print Depreciation Book Reports](how-to-print-depreciation-book-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
