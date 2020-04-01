---
title: Set Up General Ledger FA| Microsoft Docs
description: Before you work with fixed assets, you must set up default G/L accounts, posting groups, allocation keys, journal templates and batches, and class codes.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2020
ms.author: edupont

---
# Set Up General Fixed Assets Information
Before you can manage fixed assets, you must set up default G/L accounts, allocation keys, journal templates and batches for fixed asset posting and reclassification, and you can classify fixed assets in classes, such as Tangible and Intangible.

## To set up general default values for fixed assets
You define the general behavior or the fixed asset functionality and set up document number series in the  on the **Fixed Assets Setup** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets Setup**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set up fixed asset posting groups
You use posting groups to define groups of fixed assets. Entries for these posting groups are posted to the same general ledger accounts.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Posting Groups**, and then choose the related link.  
2. Choose the **New** action.
3. On the **FA Posting Group Card** page, fill in the fields as necessary.

    > [!NOTE]  
    >   To make sure that balancing accounts for different fixed assets postings are automatically inserted when you choose the **Insert FA Bal. Account** action on journal lines, follow the next step, based on appreciation posting.
4. On the **Balancing Account** FastTab, in the **Appreciation Bal. Account** field, select the general ledger account to which you want to post balancing entries for appreciation.

For more information about using the **Insert FA Bal. Account** action on fixed asset G/L journal lines, see, for example, [Revalue Fixed Assets](fa-how-revalue.md).

## To set up fixed asset allocation keys
Transactions can be allocated to various departments or projects, according to user-defined allocation keys. For example, you could set up an allocation key to allocate depreciation costs on cars with 35 percent to the administration department and 65 percent to the sales department. For more information, see [Allocate Costs and Income](year-allocate-costs-income.md).

Allocation keys apply to fixed asset classes, not to individual assets.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Posting Groups**, and then choose the related link.  
2. On the **FA Posting Groups** page, choose the **Allocations** action, and then choose a posting type.
3. On the **FA Allocations** page, fill in the fields as necessary.
4. Repeat steps 2 and 3 for each posting type that you want to define allocation keys for.

## To set up fixed asset journal templates
A template is a predefined layout for a journal. The template contains information about trace codes, reports, and number series. For more information, see [Working with General Journals](ui-work-general-journals.md).

[!INCLUDE[d365fin](includes/d365fin_md.md)] automatically creates a fixed asset journal template the first time that you open the **Fixed Asset Journal** page, but you can set up additional journal templates.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journal Templates**, and then choose the related link.  
2. Fill in the fields as necessary.

## To set up fixed asset journal batches
You can set up multiple journal batches, which are individual journals for each journal template. For example, employees can have their own journal batch that uses the employee’s initials as the journal batch name. For more information, see [Work with General Journals](ui-work-general-journals.md).  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Journal Templates**, and then choose the related link.  
2. Select the relevant journal template, and then choose the **Batches** action.
3. On the **FA Journal Batches** page, fill in the fields as necessary.

## To set up fixed asset reclassification journal templates
You use dedicated reclassification journals when you need to transfer, split, or combine fixed assets. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically creates a fixed asset reclassification journal template the first time that you open the **FA Reclass. Journal** page, but you can set up additional reclassification journal templates. For more information, see [Work with General Journals](ui-work-general-journals.md).  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journal Templates**, and then choose the related link.  
2. Fill in the fields as necessary.

## To set up fixed asset reclassification journal batches
You can set up multiple journal batches, which are individual journals for each reclassification journal template. For example, employees can have their own reclassification journal batch that uses the employee’s initials as the reclassification journal batch name. For more information, see [Work with General Journals](ui-work-general-journals.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Reclass. Journal Templates**, and then choose the related link.  
2. Select the relevant journal template, and then choose the **Batches** action.
3. On the **FA Reclass. Journal Batches** page, fill in the fields as necessary.

## To set up fixed asset class codes
Fixed asset class codes can be used to group fixed assets, for example, in tangible and intangible assets.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Classes**, and then choose the related link.
2. Enter codes and names for the classes that you want to create.

## To set up fixed asset subclass codes
You use fixed asset subclass codes to group your fixed assets into categories, such as buildings, vehicles, furniture, or machinery.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Subclasses**, and then choose the related link.
2. Enter codes and names for the classes that you want to create.

## To set up fixed asset location codes
You use fixed asset location codes to register the location of the fixed asset, such as sales department, reception, administration, production, or warehouse. This information is useful for insurance and inventory purposes.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA locations**, and then choose the related link.
2. Enter codes and names for the fixed asset locations that you want to create.

## To register opening entries
If you are using the fixed assets in [!INCLUDE[d365fin](includes/d365fin_md.md)] for the first time, you must set up the general ledger application area before you set up fixed assets. How you do this depends on whether fixed assets is integrated with general ledger.  

 The following procedure is used if fixed asset transactions are to be posted to the general ledger.  

1. Make sure that you have completed the basic setup procedures for fixed assets.  
2. Create a fixed asset card for each existing asset.  
3. Create a fixed asset depreciation book for each depreciation purpose (such as tax and financial statements). For each depreciation book, you must define the terms and conditions, such as integration with general ledger.  

    Enable general ledger integration by following the next steps. First, make sure that general ledger integration is disabled for all depreciation books, then post the opening entries, and finally, turn on general ledger integration.  
4. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Depreciation Books**, and then choose the related link.  
5. Select the relevant depreciation book, and then choose the **Edit** action to open the **Depreciation Book Card** page.
6. On the **Integration** FastTab, make sure all fields are blank by clearing all check marks. If you have more than one depreciation book, turn off general ledger integration for each one.  
7. In the fixed asset journal, enter the following lines for each asset:
   * A line with the acquisition cost.
   * A line with the accumulated depreciation to the end of the previous fiscal year.
   * A line with the accumulated depreciation from the start of the current fiscal year to the date that [!INCLUDE[d365fin](includes/d365fin_md.md)] is set to start calculating the depreciation.

    If you have other opening balances you can also enter them now, such as write-down and appreciation.  
8. After you have entered and posted the journal lines for each asset, turn on general ledger integration in the
depreciation books.

If the fixed assets are not integrated with the general ledger, skip step 6 and 8.

## See Also
[Setting Up Fixed Assets](fa-setup.md)  
[Fixed Assets](fa-manage.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
