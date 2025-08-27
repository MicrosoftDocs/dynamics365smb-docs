---
title: Dispose or retire FA
description: Post the disposal value when selling or retiring a fixed asset to calculate and record any gain or loss.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.devlang: al
ms.search.keywords: scrap, dispose fixed assets, retire fixed assets
ms.search.form: 5628, 5610, 5611, 5629, 5633
ms.date: 08/08/2025
ms.service: dynamics-365-business-central
---

# Dispose of or retire fixed assets

When you sell or otherwise dispose of a fixed asset, you must post the disposal value to calculate and record the gain or loss. A disposal entry must be the last entry posted for a fixed asset. For partially disposed fixed assets, you can post more than one disposal entry. The total of all posted disposal amounts must be a credit amount.  

> [!NOTE]  
> If you trade-in a fixed asset for another one, you must record both the sale of the old asset (disposal) and the purchase of the new one (acquisition). Learn more in [Acquire Fixed Assets](fa-how-acquire.md).  

The following steps assume that your posting groups are set up on the **FA Posting Groups** page. Learn more in [Set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  

## Post a disposal from the fixed asset G/L journal

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset G/L Journals**, and then choose the related link.  
2. Create an initial journal line and fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. In the **FA Posting Type** field, select **Disposal**.  
4. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for disposal posting.  

   > [!NOTE]  
   > Step 4 only works if you have set up the following: On the **FA Posting Group Card** page for the posting group of the fixed asset, the **Disposal Account** field contains the general ledger debit account and the **Disposal Bal. Account** field contains the general ledger account to which you want to post balancing entries for appreciation. Learn more in [Set up fixed asset posting groups](fa-how-setup-general.md#set-up-fixed-asset-posting-groups).  
1. Choose the **Post** action.  

If you sell or dispose of part of a fixed asset, you must split up the asset before you can record the disposal transaction. Learn more in [Transfer, Split, or Combine Fixed Assets](fa-how-trans-split-combine.md).  

## View disposal ledger entries

When you sell or dispose of a fixed asset, the disposal value is posted to the general ledger where you can view the result.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.  
2. Select the fixed asset that you want to view entries for, and then choose the **Depreciation Books** action.  
3. Select the depreciation book that you want to view entries for, and then choose the **Ledger Entries** action.  
4. Select a line with **Disposal** in the **FA Posting Category** field, and then choose the **Find Entries** action.  
5. On the **Find Entries** page, select the general ledger entry line, and then choose the **Show Related Entries** action.  

The **General Ledger Entries** page opens where you can see the entries that the disposal posting resulted in.  

## Related information

- [Fixed Assets](fa-manage.md)  
- [Setting Up Fixed Assets](fa-setup.md)  
- [To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
- [Find Entries](ui-find-entries.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
