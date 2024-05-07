---
title: How to record sustainability entries
description: Learn how to record GHG (greenhouse gas) emissions.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, journal
ms.search.form: 6216, 6219, 6220
ms.date: 05/02/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# How to record sustainability entries  

In this moment, the only way for recording GHG emissions to the **Sustainability Ledger** is using the **Sustainability Journals**.   

## Sustainability journal  

**Sustainability Journals** are designed to track and record sustainability-related activities using the same user experience as other journals in Business Central. Within the journal, users have the option to input emissions manually if they possess the necessary information. Alternatively, if they lack this data, they can utilize built-in formulas to accurately calculate emissions based on specific known parameters corresponding to various types of sources and accounts. 

The information that you enter in a journal is temporary and can be changed while it's in the journal. When you post the journal, the information is transferred to **Sustainability Ledger Entries** on individual **Sustainability Accounts**, where it can't be changed. You can, however, post reversing or correcting entries.  

### Use journal templates and batches 

There are two **Sustainability Journal Templates** by default, the standard and recurring one. For each journal template, you can set up your own personal journal as a journal batch. To do so, you need to choose the **Batches** action on the **Sustainability Journal Templates** page and create the new **Sustainability Journal Batch** on the new page. For example, you can define your own journal batch for each emission scope, using the **Emission Scope** option where you can choose between three existing scopes. You can also add or change the **Source Code** and **Reason Code** for each of the batches. 

>[!TIP]
>You can have one journal batch for each of emission types, if you have many lines as it can reduce the chance for making mistakes, but you can also use the common batch for all types of emissions.   

### Validating sustainability journals 

You can turn on a background check on the **Sustainability Setup** page that will help prevent delays when posting. The check will notify you when there's a mistake while working in the **Sustainability Journal**, and this will prevent you from posting the journal.  

When you enable the validation, the **Journal Check** FactBox will show issues in the current line, and in the whole batch. Validation happens when you load a journal batch, and when you choose another journal line. The **Issues Total** tile in the FactBox shows the total number of issues that [!INCLUDE [prod_short](includes/prod_short.md)] found, and you can choose it to open an overview of the issues. 

### Work with sustainability journals 

To start working with the **Sustainability Journals**, follow the steps:   

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link. 
2. On the **Sustainability Journal** page, you can enter as many lines as you plan to post with the same batch.  
3. As a **Document Type**, you can keep empty option, or choose to use **Invoice** or **Credit Memo**.  
4. In the **Account No.** field, you can choose only **Sustainability Accounts** with selected **Direct Posting** field, **Posting** as the **Accounting Type** and non-blocked account. Also, Accounts must have configured with category and subcategory.  

>[!NOTE]
>If you use the batch where the emission scope is configured, the **Emission Scope** in the **Sustainability Account** must be equal to the **Emission Scope** in the used batch.  

5. You have two options: either manually post the amounts or use formulas.   

    1. If you have accurate information about the emission, you want to post it (i.e., you have it on the received invoice), you need to select the **Manual Input** field to specify that the amounts will be input manually. In this case, you can't populate your data in the **Fuel/Electricity**, **Distance**, **Custom Amount**, **Installation Multiplier**, and **Time Factor** fields, as they'll be non-editable for this choice. But the **Emission CO2**, **Emission CH4**, and **Emission N2O** fields will be editable, and you can fill in your data directly there. 
    2. If you don't know your emission accurately, you need to calculate it, and you need to haven't selected the **Manual Input** field, and in this case the **Emission CO2**, **Emission CH4**, and **Emission N2O** fields will be non-editable, but you can enter your calculation details based on the formula you're using. You can find more about the used formulas and defined in the **Sustainability Account Category** here in the [Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md#account-categories).
  	
7. To post the journal, choose the **Post** action. When posting in a **Sustainability Journal**, entries are generated on the **Sustainability Ledger**. 

In the case your formula is based on the **Calculate from General Ledger** option in the **Sustainability Account Category**, you must use the **Collect Amount from G/L Entries** action before posting the journal to calculate emissions based on this data source. Also, if you'd made some changes in the emission factors after populating the journal lines, you must choose the **Recalculate** action to get the proper amount in the journal.  

### Recurring journals 

A recurring journal is a **Sustainability Journal** with specific fields for managing transactions that you often post with few, or if any, changes. For example, sustainability transactions such as electricity, heat, or other similar transactions. Using recurring journals, lets you post fixed and variable amounts. With a recurring journal, you create entries that will be posted regularly only one time. For example, the accounts, dimensions, dimension values, and so on, stay in the journal after posting. If changes are needed, you can make them each time you post. 

The **Recurring Method** field is important. It determines how to treat the amount on the journal line after posting. For example, if you use the same amount every time you post the line, you can let the amount remain, and in this case, you should use the **F Fixed** as an option. If you use the same accounts and text on the line, but the amount will vary every time you post, you can choose to delete the amount after posting, and in this case, you'll choose the **V Variable** option. 

You also need to configure the **Recurring Frequency** field, as this date formula field determines how often to post the entry on the journal line, and it must be filled in. Learn more at [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).  

The **Expiration Date** field determines the date on which the line will be posted for the last time. The line won't be posted after this date. The advantage of using the **Expiration Date** field is that the line won't be deleted from the journal immediately. You can enter a later date so that you can use the line in the future. If the field is blank, the line will be posted every time until it's deleted from the journal.  

## See also  
[Finance](finance.md)    
[Sustainability management overview](finance-manage-sustainability.md)   
[Sustainability Setup](finance-sustainability-setup.md)   
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)   
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
