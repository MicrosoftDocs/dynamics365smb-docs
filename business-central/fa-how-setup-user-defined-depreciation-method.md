---
title: Set Up FA User-Defined Depreciation Method
description: Define an asset's depreciation in Business Central by selecting a user-defined depreciation method on the Fixed Asset Card page.
author: jill-kotel-andersson
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: user-depreciation, depreciation methods, fixed assets
ms.date: 08/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Set up fixed assets with user-defined depreciation methods

You can use [!INCLUDE[prod_short](includes/prod_short.md)] to set up the user-defined depreciation methods as described here.

For each user-defined method, you use the **Depreciation Tables** page, where you must enter a depreciation percentage for each period (month, quarter, year, or accounting period). Then, when you assign a depreciation book with a user-defined method to a fixed asset, you must set the **First User-Defined Depr. Date** and **Depreciation Starting Date** fields on the **FA Depreciation Books** page for the specific fixed asset.  

The formula for calculating the depreciation amounts is:  

*Depreciation Amount = (Depreciation % x Number of Depreciation Days x Depr. Basis) / (100 x 360)*

> [!NOTE]  
> While the date in the field **First User-Defined Depr. Date** is used to determine the time intervals, it's the **Depreciation Starting Date** that is used to determine the number of depreciation days. If the **First User-Defined Depr. Date** is earlier than the **Depreciation Starting Date**, the percentage for the first period in the depreciation table is only partially used when the program calculates the first depreciation. This means that the asset isn't completely depreciated by the end of the last period.

## Assign a depreciation book to a fixed asset with a user-defined depreciation method

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you want to set up a fixed asset depreciation book for.
3. Choose the **Related** action, and then choose **Fixed Asset**, and then **Depreciation Books**. This opens the **FA Depreciation Books** page.

   By default, some of the fields that need to be filled in per the instructions below are hidden, so you must display them. To do this, you need to personalize the page. For more information, see [To start personalizing a page through the Personalizing banner](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).
1. In the field **Depreciation Method**, select **User-Defined**.
1. In the field **Depreciation Table Code**, select the **Depreciation Table** you want to use.
1. In the field **Depreciation Starting Date**, select the starting date for the depreciation calculation.
1. When you use a user-defined method, the **First User-Defined Depr. Date** field must be set to a date that is the same or earlier than the field **Depreciation Starting Date**. If you have selected a value in the **Period Length** field in the depreciation table, the date in the field **First User-Defined Depr. Date** must be the starting date of an accounting period.
1. Either fill in the field **No. of Depreciation Years** or the field **Depreciation Ending Date**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 

## Set up user-defined depreciation methods

On the **Depreciation Table** page, you can set up user-defined depreciation methods. For example, you can set up depreciation based on number of units.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Depreciation Tables**, and then choose the related link.  
2. On the **Depreciation Table List** page, choose the **New** action.  
3. On the **Depreciation Table Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

> [!TIP]
> Use the **Create Sum of Digits Table** function to define a depreciation table based on the *Sum of Digits* method.

With the *Sum of Digits* method, if a fixed asset is depreciated over 4 years, then the depreciation for each year is calculated in the following way:

Sum of Digits = 1 + 2 + 3 + 4 = 10
Depreciation:

* Year 1 = 4/10  
* Year 2 = 3/10  
* Year 3 = 2/10  
* Year 4 = 1/10  

### Depreciation based on number of units

This user-defined method can also be used to depreciate based on number of units, for example, in the case of production machines with an established lifetime capacity. On the **Depreciation Tables** page, you can enter the number of units that can be produced in each period (month, quarter, year, or accounting period).  

### Example - User-defined depreciation

You use a depreciation method that allows you to depreciate assets in an accelerated manner for income tax purposes.  

You would use the following depreciation rates for a fixed asset with a three-year lifetime for tax purposes:  

* Year 1: 25%  
* Year 2: 38%  
* Year 3: 37%  

The acquisition cost is LCY 100,000, and the depreciable lifetime is five years. Depreciation is calculated annually.  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/20 |Acquisition Cost |(Depreciation starting date) |100,000.00 |100,000.00 |
| 12/31/20 |Depreciation |360 |-25,000.00 |75,000.00 |
| 12/31/21 |Depreciation |360 |-38,000.00 |37,000.00 |
| 12/31/22 |Depreciation |360 |-37,000.00 |0 |
| 12/31/23 |Depreciation |None |None |0 |
| 12/31/24 |Depreciation |None |None |0 |

In the previous example, both the **First User-Defined Depr. Date** and **Depreciation Starting Date** fields would be set to 01/01/20 in the **FA Depreciation Books** page for the specific fixed asset. If, however, the **First User-Defined Depr. Date** field contained 01/01/20 and the **Depreciation Starting Date** field contained 04/01/20, the result would be:  

| Date | FA Posting Type | Days | Amount | Book Value |
| --- | --- | --- | --- | --- |
| 01/01/20 |Acquisition Cost |(Depreciation starting date) |100,000.00 |100,000.00 |
| 12/31/20 |Depreciation |270 |-18,750.00 |81,250.00 |
| 12/31/21 |Depreciation |360 |-38,000.00 |42,250.00 |
| 12/31/22 |Depreciation |360 |-37,000.00 |6,250.00 |
| 12/31/23 |Depreciation |90 |-6,250.00 |0 |
| 12/31/24 |Depreciation |None |None |0 |

## Related information

- [Setting Up Fixed Assets](fa-setup.md)  
- [Fixed Assets](fa-manage.md)  
- [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md)  
- [Depreciation Methods for Fixed Assets](fa-depreciation-methods.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
