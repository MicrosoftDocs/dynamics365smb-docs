---
title: Set Up FA Depreciation
description: Choose from multiple depreciation methods in Business Central, and configure each asset's depreciation method on the Fixed Asset Card page.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: write down, fixed asset depreciation
ms.search.form: 5611_Primary
ms.date: 08/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up fixed asset depreciation

You can use various methods of depreciation for preparing financial statements and income tax returns. Many large corporations use straight-line depreciation in their financial statements because this generally permits reporting higher earnings. For income tax purposes, however, many businesses use an accelerated depreciation method, such as declining-balance depreciation. You define an asset's depreciation method with the **Depreciation Method** field on the **Fixed Asset Card** page. Learn more in [Depreciation Methods](fa-depreciation-methods.md) for information about what the different methods do.

You set up depreciation books where you define the different ways depreciation must be calculated for different types of fixed assets. Each depreciation book specifies individual depreciation terms. For example, you can specify that a fixed asset should be depreciated over a period of three years in one book and over a period of five years in another book.

When you have created the relevant depreciation books, you must assign one or more depreciation books to each fixed asset. A depreciation book that is assigned to a fixed asset is referred to as a fixed asset depreciation book. You can set up an unlimited number of depreciation books for a fixed asset.  

## Create a depreciation book

In a fixed asset depreciation book, you specify how fixed assets are depreciated. To accommodate various methods of depreciation, you can set up multiple depreciation books.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Depreciation Books**, and then choose the related link.
2. On the **Depreciation Books List** page, choose the **New** action.
3. On the **Depreciation Book Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > You can record fixed asset transactions on the **Fixed Asset G/L Journal** page or on the **Fixed Asset Journal** page, depending on whether the transactions are for financial reporting or for internal management. Follow the next step to define which type of journal is used for the different fixed asset activities by default.
4. On the **Integration** FastTab, select the check box for each fixed asset activity whose transactions you want to post using the **Fixed Asset G/L Journal** page.
5. Repeat steps 2 through 4 for each depreciation method or posting method that you want to assign to fixed assets as a depreciation book.

> [!IMPORTANT]
> Choose the **Use Rounding in Periodic Depr.** field to round the calculated periodic depreciation amounts to whole numbers. For example, if your company also uses invoice rounding to whole numbers in the **General Ledger Setup** page, rounding also depreciation amounts to whole numbers can help provide transparency.

For example, if you dispose of a fixed asset where the depreciation book doesn't specify rounding, but your company's general ledger setup requires rounding then when you dispose of the fixed asset, you see an error message that an amount must be rounded on a ledger entry.  

## Assign a depreciation book to a fixed asset

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you want to set up a fixed asset depreciation book for.
3. On the **Depreciation Book** FastTab, fill in the fields as necessary.
4. If you need to assign more than one depreciation book to the fixed asset, choose the **Add More Depreciation Books** action.
5. Alternatively, choose the **Depreciation Books** action to specify one or more fixed asset depreciation books.

    > [!NOTE]  
    > - When you use the manual depreciation method, you must enter depreciation manually in the fixed asset G/L journal. The **Calculate Depreciation** function omits fixed assets that use the manual depreciation method. You can use this method for assets that aren't subject to depreciation, such as land.
    >
    > - When you use the user-defined depreciation method, you need to assign the depreciation book in a different way. Learn more in [Set Up User-Defined Depreciation Method](fa-how-setup-user-defined-depreciation-method.md).

## Assign a depreciation book to multiple fixed assets with a batch job

If you want to assign a depreciation book to several fixed assets, you can use the **Create FA Depreciation Books** batch job to create fixed asset depreciation books.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you want to set up a assign a depreciation book to, and then choose the **Edit** action.
3. On the **Depreciation Book Card** page, choose the **Create FA Depreciation Books** action.
4. On the **Create FA Depreciation Books** page, fill in the **Depreciation Book** field.
5. Choose the **Copy from FA No.** field, and then select the fixed asset number that you want to use as the basis for creating new fixed asset depreciation books.

   If you fill in this field, the depreciation fields in the new fixed asset depreciation books contain the same information as the corresponding fields in the fixed asset depreciation book that you copy from. Leave the field blank if you want to create new fixed asset depreciation books with empty depreciation fields.  
6. On the **Fixed Asset** FastTab, you can set a filter to select the assets that you want to create the fixed asset depreciation books for.
7. Choose the **OK** button.

## Set up depreciation posting types

For each depreciation book, you must set up how you want [!INCLUDE[prod_short](includes/prod_short.md)] to handle various posting types. For example, whether posting should be debit or credit and whether the posting type should be included in the depreciable basis.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Depreciation Books**, and then choose the related link.  
2. Select the depreciation book that you want to set up, and them choose the **FA Posting Type Setup** action.
3. On the **FA Posting Type Setup** page, fill in the fields as necessary.

    > [!NOTE]  
    > You can't insert or delete lines on the **FA Posting Type Setup** page. You can only modify the existing lines.

We recommend that you don't change the setup for depreciation books for entries that have already been posted. Changes don't affect the entries that are already posted, which would make depreciation book statistics misleading.

## Set up default templates and batches for fixed asset depreciation

For each depreciation book, you define a default setup of templates and batches. You use these defaults to duplicate lines from one journal to another, create journal lines using the **Calculate Depreciation** or **Index Fixed Assets** batch jobs, duplicate acquisition costs in the insurance journal.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Depreciation Books**, and then choose the related link.  
2. Select the depreciation book that you want to define default journals for, and then choose the **FA Journal Setup** action.  
3. If you want to have a default setup for each user, choose the **User ID** field to select from the **Users** page.  
4. In the other fields, select the journal template or journal batch that must be used by default.  

## Fiscal year 365 days field depreciation

When the Calculate Depreciation batch job calculates depreciations, the batch job normally uses a standardized year of 360 days where each of the 12 months has 30 days.

If you select this field, the Calculate Depreciation batch job uses the calendar year of 365 days instead, where each month is calculated with the same number of days as in the calendar. The only exception is February in leap years, which the batch job treats as having 28 days and not 29. Because of that, all years, also leap years, are considered to have 365 days.

## Related information

- [Setting Up Fixed Assets](fa-setup.md)  
- [Fixed Assets](fa-manage.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
