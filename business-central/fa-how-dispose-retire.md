---
title: Dispose or Retire FA| Microsoft Docs
description: You must post a disposal value when you scrap, sell, or retire a fixed asset.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: scrap
ms.date: 04/01/2020
ms.author: sgroespe

---
# Dispose of or Retire Fixed Assets
When you sell or otherwise dispose of a fixed asset, the disposal value must be posted to calculate and record the gain or loss. A disposal entry must be the last entry posted for a fixed asset. For partially disposed fixed assets, you can post more than one disposal entry. The total of all posted disposal amounts must be a credit amount.  

> [!NOTE]  
>   If you trade-in a fixed asset for another one, you must record both the sale of the old asset (disposal) and the purchase of the new one (acquisition). For more information, see [Acquire Fixed Assets](fa-how-acquire.md).  

## To post a disposal from the fixed asset G/L journal
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset G/L Journals**, and then choose the related link.  
2. Create an initial journal line and fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. In the **FA Posting Type** field, select **Disposal**.  
4. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for disposal posting.  

    > [!NOTE]  
    >   Step 4 only works if you have set up the following: On the **FA Posting Group Card** page for the posting group of the fixed asset, the **Disposal Account** field contains the general ledger debit account and the **Disposal Bal. Account** field contains the general ledger account to which you want to post balancing entries for appreciation. For more information, see [To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  
5. Choose the **Post** action.  

If you sell or dispose of part of a fixed asset, you must split up the asset before you can record the disposal transaction. For more information, see [Transfer, Split, or Combine Fixed Assets](fa-how-trans-split-combine.md).  

## To view disposal ledger entries
When you sell or dispose of a fixed asset, the disposal value is posted to the general ledger where you can view the result.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.  
2. Select the fixed asset that you want to view entries for, and then choose the **Depreciation Books** action.  
3. Select the depreciation book that you want to view entries for, and then choose the **Ledger Entries** action.  
4. Select a line with **Disposal** in the **FA Posting Category** field, and then choose the **Navigate** action.  
5. On the **Navigate** page, select the general ledger entry line, and then choose the **Show** action.  

The **General Ledger Entries** page opens where you can see the entries that the disposal posting resulted in.  

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
