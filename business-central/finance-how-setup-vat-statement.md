---
title: Set Up VAT Statement Templates and Names
description: Set up VAT statement templates and names in Business Central, define how rows calculate VAT, and preview the statement for a reporting period.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT, posting, tax, value-added tax
ms.search.form: 315, 317, 318, 320, 474
ms.date: 11/11/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up VAT statement templates and names

Tax authorities can, and do, change their requirements for posting VAT. VAT statement templates and VAT statement names can help you prepare for upcoming changes and make a smooth transition to the new requirements. You can use VAT statement templates to set up different reports when choosing to print the statement. Each VAT statement template can have multiple VAT statement names, which in turn define the calculations, and you can create a new VAT statement name when requirements change. For example, one name might calculate VAT for this year based on the current requirements, and another might calculate VAT based on requirements for next year. Names are also a way to keep a history of VAT statement formats, for example, so that you can look back to see how you calculated VAT in previous years.

## To define a VAT statement

VAT statements let you calculate your VAT settlement amount for a certain period, for example, a quarter.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Statements**, and then choose the related link.  
1. Choose the **Name** field, and then choose **New** on the **VAT Statement Names** page.
1. Enter a name and description, and then select **OK** to return to the statement.
1. Fill in the statement rows. Usually, you need a row for each combination of **VAT Bus. Posting Group** and **VAT Prod. Posting Group**. For **Row No.**, use the equivalent numbers or codes from your official VAT statement. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> You can filter the information that the statement will include, depending on what you choose in the **Type** field. **Account Totaling** is useful when you want the VAT from a specific account.
> **VAT Entry Totaling** totals VAT entries that match the **Gen. Posting Type**, **VAT Bus. Posting Group**, and **VAT Prod. Posting Group** fields. **Row Totaling** totals the rows that match the filter in the **Row Totaling** field. Learn more in [Searching, filtering, and sorting data](ui-enter-criteria-filters.md). **Description** is often used to add a note to the statement. For example, you could use it as a heading when you've used row totaling.

## To preview the VAT statement

After you define a VAT statement, you can preview it to make sure it meets your needs.
> [!TIP]
> We recommend having one section in the VAT statement with **Type** set to **VAT Entry Totaling** and another section below with **Type** set to **Account Totaling**. Use these sections to reconcile the VAT entries with the G/L entries. You can also use the **G/L - VAT Reconciliation** report for this purpose.

1. Choose **Preview**.
1. In the **Date Filter** field, enter a filter to limit the statement to a specific period. Learn more in [Searching, filtering, and sorting data](ui-enter-criteria-filters.md).
1. Select the options for the VAT entries and periods to include. These options apply to **VAT Entry Totaling** rows, not **Account Totaling** rows.
1. On the lines where **Type** is **VAT Entry Totaling**, choose the amount in **Column Amount** to see the VAT entries.
1. To include unrealized VAT, set **Amount Type** on the statement row to **Unrealized Amount** or **Unrealized Base**.

## Related information

[Set Up Value-Added Tax](finance-setup-vat.md)    
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)    
[Report VAT to a Tax Authority](finance-how-report-vat.md)    
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)    
[Local functionality in Business Central](about-localization.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
