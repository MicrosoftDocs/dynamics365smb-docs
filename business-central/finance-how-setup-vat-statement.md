---
title: Set Up a VAT Statement | Microsoft Docs
description: Set Up a VAT Statement
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.date: 04/01/2020
ms.author: bholtorf

---
# Set Up a VAT Statement

## Setting up VAT Statement Templates and VAT Statement Names
Tax authorities can, and do, change their requirements for posting VAT. VAT Statement templates and VAT statement names can help you prepare for upcoming changes and make a smooth transition to the new requirements. You can use VAT statement templates to setup different Reports when choosing to print the statement. Each VAT Statement Template can have multiple Vat Statement names which in turn define the calculations, and you can create a new VAT statement Name when requirements change. For example, one name might calculate VAT for this year based on the current requirements, and another might calculate VAT based on requirements for next year. Names are also a way to keep a history of VAT statement formats, for example, so that you can look back to see how you calculated VAT in previous years.

## To define a VAT statements
VAT statements let you calculate your VAT settlement amount for a certain period, for example, a quarter.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statements**, and then choose the related link.  
2. Choose the **Name** field, and then choose **New** on the **VAT Statement Names** page.
3. Fill in the required fields. Usually you want to have a setting for each VAT Bus. Posting Group / VAT Prod. Posting Group combination. For Row numbers it does make sense to use equvalent numbers or codes as in your official VAT Statement [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] 


> [!Tip]
> You can filter the information that the statement will include, depending on what you choose in the **Type** field. **Account Totaling** is useful when you want the VAT from a specific account.
**VAT Entry Totaling** gets VAT from the accounts assigned to the selections in the **Gen. Posting Type**, **VAT Bus. Posting Group**, and/or the **VAT Prod. Posting Group** fields. **Row Totaling** lets you enter a value or quick filter criteria in the **Row Totaling** field. For more information, see [Searching, filtering, and Sorting Data](ui-enter-criteria-filters.md). **Description** is often used to add a note to the statement. For example, you could use it as a heading when you've used row totaling.

## To preview the VAT statement
After you define a VAT statement, you can preview it to make sure it meets your needs.
> [!Tip]
> It is best practice to have one section in the VAT Statement using **Type** **Vat Entry Totaling** and another section below using **Type** **Account Totaling** to reconcile the amounts based on the **VAT Entry** table compared to the amount on the **G/L Accounts**. You can also use the **G/L - VAT Reconciliation** Report for this purpose.

1. Choose **Preview**.
2. Enter a date filter to limit the statement to a specific period. For more information about how to customize the page to show the date filter, see [Searching, filtering, and Sorting Data](ui-enter-criteria-filters.md).
3. You can select various options to specify the type of VAT entries to include in the statement.
4. On the lines where the **Type** field contains **VAT Entry Totaling** you can see a list of VAT entries by choosing the amount in the **Column Amount** field.
5. You can use personalization to show more fields in the lines. For example the Unrealized Base Amount and Unrealized VAT Amount, if you are using unrealized VAT.

## See Also  
[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)      
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)
