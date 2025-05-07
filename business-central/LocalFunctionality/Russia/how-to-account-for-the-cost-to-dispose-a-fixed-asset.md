---
title: Account for the cost to dispose fixed asset in Russia
description: Russian enhancements include accounting for the cost of disposing of fixed assets.
author: DianaMalina
ms.topic: how-to
ms.search.keywords:
ms.date: 11/14/2023
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Account for the cost to dispose a fixed asset

The maintenance on disposal feature enables you to account for the amount spent to dispose a fixed asset (FA) as an expense. You can post operations related to spending for the disposal of a fixed asset, so that they're reflected in the FA Write-Off Act forms. 

The expenses of a fixed asset disposal can be posted from general ledger journals, fixed asset journals, and purchase documents. The following procedure shows how to post the expenses for a fixed asset disposal by using the Fixed Asset General Ledger Journal. 

The expenses on a fixed asset disposal can be printed in the FA Write-off Act FA-4 report and the FA Write-off Act FA-4a report.

## To set up a maintenance code

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Setup**, and then choose the related link.
2. In the **Fixed Asset Setup** window, on the **General** FastTab, enter a maintenance code in the **On Disposal Maintenance Code** field.
3. Choose the **OK** button.

## To post expenses on a fixed asset disposal

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.

2. In the **Fixed Asset G/L Journal** window, fill in the fields as described in the following table.

   | Field                | Description                                                  |
   | :------------------- | :----------------------------------------------------------- |
   | **Account Type**     | Select **Fixed Asset** as the account type.                  |
   | **Account No.**      | Specifies the number of the fixed asset for disposal for which the expenses are made. |
   | **FA Posting Type**  | Select **Maintenance** as the fixed asset posting type.      |
   | **Maintenance Code** | Specifies the maintenance code that is entered in the **On Disposal Maintenance Code** field of the **Fixed Asset Setup** window. |

3. Choose the **OK** button.

## To print a report with expenses on a fixed asset disposal

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Write off Act**, and then choose the related link.

2. In the **FA Write off Act** window, enter the expenses that are posted for the fixed asset.

3. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.

    > [!NOTE]
    > If the expenses on the disposal of the fixed asset are made in advance, they are displayed on the second page of the report.

After the fixed asset write-off report is posted, it becomes the posted fixed asset write-off report.

## Related information

[Fixed Assets](../../fa-manage.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
