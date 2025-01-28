---
title: Row definitions in Financial Reporting
description: Describes how row definitions in financial reporting work.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/27/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103_Primary, 104_Primary, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---

# Row definitions in Financial Reporting

Row definitions in financial reports provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. You can also calculate intermediate steps that aren't shown in the final report.

## Create or edit a row definition

To create or edit a row definition, follow these steps:

1. On the **Financial Reports** page, select the relevant financial report, and then choose the **Edit Row Definition** action.
1. Choose the **Insert G/L Accounts**, **Insert CF Accounts**, and **Insert Cost Types** actions to create a row for each financial element you want to analyze. For example, you might have one row for current assets and another row for fixed assets. For inspiration, explore the financial reports in the CRONUS demonstration company.

    > [!NOTE]
    > The **Row No.** field shows the first 10 characters of an identifier, such as an account number. Adding elements with identifiers that start with the same 10 characters creates duplicates in the **Row No.** field. If needed, you can manually edit the identifiers after you insert the elements. The full identifiers are displayed in the **Totaling** field.

   > [!NOTE]
   > The columns you define on each line in the row definition represent columns three and up on the **Financial Report** page. The first two columns, **Row No.** and **Description**, are fixed.  

1. To format the rows, choose the **Bold**, **Italic**, **Underline**, and **Double Underline** checkboxes. To learn more about formatting, go to [Format your financial reporting](#format-your-financial-reporting).

## Built-in row definitions

[!INCLUDE[prod_short](includes/prod_short.md)] provides sample row definitions that can help you quickly get started setting up finance reports that suit your needs.

<!-- update this when we release the new templates in 24.1
| Row definition code | Description | How to use this row definition | 
| ------------------- | ----------- | ------------------------------ | 
| TBA 1 | TBA 1 | TBA 1 |
| TBA 2 | TBA 2 | TBA 2 |
| TBA 3 | TBA 3 | TBA 3 |
| TBA 4 | TBA 4 | TBA 4 | 
-->

> [!NOTE]
> The sample finance reports in [!INCLUDE[prod_short](includes/prod_short.md)] aren't ready to use out of the box. Depending on how you set up your G/L accounts, dimensions, G/L account categories, and budgets, adjust the sample row and column definitions and the finance reports that use them to match your setup.

## Format your financial reporting

On the **Row Definition** page, you can format your row definitions to provide visual cues that make it easier to find key information quickly. For example, lines that calculate totals often use bold font.

> [!NOTE]
> Some of the formatting options don't carry over to reports when you use the Export to Excel action. If you often export reports to Excel, you might just use the tools that Excel provides rather than row definitions.

## Use G/L account categories to change the layout of your financial statements

You can use G/L account categories to change the layout of your financial statements. For example, after you set up your account categories on the **G/L Account Categories** page, you can choose the **Generate Financial Reports** action and update the underlying financial reports for the core financial reports. The next time you run one of these reports, such as the **Balance Statement** report, new totals, and subentries are added.

Another benefit of using G/L account categories over the raw G/L accounts in your row definitions is that a change in your chart of accounts structure doesn't affect your financial reports.

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node, are fixed, and you can't add your own. However, you can delete and add account categories at lower levels and define how the related financial report appears in reports.
>
> You should create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes. Learn more at [Mapping general ledger accounts to account categories](finance-general-ledger.md#account-categories).

## Best practices for working with row definitions

Row definitions aren't versioned. When you change a row definition, the old version is replaced when your change saves to the database. The following list contains some best practices for working with row definitions:

- If you add row definitions, choose a good code and fill in the description field with a meaningful text while you still know what you use the row definition for. This information helps your coworkers (and your future self) to work with financial reporting and perhaps changing the row definition.
- Before you change a row definition, consider taking a copy of it as a backup, just in case your change doesn't work as expected. You can either just copy the definition (give it a good name), or export it. To learn more, go to [Import or export row definitions](#import-or-export-financial-reporting-row-definitions).
- If you need a fresh copy of a definition that [!INCLUDE[prod_short](includes/prod_short.md)] provides, an easy way to get one is to create a new company that only contains setup data. Then, export the definition and import it in the company where the definition needs a refresh.

## Import or export financial reporting row definitions

You can import and export financial row definitions as RapidStart configuration packages. For example, configuration packages are useful for sharing information with other companies. The package is created in a .rapidstart file, which compresses the contents.

> [!NOTE]
> When you import row definitions, the records replace existing records with the same names. It doesn't overwrite existing row or column definitions that the report definition uses.

To import or export financial report row definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Row Definitions**, then choose the related link.
1. Choose the row definition, then choose the **Import Row Definition** or **Export Row Definition** action, depending on what you want to do.

## See also

[Column definitions in financial reporting](bi-column-definitions.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
