---
title: Row definitions in Financial Reporting
description: Describes how row definitions in financial reporting work.
author: kennieNP
ms.author: kepontop
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 03/27/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---

# Row definitions in Financial Reporting

Row definitions in financial reports provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. You can also calculate intermediate steps that aren't shown in the final report.

## Create or edit a row definition

To create or edit a row definition, do as follows

1. On the **Financial Reports** page, select the relevant financial report, and then choose the **Edit Row Definition** action.
1. Choose the **Insert G/L Accounts**, **Insert CF Accounts**, and **Insert Cost Types** actions to create a row for each financial element you want to analyze. For example, you might have one row for current assets and another row for fixed assets. For inspiration, explore the financial reports in the CRONUS demonstration company.

    > [!NOTE]
    > The **Row No.** field shows the first 10 characters of an identifier, such as an account number. If you add elements with identifiers that start with the same 10 characters, you'll have duplicates in the **Row No.** field. If needed, you can manually edit the identifiers after you insert the elements. The full identifiers are displayed in the **Totaling** field.

> [!NOTE]
> The columns you define on each line in the row definition represent columns three and up on the **Financial Report** page. The first two columns, **Row No.** and **Description**, are fixed.  


## Built-in row definitions

Starting with the 2024 release wave 1 (version 24.1), [!INCLUDE[prod_short](includes/prod_short.md)] ships with sample row definitions that helps you quickly get started setting up finance reports that suits your needs.

| Row definition code | Description | How to use this row definition | 
| ------------------- | ----------- | ------------------------------ | 
| TBA 1 | TBA 1 | TBA 1 |
| TBA 2 | TBA 2 | TBA 2 |
| TBA 3 | TBA 3 | TBA 3 |
| TBA 4 | TBA 4 | TBA 4 |


> [!NOTE]
> The sample finance reports in [!INCLUDE[prod_short](includes/prod_short.md)] aren't ready to use out-of-the box. Depending of the way you set up your G/L accounts, dimensions, G/L account categories, and budgets, you need to adjust the sample row and column definitions and the finance reports they're used in to match your setup.


## Use G/L account categories to change the layout of your financial statements

You can use G/L account categories to change the layout of your financial statements. For example, after you set up your account categories on the **G/L Account Categories** page, you can choose the **Generate Financial Reports** action and update the underlying financial reports for the core financial reports. The next time you run one of these reports, such as the **Balance Statement** report, new totals and subentries are added.

Another benefit of using G/L account categories over the raw G/L accounts in your row definitions is that a change in your chart of accounts structure doesn't affect your financial reports.

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node, are fixed and you can't add your own. However, you can delete and add account categories at lower levels and define how the related financial report appears in reports.
>
> You should create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes. Learn more at [Mapping general ledger accounts to account categories](finance-general-ledger.md#account-categories).


## Importing or exporting financial reporting row definitions

You can import and export financial row definitions as RapidStart configuration packages, which are useful for sharing the information with other companies, for example. The package is created in a .rapidstart file, which compresses the contents.

> [!NOTE]
> When you import financial reporting row definitions, existing records with the same names as those you are importing will be replaced with the new definitions. Note that the configuration package for a report definition will not overwrite any existing row or column definitions that are used in the report definition.

To import or export financial report row definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Row Definitions**, then choose the related link.
1. Choose the row definition, then choose the **Import Row Definition** or **Export Row Definition** action, depending on what you want to do.

## See also

[Column definitions in financial reporting](bi-column-definitions.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
