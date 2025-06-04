---
title: Setting up Fixed Asset for depreciation calculation
description: Specifies Basic Setups required, for Fixed Asset Depreciation Calculation

author: v-debapd

    
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Setting Up Fixed Asset for Depreciation Calculation

### Overview

Business Central has included Fixed Asset Depreciation Calculation Feature to Indian Localization.

Computation of Depreciation on Block of Assets under the Income Tax Act, 1961 and computation of Depreciation under Companies Act,2013.

### Setting up Fixed Asset for Depreciation Calculation


### Following is the list of Setups, user needs to configure for Fixed Assets in **Business Central**

- [Depreciation Book](fa_overview.md#to-set-up-fa-depreciation-books)
- [FA Accounting Period Income Tax](fa_overview.md#to-set-up-fa-accounting-period-for-income-tax)
- [FA Block Code](fa_overview.md#to-set-up-fa-block-code)
- [Setup for Additional Depreciation](fa_overview.md#to-set-up-additional-depreciation)


## To set up FA Depreciation Books

Fixed assets must have a depreciation book to record depreciations for the fixed assets.


1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Depreciation Books**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**No. of Days Non Seasonal**|Specifies the number of non seasonal days.|
    |**No. of Days Seasonal**|Specifies the number of seasonal days.|
    |**FA Book Type**|Specifies whether the book type is Income Tax or not.|
    |**Depr. Threshold Days**|Specifies the threshold days for depreciation calculation.|
    |**Depr. Reduction %**|Specifies the reduction percentage for depreciation calculation.|


## To set up FA Accounting Period for Income Tax

Fixed Asset Income Tax Accounting Period needs to be created for depreciation calculation.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **FA Accounting Period for Inc. Tax**, and then choose the related link. 
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Starting Date**|Specify the starting date of the accounting period.|
    |**Name**|Specify the name of months.|
    |**New Fiscal Year**|Specify which month is the starting of a new fiscal year.|

## To set up FA Block Code

Fixed Asset Block Code is required for depreciation calculation for Income Tax Act.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **FA Classes** -> select relevant class and click on **Blocks**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**Code**|Enter the relevant code of the block.|  
    |**Description**|Specify the description of the block.|
    |**Book Value**|Specifies the total book value of the block.|
    |**Depreciation %**|Specify the depreciation percentage of the block.|
    |**No of Assets**|Specifies the total number of asset of the block.|
    |**Add Depreciation %**|Specifies the additional depreciation percentage of the block.|
    |**FA Class Code**|Specifies the fixed asset class code for which the block is attached.|

## To set up Additional Depreciation

Setup needs to be done to calculate additional depreciation for Fixed Assets.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Fixed Assets**, and then choose the related link. Then select relevant Fixed Asset -> Click on **Add. Depr. Applicable**.
 
 



## Related information 
[Fixed Asset Depreciation](FA_Depreciation.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]