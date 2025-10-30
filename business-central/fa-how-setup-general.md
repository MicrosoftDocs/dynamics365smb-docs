---
title: Set Up General Fixed Assets (FA) Information
description: Configure default G/L accounts, FA posting groups, allocation keys, journal templates and batches, and class and subclass codes before using fixed assets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: how-to
ms.search.form: 5623, 5615_Primary, 5616_Primary, 5661, 5662, 5627, 5620, 5629, 5633, 5609, 5631, 5630, 5617, 5612, 5613, 5608, 5609, 5635, 9277
ms.search.keywords: fixed assets, G/L accounts, posting groups, allocation keys, journal templates, journal batches, class codes, subclass codes
ms.date: 10/03/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up general fixed assets information

Before you can manage fixed assets (FA), you must set up default G/L accounts, allocation keys, and journal templates and batches to post and reclassify fixed assets. Also, define a classification hierarchy (classes and sub classes) to structure your assets and, if needed, define the locations where you store assets.

## Set up general behavior for fixed assets functionality

Define the general behavior of the fixed asset functionality and its document number series on the **Fixed Assets Setup** page.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets Setup**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Set up fixed asset posting groups

Use posting groups to define groups of fixed assets. Entries for these posting groups post to the same general ledger accounts.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Posting Groups**, and then choose the related link.  
2. Choose the **New** action.
3. On the **FA Posting Group Card** page, fill in the fields as necessary.

    > [!NOTE]  
    > To make sure that balancing accounts for different fixed assets postings are automatically inserted when you choose the **Insert FA Bal. Account** action on journal lines, follow the next step, based on appreciation posting.
4. On the **Balancing Account** FastTab, in the **Appreciation Bal. Account** field, select the general ledger account to which you want to post balancing entries for appreciation.

Learn more in [Revalue Fixed Assets](fa-how-revalue.md) for information about using the **Insert FA Bal. Account** action on fixed asset G/L journal lines.

## Set up fixed asset journal templates

A template is a predefined layout for a journal. The template contains information about trace codes, reports, and number series. Learn more in [Work with General Journals](ui-work-general-journals.md).

[!INCLUDE[prod_short](includes/prod_short.md)] automatically creates a fixed asset journal template the first time that you open the **Fixed Asset Journal** page, but you can set up other journal templates.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Journal Templates**, and then choose the related link.  
2. Fill in the fields as necessary.

## Set up fixed asset class and subclass codes

In fixed assets, you can define a classification hierarchy that can be used to group assets. The hierarchy has two levels: classes and subclasses.

### Fixed asset class codes

Fixed asset classes are the top-level entries in the classification hierarchy in which you group assets. For example, use classes to divide assets into tangible or intangible assets. You must create at least one fixed asset class in your setup.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Classes**, and then choose the related link.
2. Enter codes and names for the fixed asset classes that you want to create.

### Fixed asset subclass codes

Fixed asset subclasses are the second level entries in the classification hierarchy in which you group assets. Each subclass points to a top-level class. Use fixed asset subclass codes to group fixed assets in more specific categories, such as buildings, vehicles, furniture, or machinery. You must create at least one fixed asset subclass in your setup.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Subclasses**, and then choose the related link.
2. Enter codes and names for the fixed asset subclasses that you want to create.

## Start to register assets

If you're using the fixed assets in [!INCLUDE[prod_short](includes/prod_short.md)] for the first time, you must set up the general ledger application area before you set up fixed assets. How you do so depends on whether you integrate fixed assets with the general ledger.  

The following procedure is used if fixed asset transactions are to be posted to the general ledger.  

1. Complete the basic setups for fixed assets.  
2. Fill in a fixed asset card for each existing asset.  
3. Create a fixed asset depreciation book for each depreciation purpose (such as tax and financial statements). For each depreciation book, define the terms and conditions, such as integration with the general ledger.

    Enable general ledger integration by following the next steps. First, ensure that general ledger integration isn't enabled for all depreciation books, then post the opening entries, and finally, turn on general ledger integration.  
4. [!INCLUDE[open-search](includes/open-search.md)], enter **Depreciation Books**, and then choose the related link.  
5. Select the relevant depreciation book, and then choose the **Edit** action to open the **Depreciation Book Card** page.
6. On the **Integration** FastTab, turn off all of the toggles. If you have more than one depreciation book, repeat this step for each one.  
7. In the fixed asset journal, enter the following lines for each asset:
   * A line with the acquisition cost.
   * A line with the accumulated depreciation to the end of the previous fiscal year.
   * A line with the accumulated depreciation from the start of the current fiscal year to the date that [!INCLUDE[prod_short](includes/prod_short.md)] is set to start calculating the depreciation.

    If you have other opening balances you can also enter them now, such as write-down and appreciation.  
8. After you enter and post the journal lines for each asset, turn on general ledger integration in the
depreciation books.

If the fixed assets aren't integrated with the general ledger, skip steps six and eight.

## Set up fixed asset location codes (optional)

Fixed asset location codes define identifiers for where assets can be located, such as sales department, reception, administration, production, or warehouse. You can use them to register the location of a fixed asset. This information is useful for insurance and inventory purposes.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA locations**, and then choose the related link.
2. Enter codes and names for the fixed asset locations that you want to create.

## Set up fixed asset allocation keys (optional)

Use allocation keys to allocate transactions to various departments or projects. For example, you can set up an allocation key to allocate vehicle depreciation costs with 35 percent to the administration department and 65 percent to the sales department. Learn more in [Allocate Costs and Income](year-allocate-costs-income.md).

Allocation keys apply to fixed asset classes, not to individual assets.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Posting Groups**, and then choose the related link.  
2. On the **FA Posting Groups** page, choose the **Allocations** action, and then choose a posting type.
3. On the **FA Allocations** page, fill in the fields as necessary.
4. Repeat steps 2 and 3 for each posting type that you want to define allocation keys for.

## Set up fixed asset journal batches (optional)

You can set up multiple journal batches, which are individual journals for each journal template. For example, employees can have their own journal batch that uses the employee’s initials as the journal batch name. Learn more in [Work with General Journals](ui-work-general-journals.md).  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Journal Templates**, and then choose the related link.  
2. Select the relevant journal template, and then choose the **Batches** action.
3. On the **FA Journal Batches** page, fill in the fields as necessary.

## Set up fixed asset reclassification journal templates (optional)

Use dedicated reclassification journals to transfer, split, or combine fixed assets. [!INCLUDE[prod_short](includes/prod_short.md)] automatically creates a fixed asset reclassification journal template the first time you open the **FA Reclass. Journal** page, but you can set up other reclassification journal templates. Learn more in [Work with General Journals](ui-work-general-journals.md).  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Reclass. Journal Templates**, and then choose the related link.  
2. Fill in the fields as necessary.

## Set up fixed asset reclassification journal batches (optional)

You can set up multiple journal batches, which are individual journals for each reclassification journal template. For example, employees can have their own reclassification journal batch that uses the employee’s initials as the reclassification journal batch name. Learn more in [Work with General Journals](ui-work-general-journals.md).

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Reclass. Journal Templates**, and then choose the related link.  
2. Select the relevant journal template, and then choose the **Batches** action.
3. On the **FA Reclass. Journal Batches** page, fill in the fields as necessary.

## Related information

[Setting Up Fixed Assets](fa-setup.md)  
[Fixed Assets overview](fa-manage.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
