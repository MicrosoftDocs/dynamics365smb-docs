---
title: Working with Financial Reports in Russia
description: Provides information about enhanced financial reporting features available for Russia.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: financial reports, account categories, percentage calculation, financial statement, budget statement, Russia
ms.date: 07/17/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Work with financial reports

Use financial reports to get insight into the financial data stored in your chart of accounts. Financial reports analyze figures in general ledger (G/L) accounts, and compare general ledger entries with general ledger budget entries. The results display in charts on your **Home** page, for instance the cash flow chart.

[!INCLUDE[prod_short](../../includes/prod_short.md)] provides a few sample financial reports you can use right away, or you can set up your own rows and columns to specify which figures to compare. For example, you can create financial reports to calculate profit margins on dimensions such as departments or customer groups. You can create as many customized financial statements as you want.

Setting up financial reports requires an understanding of the financial data in the chart of accounts. So, for example, you could view general ledger entries as percentages of budget entries. This requires you to have created budgets. Learn more at [Create Budgets](../../finance-how-create-budgets.md).

## Account categories and financial reports

You can use account categories to change the layout of your financial statements. After you set up your account categories on the **G/L Account Categories** page, and you choose the **Generate Financial Reports** action, the underlying financial reports for the core financial reports are updated. The next time you run one of these reports, such as the balance statement, new totals, and subentries are added, based on your changes.

## Create new financial reports

You use financial reports to analyze figures in general ledger accounts or to compare general ledger entries with general ledger budget entries. For example, you can view the general ledger entries as percentages of the budget entries.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, then choose the related link.
1. On the **Financial Report** page, choose the **New** action to create a new financial report name.
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes//tooltip-inline-tip_md.md)]
1. Choose the **Edit Financial Report** action.
1. On the **Financial Report** page, fill in the fields as necessary.

   When you have created a new financial report and set up the rows, you must set up columns. You can either set them up manually or assign a predefined column layout to your financial report.

1. Choose the **Edit Column Layout Setup** action.
1. On the **Column Layout** page, fill in the fields as necessary.

   > [!NOTE]
   > If you didn't assign a default column layout to the financial report, you must set up the columns manually.

### Create a column that calculates percentages

Sometimes you may want to include a column in a financial report to calculate percentages of a total. So, let's say you have a number of rows that break down sales by dimension, you might want a column to indicate the percentage of total sales each row represents.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select a report.
1. Choose the **Edit Financial Report** action to set up a financial report row to calculate the total on which the percentage will be based.
1. Insert a line immediately above the first row for which you want to display a percentage.
1. Fill in the fields on the line as follows: In the **Totaling Type** field, enter **Set Base for Percent**, then in the **Totaling** field, enter a formula for the total that the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.
1. Choose the **Edit Column Definition** action to set up a column.
1. Fill in the fields on the line as follows: In the **Column Type** field, select **Formula**; then in the **Formula** field, enter a formula for the amount that you want to calculate a percentage for, followed by the percent sign (%). For example, if column number N contains the net change, enter **N%**.
1. Repeat steps 4 through 7 for each group of rows you want to break down by percentage.

## Set up financial reports with overviews

You can use a financial report to create a statement comparing general ledger figures and general ledger budget figures.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Financial Reports**, and then choose the related link.
1. On the **Financial Reports** page, select a financial report.
1. Choose the **Edit Row Definition** action
1. On the **Row Definition** page, in the **Name** field, select the default financial report name.
1. Choose the **Insert Accounts** action.
1. Select the accounts you want to include in your statement, then choose **OK**.

   The accounts are now inserted into your financial report. If you want, you can also change the column layout.

1. Go back to the **Financial Reports** page and choose the **Edit Financial Report** action.
1. On the **Dimensions** FastTab, set the budget filter to the desired filter name.
1. Choose **OK**.

Now you can copy and paste your budget statement into a spreadsheet.

## Related information

- [Finance](../../finance.md)  
- [Setting Up Finance](../../finance-setup-finance.md)  
- [The General Ledger and the Chart of Accounts](../../finance-general-ledger.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
