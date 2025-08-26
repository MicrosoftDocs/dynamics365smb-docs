---
title: Reclassify fixed assets
description: Reclassify a fixed asset to move it to another department, split acquisition cost and depreciation among multiple assets, or combine assets into one.
author: brentholtorf
ms.topic: how-to
ms.search.form: 5638, 5636, 5640, 5637, Report_5606
ms.search.keywords: reclassify, fixed assets, transfer, split, combine
ms.date: 08/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Transfer, split, or combine fixed assets

You can reclassify a fixed asset to transfer it to a different department, split it up, or combine it with other fixed assets. These registrations are done using the fixed asset reclassification journal.

To explore the results of fixed asset reclassifications, use the [Fixed Asset Book Value 02](reports/report-5606.md) report.

## Transfer a fixed asset to a different department

You might need to transfer a fixed asset to a different department. For example, when you put an asset in the production department for assembly and then move it to the administration department afterward.  

1. Set up a new fixed asset. Enter the new department as a dimension.  
1. Assign a fixed asset depreciation book to the new fixed asset. Learn more in [Acquire Fixed Assets](fa-how-acquire.md).
1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Reclassification Journals**, and then choose the related link.
1. Create a journal line where the **FA No.** field contains the original fixed asset, and the **New FA No.** field contains the new fixed asset to be moved. Fill in the other fields as appropriate.  
1. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you specify on the **FA Journal Setup** page for the depreciation book. Learn more in [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).
1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.
1. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 4 and 5.

If you posted an acquisition cost for an asset, you can use the fixed asset reclassification journal to split the acquisition cost among several assets.  

## Split a fixed asset into three fixed assets

You can split one fixed asset into multiple fixed assets. For example, when you need to distribute a fixed asset across three departments. In that case, you might move 25 percent of the acquisition cost and depreciation for the original fixed asset to the second fixed asset, and 45 percent to the third asset. The remaining 30 percent remains on the original fixed asset.

1. Set up two new fixed assets. Enter the relevant departments as dimensions.  
1. Assign fixed asset depreciation books to the new fixed assets. Learn more in [Acquire Fixed Assets](fa-how-acquire.md).
1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Reclassification Journals**, and then choose the related link.
1. Create two reclassification journal lines, one for each new fixed asset.
1. On the first line, enter the second fixed asset in the **New FA No.** field and **25** in the **Reclassify Acq. Cost %** field.
1. On the second line, enter the third fixed asset in the **New FA No.** field and **40** in the **Reclassify Acq. Cost %** field.
1. On both lines, select the **Reclassify Acquisition Cost** and **Reclassify Depreciation** checkboxes.
1. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you specified on the **FA Journal Setup** page for the specified depreciation book. Learn more in [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).
1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.
1. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 4 through 8.

## Combine two fixed assets into one

You can combine multiple fixed assets into one fixed asset, for example when you move distributed fixed assets into one department. If you posted acquisition costs and depreciation for the fixed asset to move, those values are combined in the single fixed asset.

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Reclassification Journals**, and then choose the related link.
1. Create a reclassification journal where the **FA No.** field contains the fixed asset to move or combine, and the **New FA No.** field contains the combined fixed asset.
1. Leave the **Reclassify Acq. Cost %** field empty to move/combine the entire acquisition cost.  
1. Select the **Reclassify Acquisition Cost** and **Reclassify Depreciation** checkboxes.
1. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you specified on the **Fixed Asset Journal Setup** page for the specified depreciation book. Learn more in [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).  
1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset G/L Journals**, and then choose the related link.
1. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 2 through 5.

## View changed depreciation book values due to fixed asset reclassification

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Book Value 02**, and then choose the related link.
1. Fill in the fields as necessary.
1. Choose the **Print** or **Preview** button.  

Learn more in [Fixed Asset Book Value 02 (report)](reports/report-5606.md).

## Related information

- [Fixed Asset Book Value 02 (report)](reports/report-5606.md)  
- [Fixed Assets](fa-manage.md)  
- [Setting Up Fixed Assets](fa-setup.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
