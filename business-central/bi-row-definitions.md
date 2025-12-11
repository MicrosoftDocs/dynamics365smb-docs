---
title: Row definitions in Financial Reporting
description: Describes how row definitions in financial reporting work.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/10/2025
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 103_Primary, 104_Primary, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766
ms.service: dynamics-365-business-central
---

# Row definitions in Financial Reporting

Row definitions in financial reports provide a place for calculations that can't be made directly in the chart of accounts. For example, you can create subtotals for groups of accounts and then include that total in other totals. You can also calculate intermediate steps that aren't shown in the final report.

## Create a new row definition

To create a new row definition, follow these steps:

1. On the **(Financial Report) Row Definitions** page, choose the **New** action.
1. Enter a unique name for the definition.
1. In the **Description/* field, enter a descriptive name for the definition. This description provides context when you use the definition, but doesn't show on the report.
1. Enter an internal description for the definition.

## Edit the content of a row definition

To edit the content of a row definition, follow these steps:

1. On the **(Financial Report) Row Definitions** page, select the relevant definition, and then choose the **Edit Row Definition** action.
1. Choose the **Insert G/L Accounts**, **Insert CF Accounts**, and **Insert Cost Types** actions to create a row for each financial element you want to analyze. For example, you might have one row for current assets and another row for fixed assets. For inspiration, explore the financial reports in the CRONUS demonstration company.

    > [!NOTE]
    > The **Row No.** field can hold up to 10 characters and denote a row identifier, such as an account number or just a string like "Revenue" or "R". You use these identifiers for calculated rows in the **Totalling** field. The **Row No.** values do not need to be unique within the row definition.
    >
    > If needed, you can manually edit the identifiers after you insert the elements, either directly on the page or in Excel.

   > [!NOTE]
   > The columns you define in a column definition represent columns three and up on the **Financial Report** page. The first two columns, **Row No.** and **Description**, are fixed.  

1. To format the rows, choose the **Bold**, **Italic**, **Underline**, and **Double Underline** checkboxes. To learn more about formatting, go to [Format your financial reporting](#format-rows-in-your-financial-reports).

## Working with row formulas

A powerful feature in Financial Reporting is that you can use values computed in previous rows in row formulas defined in subsequent rows. Set the **Totaling Type** to **Formula**, and then write your calculation in the **Totalling** field on the same row.

The following excerpt of a row definition illustrates how row formulas work. Your chart of accounts structure might differ from the accounts shown.

| Row No. | Description | Totaling Type | Totaling | ... | Show |
| ------- | ------|-------- | -------- | --- | ---- |
|         | ## Revenue calculation start | Formula      |                              | | No   |
| R      | Product Revenue | Posting Accounts      | 40000..40209                 | | Yes |
| R      | Discounts and Returns | Posting Accounts | 40910..40919 \| 40940..49999 | | Yes |
| F1      | Total Revenue    | Formula               | R                            | | Yes |
|         | ## Revenue calculation end   | Formula      |                              | | No   |
| L       | Total liabilities  | Account Category     | Liabilities                  | | Yes |
|         | Revenue to liabilities | Formula      | F1 / L                          | | Yes |

The example illustrates some different tips and tricks:

* You can use a formula row as a code comment. Remember to set the **Show** option to **No**.
* The formula in row F1 summarizes all numbers from rows with **R** in the **Row No.** field (the Row No. setting doesn't have to be unique).
* You can use results from previous calculations in new row formulas.

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

## Format rows in your financial reports

On the **Row Definition** page, you can format the rows in a row definition to provide visual cues that make it easier to find key information quickly. For example, lines that calculate totals often use bold font.

The following table describes the different formatting options on a row:

| Formatting property | How the row is displayed | On-screen | PDF/Print |
| ------------------- | ------------------------ | --------- | --------- |
| Bold                | The row header is formatted in bold. | Yes | Yes |
| Italic              | The row header is formatted in italics. | No | Yes |
| Underline           | The columns in the report are formatted with an underline. Typically used rows that display a subtotal. | No | Yes |
| Double Underline    | The columns in the report are formatted with a double underline. Typically used for rows that display a total. | No | Yes |
| New Page            | If you want to make a report with different sections separated by page breaks in the report output (for PDF or print), use this property on a row. This setting inserts a page break after the row.  | No | Yes |
| Show Opposite Sign  | The data in columns is formatted with the opposite sign from how they're calculated. Typically used to show debits in reports as negative amounts with a minus sign and credits as positive amounts. | Yes | Yes |

> [!NOTE]
> Some of the formatting options don't carry over to reports when you use the Export to Excel action. If you often export reports to Excel, you might just use the tools that Excel provides rather than row definitions.

## Adding empty lines in your financial reports

If you want to add an empty line to a financial report, you can add a row and set the **Totalling Type** field.

The following table describes the different formatting options for a row that define an empty line:

| Value of the Totalling Type property | How the row is displayed | On-screen | PDF/Print |
| -------------------------------- | ------------------------ | --------- | --------- |
| Formula (with empty Totalling value)     | The row is empty. | Yes | Yes |
| Underline           | The columns on the row are empty and are formatted with an underline. Typically used for rows that display a section. | No | Yes |
| Double Underline    | The columns on the row are empty and are formatted with a double underline. Typically used for rows that display the final part of a section. | No | Yes |

## Conditionally display rows in your financial reports

On the **Row Definition** page, the **Show** setting on rows defines whether they show in the report output for PDF or print.

The following table describes the different display options on a row:

| Value of the Show setting | Whether the row displays |
| ------------------------------ | ------------------------ |
| Yes | Row always shows. |
| No | Row never shows. Use this setting for rows that are only used in calculation steps. |
| If any column not zero | If any column in the report has a nonzero value, the row shows. Otherwise, it doesn't show. |
| When positive balance | If column data in the report has positive values, the row shows. Otherwise, it doesn't show. |
| When negative balance | If column data in the report has negative values, the row shows. Otherwise, it doesn't show. |

## Use G/L account categories to change the layout of your financial statements

You can use G/L account categories to change the layout of your financial statements. For example, after you set up your account categories on the **G/L Account Categories** page, you can choose the **Generate Financial Reports** action and update the underlying financial reports for the core financial reports. The next time you run one of these reports, such as the **Balance Statement** report, new totals, and subentries are added.

Another benefit of using G/L account categories over the G/L accounts in your row definitions is that a change in your chart of accounts structure doesn't affect your financial reports.

The following excerpt of a row definition illustrates how you can use account categories. Your chart of accounts structure and use of account categories might differ from the example.

| Row No. | Description                | Totaling Type    | Totaling    | ... | Show |
| ------- | -------------------------- | ---------------- | ----------- | --- | ---- |
|         | // Worlds smallest balance sheet | Formula          |             |     | No   |
| A       | Total assets                     | Account Category | Assets      |     | Yes  |
| L       | Total liabilities                | Account Category | Liabilities |     | Yes  |
|         |                                  | Underline        |             |     | Yes  |
|         | Balance                          | Formula          | A+L         |     | Yes  |
|         |                                  | Double underline |             |     | Yes  |

> [!NOTE]
> The top-level account categories, such as the **Liabilities** node, are fixed, and you can't add your own. However, you can delete and add account categories at lower levels and define how the related financial report displays.
>
> You should create and structure your own lower-level G/L account categories from scratch, in a hierarchy if needed, rather than try to rearrange the existing ones. For example, you can restructure the **Liabilities** node to contain a new **Equity** node followed by the **Current Liabilities** and **Long Term Liabilities** nodes. Learn more at [Mapping general ledger accounts to account categories](finance-general-ledger.md#account-categories).

## Find the reports that use a row definition

[!INCLUDE[introduced-in-2025rw1](includes/introduced_in_2025rw1.md)]

Before you change a row definition, it can be helpful to know which reports use it so that you understand the effect of your change. To find out which reports use a row definition, follow these steps:

1. On the **(Financial Report) Row Definitions** page, select the definition, and then choose the **Edit Row Definition** action.
1. To open a list of reports that use the definition, choose the **Where-Used** action.

## Import or export financial reporting row definitions

You can import and export financial row definitions as RapidStart configuration packages. For example, configuration packages are useful for sharing information with other companies. The package is created in a RAPIDSTART file that compresses the contents.

> [!NOTE]
> When you import row definitions, the records replace existing records with the same names. It doesn't overwrite existing row or column definitions that the report definition uses.

To import or export financial report row definitions, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Row Definitions**, then choose the related link.
1. Choose the row definition, then choose the **Import Row Definition** or **Export Row Definition** action, depending on what you want to do.

## Edit a financial reporting row definition in Excel

[!INCLUDE[introduced-in-2025rw2](includes/introduced-in-2025rw2.md)]

If you want to edit all the lines in a row definition, with the Edit in Excel action, you can make all the changes in Excel and then publish the changes back to [!INCLUDE[prod_short](includes/prod_short.md)]. 

To learn more, go to [Edit in Excel](across-work-with-excel.md#edit-in-excel).

## Best practices for working with row definitions

Row definitions aren't versioned. When you change a row definition, the old version is replaced when your change saves to the database. The following list contains some best practices for working with row definitions:

* If you add row definitions, choose a good code and fill in the description field with a meaningful text while you still know what you use the row definition for. This information helps your coworkers (and your future self) to work with financial reporting and perhaps changing the row definition.
* Use the **Where-Used** action to learn where a row definition is used before you make any changes to it.
* Before you change a row definition, consider taking a copy of it as a backup, just in case your change doesn't work as expected. You can either just copy the definition (give it a good name), or export it. To learn more, go to [Import or export row definitions](#import-or-export-financial-reporting-row-definitions).
* If you need a fresh copy of a definition that [!INCLUDE[prod_short](includes/prod_short.md)] provides, an easy way to get one is to create a new company that only contains setup data. Then, export the definition and import it in the company where the definition needs a refresh.


## Related information
<!-- 
2025w1: add link to administrator article for Financial Report Lifecycle telemetry 
-->

[Column definitions in financial reporting](bi-column-definitions.md)  
[Prepare financial reporting](bi-how-work-account-schedule.md)  
[Financial analytics overview](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
