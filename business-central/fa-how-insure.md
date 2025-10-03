---
title: Insure fixed assets
description: Assign one or more fixed assets to an insurance policy by posting to the insurance coverage ledger using the Insurance Journal page.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.keywords: policy, coverage, insure fixed assets, fixed assets
ms.search.form: 5647, 5644, 5653, 5651, 5655, 5652, 5645, 5656, 5646, 5648, 9275
ms.date: 10/03/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Insure fixed assets

Use the **Insurance Card** page to set up an insurance policy to cover one or more fixed assets. You can assign one fixed asset to one insurance policy, or multiple fixed assets to one insurance policy.

You assign a fixed asset to an insurance policy by posting to the insurance coverage ledger from the **Insurance Journal** page.

In addition, you can assign a fixed asset to an insurance policy and create coverage ledger entries when you post its acquisition cost. You post an acquisition cost from the fixed asset journal with the **Insurance No.** field filled in. You must turn on the **Automatic Insurance Posting** toggle on the **Fixed Asset Setup** page. Learn more in [Acquire a fixed asset by using a fixed asset G/L journal](fa-how-acquire.md#acquire-a-fixed-asset-by-using-a-fixed-asset-gl-journal).

If the **Automatic Insurance Posting** toggle on the **Fixed Asset Setup** page isn't turned on, posting acquisitions from the fixed asset journal creates lines on the **Insurance Journal** page. You must post those lines manually.

> [!WARNING]  
> If you don't turn on the **Automatic Insurance Posting** toggle on the **Fixed Asset Setup** page, your insurance journal should be based on a journal template without a number series. This is because the inserted document numbers from the fixed asset journal line will otherwise conflict with the number series of the insurance journal. Learn more in [Set Up General Fixed Assets Information](fa-how-setup-general.md) for information about journal templates and batches.

After you assign a fixed asset to an insurance policy, the **Insured** field on the fixed asset card contains **Yes**. When you sell the fixed asset, the toggle is automatically turned off.

## Create or modify an insurance card

When you receive information about changes in the coverage amount, you must enter the new information on the **Insurance Card** page to ensure that you analyze insurance policy coverage correctly.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Insurance**, and then choose the related link.
1. Choose the **New** action to create a new card for an insurance policy. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Alternatively, select the insurance policy that you want to change, and then choose the **Edit** action.

## Assign a fixed asset to an insurance policy by posting from the insurance journal

You assign a fixed asset to an insurance policy by posting to the insurance coverage ledger.  

The following procedure explains how to create an insurance journal line manually. If the **Automatic Insurance Posting** toggle is turned on the **Fixed Asset Setup** page, insurance journal lines are automatically created when you post acquisition costs. In that case, all you have to do is to post the journal.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Insurance Journals**, and then choose the related link.  
1. Open the relevant journal, and fill in the journal lines as necessary.  
1. To assign multiple fixed assets to one insurance policy, create journal lines with the same value in the **Insurance No.** field and different values in the **FA No.** field.  
1. Choose the **Post** action.  

   > [!NOTE]  
   > The entries from an insurance journal are only posted to the insurance coverage ledger.  

## Update the insurance value of a fixed asset

You can use the **Index Insurance** batch job to update the value of the fixed assets that are covered.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Index Insurance**, and then choose the related link.
1. Fill in the fields as necessary.

   > [!NOTE]  
   > In the **Index Figure** field, you enter a decrease of 5%, for example, as 95, whereas you enter an increase of 2% as 102.  
1. Choose the **OK** button.  

   The batch job calculates the new amount as a percentage of the total value insured, as stated on the **Insurance Statistics** page, and then creates a line in the insurance journal.  
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Insurance Journals**, and then choose the related link.  
1. Open the relevant insurance journal, review the created values, and then post them to the insurance coverage ledger.  

## Monitor insurance coverage

[!INCLUDE[prod_short](includes/prod_short.md)] provides dedicated reports and statistics pages for use in analyzing insurance policies and whether your fixed assets are over- or under-insured.  

Learn more in [Fixed assets insurance reports](fa-reports.md#fixed-assets-insurance-reports) for information about the built-in reports for fixed assets insurance.

### Overview of insurance policies

To get an overview of your insurance policies, use the [Insurance - List](reports/report-5621.md) report.

### Insurance coverage

To find out which insurance policies cover each asset, and by which amount, use the [Insurance - Tot. Value Insured](reports/report-5625.md) report.

#### Over/under coverage

You can check whether fixed assets are over- or under-insured in the following ways:  

* The **Insurance Statistics** page. A positive amount in the **Over/Under Insured** field means that the fixed asset is over-insured. A negative amount means that the asset is under-insured.  
* The **Fixed Asset Statistics** page. Choose the **Total Value Insured** field to view the **Ins. Coverage Ledger Entries** page.  
* The **Over/Under Coverage** report.  
* The [Insurance - Analysis](reports/report-5620.md) report.  

### Uninsured fixed assets

To check whether you forgot to assign a fixed asset to an insurance policy, use the [Insurance - Uninsured FAs](reports/report-5626.md) report.

## View insurance coverage ledger entries

You can view the entries that you made in the insurance coverage ledger.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Insurance**, and then choose the related link.  
1. Select the relevant insurance policy, and then choose the **Coverage Ledger Entries** action.  

## View the total insurance value of fixed assets

A matrix page shows the insurance values that are registered for each insurance policy for each fixed asset that result from posted insurance-related amounts.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Insurance**, and then choose the related link.  
1. Select the relevant insurance policy, and then choose the **Total Value Insures per FA** action.  
1. Fill in the fields as necessary.  
1. Choose the **Show Matrix** action.  
1. To see the underlying insurance coverage ledger entries, choose a value in the matrix.  

## Correct insurance coverage entries

If a fixed asset was assigned to the wrong insurance policy, you can correct it by creating two reclassification entries from the insurance journal.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Insurance Journals**, and then choose the related link.  
1. Create one journal line for the fixed asset and the correct insurance policy where the value in the **Amount** field is positive.  
1. Create another journal line for the fixed asset and the incorrect insurance policy where the value in the **Amount** field is negative.  
1. Choose the **Post** action.  

The fixed asset is removed from the incorrect insurance policy on the second line. The asset is assigned to the correct insurance policy on the first line of the journal.  

## Related information

- [Insurance - List (report)](reports/report-5621.md)  
- [Insurance - Tot. Value Insured (report)](reports/report-5625.md)
- [Insurance - Uninsured FAs](reports/report-5626.md)
- [Fixed assets insurance reports](fa-reports.md#fixed-assets-insurance-reports)
- [Fixed assets analytics overview](fa-analytics-overview.md)
- [Fixed Assets](fa-manage.md)  
- [Setting Up Fixed Assets](fa-setup.md)  
- [Finance](finance.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
