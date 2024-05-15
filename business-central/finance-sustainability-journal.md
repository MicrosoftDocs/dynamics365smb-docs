---
title: Record sustainability entries
description: Learn how to record greenhouse gas (GHG) emissions.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, journal
ms.search.form: 6216, 6219, 6220
ms.date: 05/07/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Record sustainability entries

Currently, the only way to record greenhouse gas (GHG) emissions in the sustainability ledger is to use sustainability journals.

## Sustainability journals

Sustainability journals are designed to track and record sustainability-related activities by using the same user experience as other journals in Business Central. Users who have the necessary information can manually enter emissions in a journal. Alternatively, if they lack the information, they can use built-in formulas to accurately calculate emissions based on specific known parameters that correspond to various types of sources and accounts.

The information that you enter in a journal is temporary and can be changed while it's in that journal. When you post the journal, the information is transferred to sustainability ledger entries on individual sustainability accounts, where it can't be changed. However, you can post reversing or correcting entries.

### Use journal templates and batches

By default, there are two sustainability journal templates: the standard template and the recurring template.

For each journal template, you can set up your own personal journal as a journal batch. To do so, select the **Batches** action on the **Sustainability Journal Templates** page, and then create the new **sustainability journal batch** on the new page. For example, you can define your own journal batch for each emission scope by using the **Emission Scope** option and then selecting among the three existing scopes. For each batch, you can add or change the **Source Code** and **Reason Code** values.

> [!TIP]
> If you have many lines, you can help reduce the risk of mistakes by having one journal batch for each emission type. Alternatively, you can use the common batch for all emission types.

### Validate sustainability journals

On the **Sustainability Setup** page, you can turn on a background check to help prevent posting delays. If any mistakes that occur while you work in the sustainability journal, the validation notifies you and prevents you from posting the journal.

When you enable the validation, the **Journal Check** FactBox shows issues on the current line and in the whole batch. Validation occurs when you load a journal batch and when you select another journal line. The **Issues Total** tile in the FactBox shows the total number of issues that [!INCLUDE [prod_short](includes/prod_short.md)] found. You can select the tile to open an overview of the issues.

### Work with sustainability journals

To start to work with sustainability journals, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link.
2. On the **Sustainability Journal** page, enter as many lines as you plan to post in the same batch.
3. You can leave the **Document Type** field blank, or you can select **Invoice** or **Credit Memo**.
4. In the **Account No.** field, you can select only non-blocked sustainability accounts where the **Direct Posting** field is selected and the **Accounting Type** field is set to **Posting**. The accounts must also be configured with a category and a subcategory.

    > [!NOTE]
    > If you use a batch where the emission scope is configured, the **Emission Scope** value in the sustainability account must equal the **Emission Scope** value in the batch.

5. You can either manually post the amounts or use formulas.

    - If you have accurate information about the emission and want to post it (that is, if you have the information on the received invoice), select the **Manual Input** field to indicate that you'll manually enter the amounts. In this case, you can't enter your data directly in the **Fuel/Electricity**, **Distance**, **Custom Amount**, **Installation Multiplier**, and **Time Factor** fields, because they become noneditable. However, the **Emission CO2**, **Emission CH4**, and **Emission N2O** fields remain editable, and you can enter your data directly in them.
    - If you don't have accurate knowledge of the emission and must calculate it, don't select the **Manual Input** field. In this case, the **Emission CO2**, **Emission CH4**, and **Emission N2O** fields become noneditable. However, you can enter your calculation details based on the formula that you're using. Learn more about the formulas that are and defined in the **sustainability account category** in [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md#account-categories).

6. To post the journal, select the **Post** action. When you post in a sustainability journal, entries are generated in the sustainability ledger.

If your formula is based on the **Calculate from General Ledger** option in the sustainability account category, you must use the **Collect Amount from G/L Entries** action before you post the journal, to calculate emissions based on this data source. Additionally, if you made changes to the emission factors after the journal lines were populated, you must select the **Recalculate** action to get the proper amount in the journal.

### Recurring journals

A recurring journal is a sustainability journal that has specific fields for managing transactions that you often post with few, if any, changes. Examples include sustainability transactions such as electricity or heat, or other similar transactions. You can use recurring journals to post fixed and variable amounts.

When you use a recurring journal, entries that you'll regularly post must be created only one time. Information such as the accounts, dimensions, and dimension values remain in the journal after posting. Each time that you post, you can make any changes that are needed.

The **Recurring Method** field is important. It determines how the amount on the journal line is handled after posting. For example, if you use the same amount every time that you post the line, you can select the **F Fixed** option to let the amount remain after posting. If you use the same accounts and text on the line, but the amount varies every time that you post, you can select the **V Variable** option to delete the amount after posting.

The **Recurring Frequency** field is also important and must be set. It's a date formula field that determines how often the entry on the journal line is posted. Learn more in [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

The **Expiration Date** field determines the date when the line will be posted for the last time. The line won't be posted after that date. The advantage of using the **Expiration Date** field is that the line isn't immediately deleted from the journal. You can enter a later date so that you can use the line in the future. If the field is blank, the line will be posted every time, until it's deleted from the journal.

## See also

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability Setup](finance-sustainability-setup.md)  
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
