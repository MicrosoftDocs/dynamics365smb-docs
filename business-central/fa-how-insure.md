---
title: Insure Fixed Assets| Microsoft Docs
Description: You can assign a fixed asset to an insurance policy, which is represented by an insurance card.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: policy, coverage
ms.date: 04/01/2020
ms.author: sgroespe

---
# Insure Fixed Assets
An insurance policy for a fixed asset is represented by an insurance card. You can assign one fixed asset to one insurance policy or multiple fixed assets to one insurance policy.

You assign a fixed asset to an insurance policy by posting to the insurance coverage ledger from the **Insurance Journal** page.

In addition, you can assign a fixed asset to an insurance policy and create coverage ledger entries when you post its acquisition cost. You do this by posting an acquisition cost from the fixed asset journal with the **Insurance No.** field filled in. The **Automatic Insurance Posting** check box on the **Fixed Asset Setup** page must be selected. For more information, see [To post a fixed asset acquisition manually with the fixed asset G/L journal](fa-how-acquire.md#to-post-a-fixed-asset-acquisition-manually-with-the-fixed-asset-gl-journal).

If the **Automatic Insurance Posting** check box on the **Fixed Asset Setup** page is not selected, then posting acquisitions from the fixed asset journal will create lines on the **Insurance Journal** page, which you must then post manually.

> [!WARNING]  
>   If you do not select the **Automatic Insurance Posting** check box on the **Fixed Asset Setup** page, then your insurance journal should be based on a journal template without a number series. This is because the inserted document numbers from the fixed asset journal line will otherwise conflict with the number series of the insurance journal. For more information about journal templates and batches, see [Set Up General Fixed Assets Information](fa-how-setup-general.md).

After you have assigned a fixed asset to an insurance policy, the **Insured** check box is selected on the fixed asset card. When you sell the fixed asset, the check box is automatically deselected.

## To create or modify an insurance card
An insurance policy for a fixed asset must be represented by an insurance card.

When you receive information about changes in the coverage amount, you must enter the new information on the **Insurance Card** page to ensure that you analyze insurance policy coverage correctly.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance**, and then choose the related link.
2. Choose the **New** action to create a new card for an insurance policy. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Alternatively, select the insurance policy that you want to change, and then choose the **Edit** action.

## To assign a fixed asset to an insurance policy by posting from the insurance journal
You assign a fixed asset to an insurance policy by posting to the insurance coverage ledger.  

The following procedure explains how to create an insurance journal line manually. If the **Automatic Insurance Posting** check box is selected on the **FA Setup** page, then insurance journal lines are automatically created when you post acquisition costs. In that case, all you have to do is to post the journal.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance Journals**, and then choose the related link.  
2. Open the relevant journal, and fill in the journal lines as necessary.  
3. To assign multiple fixed assets to one insurance policy, create journal lines with the same value in the **Insurance No.** field and different values in the **FA No.** field.  
4. Choose the **Post** action.  

    > [!NOTE]  
    >   The entries from an insurance journal are only posted to the insurance coverage ledger.  

## To update the insurance value of a fixed asset
You can use the **Index Insurance** batch job to update the value of the fixed assets that are covered.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Index Insurance**, and then choose the related link.
2. Fill in the fields as necessary.

    > [!NOTE]  
    >   In the **Index Figure** field, you enter a decrease of 5%, for example, as 95, whereas you enter an increase of 2% as 102.  
3. Choose the **OK** button.  

   The batch job calculates the new amount as a percentage of the total value insured, as stated on the **Insurance Statistics** page, and then creates a line in the insurance journal.  
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance Journals**, and then choose the related link.  
5. Open the relevant insurance journal, review the created values, and then post them to the insurance coverage ledger.  

## To monitor insurance coverage
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides dedicated reports and statistics pages for use in analyzing insurance policies and whether your fixed assets are over- or under-insured.  

### Overview of Insurance Policies
To get an overview of your insurance policies, preview or print the **Insurance - List** report. The report shows all the policies and the most important fields from the insurance cards.  

### Insurance Coverage
To see which insurance policies cover each asset and by which amount, you can preview or print the **Insurance - Tot. Value Insured** report.  

### Over/Under Coverage
You can check if fixed assets are over- or under-insured in the following ways:  

* The **Insurance Statistics** page. A positive amount in the **Over/Under Insured** field means that the fixed asset is over-insured. A negative amount means that it is underinsured.  
* The **Fixed Asset Statistics** page. Choose the **Total Value Insured** field to view the **Ins. Coverage Ledger Entries** page.  
* The **Over/Under Coverage** report.  
* The **Insurance Analysis** report.  

### Uninsured Fixed Assets
To check if you have forgotten to assign a fixed asset to an insurance policy, you can print or preview the **Insurance - Uninsured FAs** report. This report displays fixed assets for which amounts have not been posted to the insurance coverage ledger.  

## To view insurance coverage ledger entries
You can view the entries that you have made in the insurance coverage ledger.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance**, and then choose the related link.  
2. Select the relevant insurance policy, and then choose the **Coverage Ledger Entries** action.  

## To view the total insurance value of fixed assets
A dedicated matrix page shows the insurance values that are registered for each insurance policy for each fixed asset as a result of insurance-related amounts that you have posted.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance**, and then choose the related link.  
2. Select the relevant insurance policy, and then choose the **Total Value Insures per FA** action.  
3. Fill in the fields as necessary.  
4. Choose the **Show Matrix** action.  
5. To see the underlying insurance coverage ledger entries, choose a value in the matrix.  

## To correct insurance coverage entries
If a fixed asset has been attached to the wrong insurance policy, you can correct it by creating two reclassification entries from the insurance journal.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance Journals**, and then choose the related link.  
2. Create one journal line for the fixed asset and the correct insurance policy where the value in the **Amount** field is positive.  
3. Create another journal line for the fixed asset and the incorrect insurance policy where the value in the **Amount** field is negative.  
4. Choose the **Post** action.  

The fixed asset will be detached from the incorrect insurance policy, on the second line, and attached to the correct insurance policy, on the first line.  

## See Also
[Fixed Assets](fa-manage.md)  
[Setting Up Fixed Assets](fa-setup.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
