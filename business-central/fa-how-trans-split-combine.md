---
title: Reclassify fixed assets
description: You reclassify a fixed asset to transfer it to a different department, split it up, or combine it with other fixed assets.
author: brentholtorf
ms.topic: how-to
ms.search.form: 5638, 5636, 5640, 5637, Report_5606
ms.date: 11/07/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Transfer, split, or combine fixed assets

You can reclassify a fixed asset to transfer it to a different department, split it up, or combine it with other fixed assets. These registrations are done using the fixed asset reclassification journal.

To explore the results of fixed asset reclassifications, use the [Fixed Asset Book Value 02](reports/report-5606.md) report.

## To transfer a fixed asset to a different department

You might need to transfer a fixed asset to a different department. For example, when you put an asset in the production department for assembly and then move it to the administration department afterward.  

1. Set up a new fixed asset. Enter the new department as a dimension.  
2. Assign a fixed asset depreciation book to the new fixed asset. For more information, see [Acquire Fixed Assets](fa-how-acquire.md).
3. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset Reclassification Journals**, and then choose the related link.
4. Create a journal line where the **FA No.** field contains the original fixed asset, and the **New FA No.** field contains the new fixed asset to be moved. Fill in the other fields as appropriate.  
5. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you specify on the **FA Journal Setup** page for the depreciation book. For more information, see [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).
6. [!INCLUDE[open-search](includes/open-search.md)], enter **FA G/L Journals**, and then choose the related link.    
7. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 4 and 5.

If you posted an acquisition cost for an asset, you can use the fixed asset reclassification journal to split the acquisition cost among several assets.  

## To split a fixed asset into three fixed assets

You can split one fixed asset into multiple fixed assets. For example, when you need to distribute a fixed asset across three departments. In that case, you might move 25 percent of the acquisition cost and depreciation for the original fixed asset to the second fixed asset, and 45 percent to the third asset. The remaining 30 percent remains on the original fixed asset.

1. Set up two new fixed assets. Enter the relevant departments as dimensions.  
2. Assign fixed asset depreciation books to the new fixed assets. For more information, see [Acquire Fixed Assets](fa-how-acquire.md).
3. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset Reclassification Journals**, and then choose the related link.
4. Create two reclassification journal lines, one for each new fixed asset.
5. On the first line, enter the second fixed asset in the **New FA No.** field and **25** in the **Reclassify Acq. Cost %** field.
6. On the second line, enter the third fixed asset in the **New FA No.** field and **40** in the **Reclassify Acq. Cost %** field.
7. On both lines, select the **Reclassify Acquisition Cost** and **Reclassify Depreciation** checkboxes.  
8. Choose the **Reclassify** action.  

    Two lines are now created in the fixed asset G/L journal using the template and batch that you specified on the **FA Journal Setup** page for the specified depreciation book. For more information, see [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).    
9. [!INCLUDE[open-search](includes/open-search.md)], enter **FA G/L Journals**, and then choose the related link.
10. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 4 through 8.


## To combine two fixed assets into one

You can combine multiple fixed assets into one fixed asset, for example when you move distributed fixed assets into one department. If you posted acquisition costs and depreciation for the fixed asset to move, those values are combined in the single fixed asset.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset Reclassification Journals**, and then choose the related link.
2. Create a reclassification journal where the **FA No.** field contains the fixed asset to move or combine, and the **New FA No.** field contains the combined fixed asset.
3. Leave the **Reclassify Acq. Cost %** field empty to move/combine the entire acquisition cost.  
4. Select the **Reclassify Acquisition Cost** and **Reclassify Depreciation** checkboxes.
5. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you specified on the **Fixed Asset Journal Setup** page for the specified depreciation book. For more information, see [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).  
6. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset G/L Journals**, and then choose the related link.
7. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 2 through 5.

## To view changed depreciation book values due to fixed asset reclassification

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Asset Book Value 02**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.  

For more information, see [Fixed Asset Book Value 02 (report)](reports/report-5606.md).

## Related information

[Fixed Asset Book Value 02 (report)](reports/report-5606.md)  
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
