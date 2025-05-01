---
title: Record sustainability entries
description: Learn how to record greenhouse gas (GHG) emissions.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, water, waste, intensity, CSRD, journal
ms.search.form: 6216, 6219, 6220
ms.date: 01/29/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Record sustainability entries

You can manually record greenhouse gas (GHG) emissions or water and waste intensity in the sustainability ledger by using sustainability journals. You can also use purchase documents or general journals to record GHG emissions.  

<!--> [!NOTE]
> Posting water and waste intensity and using general journals for posting emissions will be enabled starting *2025 release wave 1*.  -->

## Sustainability journals

Sustainability journals are designed to track and record sustainability-related activities by using the same user experience as other journals in [!INCLUDE [prod_short](includes/prod_short.md)]. You can manually enter emissions and water or waste intensity in a journal. Alternatively, if you don't have the information, you can use built-in formulas to accurately calculate emissions or water or waste intensity based on parameters that correspond to various types of sources and accounts.

The information that you enter in a journal is temporary and you can change it while it's in that journal. When you post the journal, the information is transferred to sustainability ledger entries on individual sustainability accounts, where it can't be changed. However, you can post reversing or correcting entries.

### Use journal templates and batches

By default, there are standard and recurring sustainability journal templates.

For each journal template, you can set up your own personal journal as a journal batch. To do so, select the **Batches** action on the **Sustainability Journal Templates** page, and then create the new **Sustainability Journal Batch** on the new page. For example, you can define your own journal batch for each emission scope by using the **Emission Scope** option and then selecting among the four existing scopes or **Water/Waste** option. For each batch, you can add or change the **Source Code** and **Reason Code** values.

> [!TIP]
> If you have many lines, you can help reduce the risk of mistakes by having one journal batch for each emission type. Alternatively, you can use the common batch for all emission types.

### Validate sustainability journals

On the **Sustainability Setup** page, you can turn on a background check to help prevent posting delays. If any mistakes occur while you work in the sustainability journal, the validation notifies you and prevents you from posting the journal.

When you enable the validation, the **Journal Check** FactBox shows issues on the current line and in the whole batch. Validation occurs when you load a journal batch and when you select another journal line. The **Issues Total** tile in the FactBox shows the total number of issues that [!INCLUDE [prod_short](includes/prod_short.md)] found. You can select the tile to open an overview of the issues.

### Work with sustainability journals

To work with sustainability journals, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Journal**, and then select the related link.
2. On the **Sustainability Journal** page, enter as many lines as you plan to post in the same batch.
3. For internal documents, you can leave the **Document Type** field blank. If not, you can select **Invoice**, **Credit Memo**, or **GHG Credit**.  
4. In the **Account No.** field, you can select only nonblocked sustainability accounts where the **Direct Posting** field is selected and the **Accounting Type** field is set to **Posting**. The accounts must also be configured with a category and a subcategory.

    > [!NOTE]
    > If you use a batch where the emission scope is configured, the **Emission Scope** value in the sustainability account must equal the **Emission Scope** value in the batch.

5. You can either manually fill in the emission amounts or use formulas.

    - If you have accurate information about gas emission or water or waste intensity and want to post it (that is, if you have the information on the received invoice, or some other measured model), select the **Manual Input** field to indicate that you manually enter the amounts. In this case, you can't enter your data directly in the **Fuel/Electricity**, **Distance**, **Custom Amount**, **Installation Multiplier**, and **Time Factor** fields because they become uneditable. However, the **Emission CO2**, **Emission CH4**, **Emission N2O**, **Water Intensity**, **Discharged Into Water**, and **Waste Intensity** fields remain editable, and you can enter your data directly in them.
    - If you don't have accurate knowledge of the gas emission or water or waste intensity and must calculate it, don't select the **Manual Input** field. In this case, the **Emission CO2**, **Emission CH4**, **Emission N2O**, **Water Intensity**, **Discharged Into Water**, and **Waste Intensity** fields become uneditable. However, you can enter your calculation details based on the formula that you're using. To learn more about the formulas that are defined in the **sustainability account category**, go to [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md#account-categories).  

6. To post the journal, select the **Post** action. When you post in a sustainability journal, entries are generated in the sustainability ledger.

> [!NOTE]
> For water and waste intensity calculation, you can only use a formula with the **Custom Amount** that's multiplied with the emission factor from the **Sustainability Account Subcategory**.  

> [!IMPORTANT]
> If your formula is based on the **Calculate from General Ledger** option in the sustainability account category, you must use the **Collect Amount from G/L Entries** action before you post the journal. The action calculates emissions based on this data source. Additionally, if you made changes to the emission factors after the journal lines were filled in, you must select the **Recalculate** action to get the correct amount in the journal.

### Changing account subcategories in the journal line  

You can have more than one **Account Subcategory** related to one **Sustainability Account**, but only one can be set as the default value. You must set the default value for the account every time if you want to use it for posting. To use a different subcategory for each account, you can easily change this value on the **Sustainability Journal** line, but you can only select subcategories that are already associated with the specific account and account category.

> [!TIP]
> Here's an example. You want to use one account for different types of cars, but the cars have different emission factors. You can set up one account and create an account subcategory for each emission factor. When you work in your sustainability journal, you can easily change your account subcategory based on the car type you choose to use for recording emissions.

### Recurring journals

A recurring journal is a sustainability journal that has specific fields for managing transactions that you often post with few, if any, changes. Examples include sustainability transactions such as electricity or heat, or other similar transactions. You can use recurring journals to post fixed and variable amounts.

When you use a recurring journal, you create the entries that you regularly post only one time. Information such as the accounts, dimensions, and dimension values remain in the journal after posting. Each time that you post, you can make any changes that are needed.

The **Recurring Method** field is important. It determines how the amount on the journal line is handled after posting. For example, if you use the same amount every time that you post the line, you can select the **F Fixed** option to let the amount remain after posting. If you use the same accounts and text on the line, but the amount varies every time that you post, you can select the **V Variable** option to delete the amount after posting.

The **Recurring Frequency** field is also important and must be set. It's a date formula field that determines how often the entry on the journal line is posted. Learn more in [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

The **Expiration Date** field determines the date when the line is posted for the last time. The line won't be posted after that date. The advantage of using the **Expiration Date** field is that the line isn't immediately deleted from the journal. You can enter a later date so that you can use the line in the future. If the field is blank, the line is posted every time, until you delete it from the journal.

## Purchase documents  

To enable recording of greenhouse gas (GHG) emissions in any purchase-related documents, you must select the **Use Emissions in Purchase Documents** on the **Sustainability Setup** page. 

To work with any purchase-related documents, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon and:  
   - Enter **Purchase Invoices** if you want the invoice as a **Document Type**, and then select the related link.  
   - Enter **Purchase Orders** if you want the order as a **Document Type**, and then select the related link.  
2. Populate the header and lines based on the instructions in [how to work with purchase invoices and orders](purchasing-how-record-purchases.md).
3. If you have information about emissions on your invoice from the vendor, choose the appropriate **Sustainability Account No.** in the document lines and add emission values using one of the following fields (based on what you want to track and emissions you have on your physical invoice): **Emission CO2**, **Emission CH4**, or **Emission N2O**.

    > [!NOTE]
    > The values you enter in the emission fields are fixed amounts per line. They aren't multiplied with the **Quantity** field. You can use **Sustainability Account No.** only when the **Type** field (**Option Values**) is **Item** or **G/L Account**. You can't use **Resource** or **Charge (Item)** **Option Values**. 

4. If you want to review total emissions before posting, you can open the statistics page and find the total posted emissions and emissions for posting per document (any purchase-related documents) on the **Sustainability** FastTab.
5. Post the documents and open a new **Posted Purchase Invoice**.
6. Select the **Find Entries** action. You have a **Sustainability Ledger Entry** as one of the related entries on the **Find entries** page.

> [!NOTE]
> When you post the document, for each of the purchase lines where you have **Sustainability Account No.**, [!INCLUDE [prod_short](includes/prod_short.md)] creates an independent **Sustainability Ledger Entry** with the **Invoice** as a **Document Type** and the same **Document No.**.

> [!NOTE]
> You can also create and post a **Purchase Credit Memo** manually, or by using the **Cancel**, **Correct**, or **Create Corrective Credit Memo** actions, in which case [!INCLUDE [prod_short](includes/prod_short.md)] copies the existing values from the posted invoice.  

## General journals

You can use general journals to post gas emissions together with the financial amounts. This option is used if you want to post your incoming invoices using journals and not documents. In this situation, you can [use general journals](ui-work-general-journals.md) as usual, but before posting journals, you should add emissions. There isn't an option to use formulas in general journals. After you select the right **Sustainability Account No.** for the journal line, you can add only total emission amounts in the **Total Emission CO2**, **Total Emission CH4**, or **Total Emission N2O** fields. After you post, lines are recorded in the **Sustainability Ledger Entries** and if you included a carbon equivalent calculation, [!INCLUDE [prod_short](includes/prod_short.md)] calculates it.

> [!NOTE]
> You can select the **Sustainability Account No.** in the journal line only if **Document Type** for this line is **Invoice** or **Credit Memo**. For all other options, you can't select the **Sustainability Account No.** and post emissions.  

## Related information

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability Setup](finance-sustainability-setup.md)  
[Chart of Sustainability Accounts and Ledger](finance-sustainability-accounts-ledger.md)  
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)  
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)  
[How to work with general journals](ui-work-general-journals.md)  
[How to work with purchase invoices and orders](purchasing-how-record-purchases.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
