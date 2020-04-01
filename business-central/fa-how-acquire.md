---
title: Acquire Fixed Assets| Microsoft Docs
description: You can set up a fixed asset, assign a depreciation book, and record the fixed asset’s acquisition cost.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: purchase fixed asset
ms.date: 04/01/2020
ms.author: sgroespe

---
# Acquire Fixed Assets
For each fixed asset, you must set up a card containing information about the asset. You can set up buildings or production equipment as a main asset with a component list, and you can group them in various ways, such as by class, department, or location. A depreciation book must be set up and assigned to each fixed asset before you can acquire it.

When a fixed asset is set up and a depreciation book assigned, you must acquire the fixed asset. To acquire a fixed asset, you record its acquisition cost in the relevant G/L account, bank account, or vendor by posting an acquisition transaction from the **Fixed Asset G/L Journal** page. You can use the **Assisted Fixed Asset Acquisition** page to create and post the required general journal lines automatically.

The salvage value is the residual value of a fixed asset when it can no longer be used. You can post the salvage value at the same time as you post the acquisition cost. For more information, see [Depreciate or Amortize Fixed Assets](fa-how-depreciate-amortize.md).

Indexation is used to adjust values for general price-level changes. The **Index Fixed Assets** batch job can be used to calculate the acquisition costs at replacement costs.

## To create a fixed asset and acquire it automatically
The following procedure describes how to create a fixed asset and then acquire it by using the **Assisted Fixed Asset Acquisition** page to create and post the required fixed asset G/L journal lines. You can also create and post the journal lines manually. For more information, see [To post a fixed asset acquisition manually with the fixed asset G/L journal](fa-how-acquire.md#to-post-a-fixed-asset-acquisition-manually-with-the-fixed-asset-gl-journal).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields on the **General** FastTab as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. On the **Depreciation Book** FastTab, fill in the fields as necessary. This step assigns a depreciation book to the fixed asset.  
4. If you need to assign more than one depreciation book to the fixed asset, choose the **Add More Depreciation Books** action. For more information, see [To assign a depreciation book to a fixed asset](fa-how-setup-depreciation.md#to-assign-a-depreciation-book-to-a-fixed-asset).

    When all fields required to acquire a fixed asset are filled in, the **You are ready to acquire the fixed asset. Acquire** notification appears at the top of the page.
5. Choose the **Acquire** action in the notification.
6. Follow the steps on the **Assisted Fixed Asset Acquisition** page to complete the automatic acquisition of the fixed asset.

> [!NOTE]  
>   You can also post acquisition cost as credits. In that case, remember that the value in the **Acquisition Cost Incl. VAT** field must be with a minus sign to indicate a credit.

When you choose **Finish**, the **Book Value** field on the **Fixed Asset Card** page is filled, indicating that the fixed asset has been acquired at the specified acquisition cost.  

## To set up a component list for a main asset
You can group your fixed assets into main assets and their components. For example, you may have a production machine that consists of many parts that you want to group in this manner.  

Both the main asset and all its components must be set up as individual fixed asset cards. After you have set up a component list, [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically fills in the **Main Assets/Component** and **Components of Main Asset** fields on the fixed asset cards.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that is the main asset, and then choose the **Main Asset Components** action.
3. On the **Main Asset Components** page, choose the **FA No**. field, and then select the fixed asset that you want to add as a component of the main asset.
4. Close the page.
5. Repeat steps 3 and 4 for each component asset that you want to add.
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Setup**, and then choose the related link.
7. Select the **Allow Posting to Main Assets** check box.

## To post a fixed asset acquisition manually with the fixed asset G/L journal
The following procedure describes how to acquire a fixed asset manually by creating and posting lines on the **Fixed Asset G/L Journal** page. You can also acquire a fixed asset automatically by using the **Assisted Fixed Asset Acquisition** page. For more information, see step 5 in [To create a fixed asset and acquire it automatically](fa-how-acquire.md#to-create-a-fixed-asset-and-acquire-it-automatically).

> [!NOTE]  
>   You can also post acquisition cost as credits. In that case, remember that the value in the **Amount** field must be with a minus sign to indicate a credit.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA G/L Journals**, and then choose the related link.
2. On the **Fixed Asset G/L Journal** page, in the **FA Posting Type** field, select **Acquisition Cost**.
3. Fill in the remaining fields as necessary.
4. Choose the **Post** action.  

> [!TIP]  
>   If you fill in the **Insurance No.** field in the fixed asset G/L journal when you post an acquisition cost, then [!INCLUDE[d365fin](includes/d365fin_md.md)] will also post the acquisition cost of the fixed asset to the insurance coverage ledger. For more information, see [Insure Fixed Assets](fa-how-insure.md).

## To cancel an acquisition cost posting for one fixed asset
If you make an error when posting an acquisition cost, you can remove the entry with the **Cancel FA Entries** batch job and then post the correct acquisition entry. The erroneous entries are transferred to the **FA Error Ledger Entries** page.

For example, if you post an acquisition with the wrong date, you must correct it as soon as possible because the fixed asset posting date is used is many critical calculations.

> [!IMPORTANT]  
>   You cannot use the **Reverse Transactions** function for fixed asset entries.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cancel FA Entries**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choose the **OK** button to run the batch job.
4. When the incorrect entry or entries are canceled, proceed to post the correct acquisition cost.

To cancel ledger entries for multiple fixed assets at a time, use the **Cancel FA Ledger Entries** batch job.

## To post the salvage value together with the acquisition cost
You can post the salvage value together with the acquisition cost from a fixed asset journal.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journals**, and then choose the related link.
2. On the **Fixed Asset Journals** page, create the acquisition line. For more information, see [To post a fixed asset acquisition manually with the fixed asset G/L journal](fa-how-acquire.md#to-post-a-fixed-asset-acquisition-manually-with-the-fixed-asset-gl-journal).
3. In the **Salvage Value** field on the journal line, enter the salvage value amount as a credit (with a minus sign).
4. Choose the **Post** action.

> [!NOTE]
> If a salvage value exists for a fixed asset, then that value will be used in depreciation posting instead of the value in the **Ending Book Value** field on the **FA Depreciation Books** page. For more information, see [To manage the ending book value](fa-how-depreciate-amortize.md#to-manage-the-ending-book-value).

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
