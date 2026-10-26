---
title: Set Up Alternate Depreciation Methods
description: Learn how to set up depreciation tables and enable anticipated, accelerated, or reduced depreciation in the Italian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: alternate depreciation methods, anticipated depreciation, accelerated depreciation, reduced depreciation, depreciation table, Italian version
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up alternate depreciation methods

Alternate depreciation methods are as follows:  

- Anticipated depreciation
- Accelerated depreciation
- Reduced depreciation

You must create depreciation tables to set up these depreciation methods.  

## Steps to set up alternate depreciation methods

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Depreciation Tables**, and then choose the related link.  
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
    |**Accelerated/Reduced %**|The percentage used to calculate accelerated or reduced depreciation for the period.|

1. Review **Total Depreciation %**. This read-only field adds the period depreciation, anticipated, and accelerated or reduced percentages from the table lines.
1. Choose the **OK** button.  

Assign the depreciation table to the relevant fixed asset depreciation book with **Depreciation Method** set to **User-Defined**. For anticipated depreciation, also enable **Calc. Anticipated Depreciation** on the depreciation book and use **Use Anticipated Depr.** when you run **Calculate Depreciation**.

For accelerated or reduced depreciation, enable **Calc. Custom 2 Depreciation** on the depreciation book and select **Use Acc./Red. Depr.** in **Calculate Depreciation**.

## Related information

- [Set Up Fixed Asset Depreciation](../../fa-how-setup-depreciation.md)
- [Italian Fixed Assets](italian-fixed-assets.md)
- [Create Multiple Fixed Asset Cards](how-to-create-multiple-fixed-asset-cards.md)
- [Set Up Compressed Depreciation of Fixed Assets](how-to-set-up-compressed-depreciation-of-fixed-assets.md)
- [Print Depreciation Book Reports](how-to-print-depreciation-book-reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
