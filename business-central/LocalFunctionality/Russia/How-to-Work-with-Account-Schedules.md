---
title: Working with account schedules in Russia
description: Russian enhancements include additional functionality around account schedules.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Work with Account Schedules

Use account schedules to get insight into the financial data stored in your chart of accounts. Account schedules analyze figures in G/L accounts, and compare general ledger entries with general ledger budget entries. The results display in charts on your Home page, such as the Cash Flow chart. 

[!INCLUDE[prodshort](../../includes/prodshort.md)] provides a few sample account schedules that you can use right away, or you can set up your own rows and columns to specify the figures to compare. For example, you can create account schedules to calculate profit margins on dimensions like departments or customer groups. You can create as many customized financial statements as you want.

Setting up account schedules requires an understanding of the financial data in the chart of accounts. For example, you can view general ledger entries as percentages of budget entries. This requires that budgets are created. For more information, see [Create Budgets](../../finance-how-create-budgets.md).

## Account Categories and Account Schedules

You can use account categories to change the layout of your financial statements. After you set up your account categories in the **G/L Account Categories** window, and you choose the **Generate Account Schedules** action, the underlying account schedules for the core financial reports are updated. The next time you run one of these reports, such as the balance statement, new totals and subentries are added, based on your changes. 

## To create new account schedules

You use account schedules to analyze figures in general ledger accounts or to compare general ledger entries with general ledger budget entries. For example, you can view the general ledger entries as percentages of the budget entries. 

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Schedules**, and then choose the related link.

2. In the **Account Schedule Names** window, choose the **New** action to create a new account schedule name.

3. Fill in the fields as necessary. Choose a field to read a short description of the field or link to more information.

4. Choose the **Edit Account Schedule** action.

5. In the **Account Schedule** window, fill in the fields as necessary.

   When you have created a new account schedule and set up the rows, you must set up columns. You can either set them up manually or assign a predefined column layout to your account schedule.

6. Choose the **Edit Column Layout Setup** action.

7. In the **Column Layout** window, fill in the fields as necessary.

> [!NOTE]
> If you did not assign a default column layout to the account schedule, you must set the columns up manually.

### To create a column that calculates percentages

Sometimes you may want to include a column in an account schedule to calculate percentages of a total. For example, if you have a number of rows that break down sales by dimension, you may want a column to indicate the percentage of total sales that each row represents. 

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Schedules**, and then choose the related link.
2. In the **Account Schedule Names** window, select an account schedule.
3. Choose the **Edit Account Schedule** action to set up an account schedule row to calculate the total on which the percentages will be based.
4. Insert a line immediately above the first row for which you want to display a percentage.
5. Fill in the fields on the line as follows: In the **Totaling Type** field, enter **Set Base for Percent**. In the **Totaling** field, enter a formula for the total that the percentage will be based on. For example, if row 11 contains the total sales, enter **11**.
6. Choose the **Edit Column Layout Setup** action to set up a column.
7. Fill in the fields on the line as follows: In the **Column Type** field, select **Formula**. In the **Formula** field, enter a formula for the amount that you want to calculate a percentage for, followed by %. For example, if column number N contains the net change, enter **N%**.
8. Repeat steps 4 through 7 for each group of rows that you want to break down by percentage.

## To set up account schedules with overviews

You can use an account schedule to create a statement comparing general ledger figures and general leger budget figures. 

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Schedules**, and then choose the related link.

2. In the **Account Schedule Names** window, select an account schedule.

3. Choose the **Edit Account Schedule** action

4. In the **Account Schedule** window, in the **Name** field, select the default account schedule name.

5. Choose the **Insert Accounts** action.

6. Select the accounts that you want to include in your statement, and then choose the **OK** button.

   The accounts are now inserted into your account schedule. If you want you can also change the column layout.

7. Choose the **Overview** action.

8. On the **Dimension Filters** FastTab, set the budget filter to the desired filter name.

9. Choose the **OK** button.

Now you can copy and paste your budget statement into a spreadsheet.

## See Also

[Finance](../../finance.md)  
[Setting Up Finance](../../finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](../../finance-general-ledger.md)  
