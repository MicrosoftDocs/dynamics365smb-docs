---
title: Analyze Actual Amounts Versus Budgeted Amounts
description: This article describes how to analyze actual amounts versus budgeted amounts as a means of gathering, analyzing, and sharing your company data.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 120, 121, 422
ms.date: 09/14/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Analyze Actual Amounts Versus Budgeted Amounts

As a part of gathering, analyzing, and sharing your company data, you view actual amounts compared to budgeted amounts for all accounts and for several periods.

To analyze budgeted amounts, you must first create general ledger (G/L) budgets. Learn more at [Create G/L Budgets](finance-how-create-budgets.md).

## View a G/L budget

In a budget with dimensions, you can filter the entries and see specific budgets.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Budgets**, then choose the related link.
2. On the **G/L Budgets** page, open the budget you want to view.  
3. At the top of the page, fill in the fields necessary to define what is shown. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> If you've selected **Period** in either the **Show as Lines** or **Show as Columns** field, then you must fill in the **View by** field. If you have not selected **Period** in either of those fields, enter the appropriate period in the **Date Filter** field.  

> [!NOTE]  
> Only entries from the general ledger budget with the filter codes you enter on the **Filters** FastTab are included in the calculation. Budget entries without any or with other filter codes are not included. As long as the filter remains on the page, the budget only displays entries with those filter codes.  

> [!TIP]  
> Use the **Edit Budget** action to modify the budget. On the budget page, choose an amount to view the underlying general ledger budget entries.

## View actual and budgeted amounts for all accounts

You can view general ledger budgets and compare them with actual figures in several areas of [!INCLUDE[prod_short](includes/prod_short.md)].

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, then choose the related link.  
2. On the **Chart of Accounts** page, choose the **G/L Balance/Budget** action.
3. On the **Options** FastTab, fill in the fields as necessary to define what is displayed in the table.  
4. Hover over a field on the table to read a short description about the displayed amount.

> [!NOTE]  
> The filters you set on the page header will be applied to both general ledger and budget entries.

The leftmost columns contain the chart of accounts. Of the five columns on the rightmost side, the first four columns show actual and budgeted debit and credit amounts for each account. The fifth column shows the proportional relationship between the actual and the budgeted amounts on the general ledger account.  

> [!TIP]  
> Use the **View by** field on the **G/L Balance/Budget** page to select the period length. Use the **View as** field to select the way the amounts will be calculated, either **Net Change** or **Balance at Date**. Choose the **Previous Period** or **Next Period** action to change the period.  

## To view actual and budgeted amounts for several periods  

Instead of viewing the actual and budgeted amounts for all accounts within a single period, you can view a number of periods for a single account.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, then choose the related link.  
2. On the **Chart of Accounts** page, select the relevant general ledger account, then choose the **G/L Account Balance/Budget** action.  
3. On the **Options** FastTab, fill in the fields as necessary to define what is displayed in the table.  
4. On the **Lines** FastTab, hover over a field on the table to read a short description about the displayed amount.  

## Related information

[Financial Business Intelligence](bi.md)  
[Work with Financial Reports](bi-how-work-account-schedule.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
