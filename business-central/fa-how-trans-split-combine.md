---
title: Reclassify Fixed Assets| Microsoft Docs
description: You reclassify a fixed asset to transfer it to a different department, split it up, or combine it with other fixed assets.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2020
ms.author: sgroespe

---
# Transfer, Split, or Combine Fixed Assets
You use the fixed asset reclassification journal to transfer, split up, and combine fixed assets. You view or print the results of fixed asset reclassification with the **Fixed Asset-Book Value 02** report.

## To transfer a fixed asset to a different department
You may need to transfer a fixed asset to a different department when, for example, you place an asset in the production department while it is under construction and then move it to the administration department when it is finished.  

1. Set up a new fixed asset. Enter the new department in the **Department Code** field.
2. Assign a fixed asset depreciation book to the new fixed asset. For more information, see [Acquire Fixed Assets](fa-how-acquire.md).
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journals**, and then choose the related link.
4. Create a reclassification journal where the **FA No.** field contains the original fixed asset, and the **New FA No.** field contains the new fixed asset to be moved.  
5. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you have specified on the **FA Journal Setup** page for the specified depreciation book. For more information, see [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.    
7. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 4 and 5.

If you have posted an acquisition cost for one asset, you can use the fixed asset reclassification journal to split the acquisition cost among several assets.  

## To split a fixed asset into three fixed assets
You can split one fixed asset into multiple fixed assets, for example when you need to distribute a fixed asset onto three different departments. In that case, you can move, for example, 25 percent of the acquisition cost and depreciation for the original fixed asset to the second fixed asset and 45 percent to the third asset. The remaining 30 percent will remain on the original fixed asset.

1. Set up two new fixed assets. Enter the new department in the **Department Code** field.
2. Assign fixed asset depreciation books to the new fixed assets. For more information, see [Acquire Fixed Assets](fa-how-acquire.md).
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journals**, and then choose the related link.
4. Create two reclassification journal lines, one for each new fixed asset.
5. On the first line, enter the second fixed asset in the **New FA No.** field and 25 in the **Reclassify Acq. Cost %** field.
6. On the second line, enter the third fixed asset in the **New FA No.** field and 40 in the **Reclassify Acq. Cost %** field.
7. On both lines, select the **Reclassify Acquisition Cost** and **Reclassify Depreciation** check boxes.   
8. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you have specified on the **FA Journal Setup** page for the specified depreciation book. For more information, see [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).    
9. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.
10. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 4 through 8.

## To combine two fixed assets into one
You can combine multiple fixed assets into one fixed asset, for example when you move distributed fixed assets into one department. If you have posted acquisition costs and depreciation for the fixed asset to be moved, those values will be combined in the single fixed asset.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journals**, and then choose the related link.
2. Create a reclassification journal where the **FA No.** field contains the fixed asset to be moved/combined, and the **New FA No.** field contains the fixed asset that it will be combined with.
3. Leave the **Reclassify Acq. Cost %** field empty to move/combine the entire acquisition cost.    
4. Select the **Reclassify Acquisition Cost** and **Reclassify Depreciation** check boxes.
5. Choose the **Reclassify** action.

    Two lines are now created in the fixed asset G/L journal using the template and batch that you have specified on the **FA Journal Setup** page for the specified depreciation book. For more information, see [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md).   
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.
7. On the **Fixed Asset G/L Journal** page, choose the **Post** action to post the reclassification that you performed in steps 2 through 5.

## To view changed depreciation book values due to fixed asset reclassification
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Book Value 02**, and then choose the related link.
2. Fill in the fields as necessary.
3. Choose the **Print** or **Preview** button.  

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
