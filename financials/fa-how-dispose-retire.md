---
title: 'How to: Dispose of or Retire Fixed Assets| Microsoft Docs'
description: Describes how to sell or retire a fixed asset.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2016
ms.author: sgroespe

---
# How to: Dispose of or Retire Fixed Assets
When you sell or otherwise dispose of a fixed asset, the disposal value must be posted to calculate and record the gain or loss. A disposal entry must be the last entry posted for a fixed asset. For partially disposed fixed assets, you can post more than one disposal entry. The total of all posted disposal amounts must be a credit amount.  

**Note:** If you trade-in a fixed asset for another one, you must record both the sale of the old asset (disposal) and the purchase of the new one (acquisition). For more information, see [How to: Acquire Fixed Assets](fa-how-acquire.md).  

## To post a disposal from the fixed asset G/L journal
1. In the top right corner, choose the **Search for Page or Report** icon, enter **FA G/L Journals**, and then choose the related link.  
2. Create an initial journal line and fill in the fields as necessary. Choose a field to read a short description of the field or link to more information.  
3. In the **FA Posting Type** field, select **Disposal**.  
4. Choose the **Insert FA Bal. Account** action. A second journal line is created for the balancing account that is set up for disposal posting.  
   
    **Note:** Step 4 only works if you have set up the following: In the **FA Posting Group Card** window for the posting group of the fixed asset, the **Disposal Account** field contains the general ledger debit account and the **Disposal Bal. Account** field contains the general ledger account to which you want to post balancing entries for appreciation. For more information, see the "To set up fixed asset posting groups" section in [How to: Set Up General Fixed Asset Information](fa-how-setup-general.md).  
5. Choose the **Post** action.  
   
    If you sell or dispose of part of a fixed asset, you must split up the asset before you can record the disposal transaction. For more information, see [How to: Transfer, Split, or Combine Fixed Assets](fa-how-trans-split-combine.md).  

## To view disposal ledger entries
When you sell or dispose of a fixed asset, the disposal value is posted to the general ledger where you can view the result.  

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Fixed Assets**, and then choose the related link.  
2. Select the fixed asset that you want to view entries for, and then choose the **Depreciation Books** action.  
3. Select the depreciation book that you want to view entries for, and then choose the **Ledger Entries** action.  
4. Select a line with **Disposal** in the **FA Posting Category** field, and then choose the **Navigate** action.  
5. In the **Navigate** window, select the general ledger entry line, and then choose the **Show** action.  

The **General Ledger Entries** window opens where you can see the entries that the disposal posting resulted in.  

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Welcome to Dynamics 365 for Financials](madeira-get-started.md)  
[Working With Financials](ui-work-product.md)

