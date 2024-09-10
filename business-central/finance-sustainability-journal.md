---
title: Record sustainability entries
description: Learn how to record greenhouse gas (GHG) emissions.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, journal
ms.search.form: 6216, 6219, 6220
ms.date: 09/09/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Record sustainability entries

Users can manually record greenhouse gas (GHG) emissions in the sustainability ledger manually using sustainability journals or any kind of purchase-related documents.  

> [!NOTE]
> Using any kind of purchase-related documents to record greenhouse gas (GHG) emissions is available starting with the *2024 release wave 2*.  

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

To work with sustainability journals, follow the steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link.
2. On the **Sustainability Journal** page, enter as many lines as you plan to post in the same batch.
3. For internal document, you can leave the **Document Type** field blank. If not, you can select **Invoice** or **Credit Memo**.
4. In the **Account No.** field, you can select only non-blocked sustainability accounts where the **Direct Posting** field is selected and the **Accounting Type** field is set to **Posting**. The accounts must also be configured with a category and a subcategory.

    > [!NOTE]
    > If you use a batch where the emission scope is configured, the **Emission Scope** value in the sustainability account must equal the **Emission Scope** value in the batch.

5. You can either manually fill in the emission amounts or use formulas.

    - If you have accurate information about the emission and want to post it (that is, if you have the information on the received invoice), select the **Manual Input** field to indicate that you'll manually enter the amounts. In this case, you can't enter your data directly in the **Fuel/Electricity**, **Distance**, **Custom Amount**, **Installation Multiplier**, and **Time Factor** fields, because they become noneditable. However, the **Emission CO2**, **Emission CH4**, and **Emission N2O** fields remain editable, and you can enter your data directly in them.
    - If you don't have accurate knowledge of the emission and must calculate it, don't select the **Manual Input** field. In this case, the **Emission CO2**, **Emission CH4**, and **Emission N2O** fields become noneditable. However, you can enter your calculation details based on the formula that you're using. Learn more about the formulas that are and defined in the **sustainability account category** in [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md#account-categories).

6. To post the journal, select the **Post** action. When you post in a sustainability journal, entries are generated in the sustainability ledger.

If your formula is based on the **Calculate from General Ledger** option in the sustainability account category, you must use the **Collect Amount from G/L Entries** action before you post the journal, to calculate emissions based on this data source. Additionally, if you made changes to the emission factors after the journal lines were populated, you must select the **Recalculate** action to get the proper amount in the journal.

### Changing Account Subcategories in the journal line  

It's important to know that you can have more than one *Account Subcategory* related to one *Sustainability Account*, but only one can be set as the default value. You must set the default value for the account every time if you want to use it for posting. To use a different subcategory for each account, you can easily change this value on the **Sustainability Journal** line, but you can only select subcategories that are already associated with the specific account and account category.   

> [!TIP]
> For example, if you want to use one account for business cars, but you have different car types with different emission factors, you can set up one *Account* and create as many *Account Subcategories* as you need for cars with different emission factors. When you work in your *Sustanability Journal*, you can easily change your *Account Subcategory* based on the car type you choose to use for recording emissions. 

### Recurring journals

A recurring journal is a sustainability journal that has specific fields for managing transactions that you often post with few, if any, changes. Examples include sustainability transactions such as electricity or heat, or other similar transactions. You can use recurring journals to post fixed and variable amounts.

When you use a recurring journal, entries that you'll regularly post must be created only one time. Information such as the accounts, dimensions, and dimension values remain in the journal after posting. Each time that you post, you can make any changes that are needed.

The **Recurring Method** field is important. It determines how the amount on the journal line is handled after posting. For example, if you use the same amount every time that you post the line, you can select the **F Fixed** option to let the amount remain after posting. If you use the same accounts and text on the line, but the amount varies every time that you post, you can select the **V Variable** option to delete the amount after posting.

The **Recurring Frequency** field is also important and must be set. It's a date formula field that determines how often the entry on the journal line is posted. Learn more in [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

The **Expiration Date** field determines the date when the line will be posted for the last time. The line won't be posted after that date. The advantage of using the **Expiration Date** field is that the line isn't immediately deleted from the journal. You can enter a later date so that you can use the line in the future. If the field is blank, the line will be posted every time, until it's deleted from the journal.

## Purchase documents  

To enable recording of greenhouse gas (GHG) emissions in any purchase-related documents, you must select the **Use Emissions in Purchase Documents** on the **Sustainability Setup** page.  

To work with any purchase-related documents, follow the steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon and:  
   1. Enter **Purchase Invoices** if you want invoice as a **Document Type**, and then select the related link.  
   2. Enter **Purchase Orders** if you want order as a **Document Type**, and then select the related link.  
2. Populate header and lines based on the following instruction [how to work with purchase invoices and orders](purchasing-how-record-purchases.md).
3. If you have information about emission on the invoice you have from vendor, choose appropriate **Sustainability Account No.** in the document lines and add emissions values using one of the following fields (based on what you want to track and emission you have on your physical invoice): **Emission CO2**, **Emission CH4**, or **Emission N2O**.

    > [!NOTE]
    > The values you enter in the emission fields are fixed amounts per line and they will not be multiplied with the **Quantity** field. You can use **Sustainability Account No.** only when the **Type** field (**Option Values**) is **Item** or **G/L Account**. You can't use **Resource** or **Charge (Item)** **Option Values**. 

4. If you want to see total emissions before posting, you can open the statistic page and find total posted emissions and emissions for posting per document (any purchase-related documents) in the **Sustainability** FastTab.   
5. Post the documents and open new **Posted Purchase Invoice**.
6. Select **Find Entries** action and you'll see that you have **Sustainability Ledger Entry** as one of the related entries on the **Find entries** page.

> [!NOTE]
> When you post the document, for each of the purchase lines where you have **Sustanability Account No.** system will create independent **Sustainability Ledger Entry** with the **Invoice** as a **Document Type** and the same **Document No.**

> [!NOTE]
> You can also create and post **Purchase Credit Memo**. You can do it manually or using some of the following options: **Cancel**, **Correct**, or **Create Corrective Credit Memo** in which case the system will copy the existing values from the posted invoice.  

## See also

[Finance](finance.md)    
[Sustainability management overview](finance-manage-sustainability.md)    
[Sustainability Setup](finance-sustainability-setup.md)    
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)    
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
[Sustainability reports and analytics in Business Central](sustainability-reports.md)   
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
