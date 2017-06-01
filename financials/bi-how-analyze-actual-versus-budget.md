---
title: 'How to: Analyze Actual Amounts Versus Budgeted Amounts| Microsoft Docs'
description: Describes how to analyze actual amounts versus budgeted amounts.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 06/01/2017
ms.author: sgroespe

---
# How to: Analyze Actual Amounts Versus Budgeted Amounts
As a part of gathering, analyzing, and sharing your company data, you view actual amounts compared to budgeted amounts for all accounts and for several periods.

To analyze budgeted amo8nts, you must first create budgets. For more information, see [How to: Create Budgets](finance-how-create-budgets.md).

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).

## To view a budget
In a budget with dimensions, you can filter the entries and see specific budgets.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **G/L Budgets**, and then choose the related link.
2. In the **G/L Budgets** window, open the budget that you want to view.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    **Note**: If you have selected **Period** in either the **Show as Lines** or the **Show as Columns** field, then you must fill in the **View by** field. If you have not selected **Period** in either the **Show as Lines** or **Show as Columns** field, then enter the appropriate period in **Date Filter** field.  

4. Choose the **Show Matrix** action to view the budget matrix.  

**Note**: Only entries from the general ledger budget with the filter codes that you enter on the **Filters** FastTab are included in the calculation. Budget entries with other filter codes or without any filter codes are not included. As long as the filter remains on the window, the budget only displays the budget entries with these filter codes.  

**Tip**: If you want to modify the budget, you can modify the budget entries. Choose an amount to view the underlying general ledger budget entries.

## To view actual and budgeted amounts for all accounts  
You can view general ledger budgets and compare them with actual figures in several areas of [!INCLUDE[d365fin](includes/d365fin_md.md)].

1. In the top right corner, choose the **Search for Page or Report** icon ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon"), enter **Chart of Accounts**, and then choose the related link.  
2. In the **Chart of Accounts** window, choose the **G/L Balance/Budget** action.
3. Fill in the fields as necessary.  
4. To see a specification that makes up the amount shown, choose the field.  

**Note**: The filters you set in the window header will be applied to general ledger entries and also budget entries.

The leftmost columns contain the chart of accounts. Of the five columns on the rightmost side, the first four columns show actual and budgeted debit and credit amounts for each account. The fifth column shows the proportional relationship between the actual and the budgeted amounts on the general ledger account.  

**Tip**: Use the **View by** field in the **G/L Balance/Budget** window to select the period length. Use the **View as** field to select the way the amounts will be calculated, **Net Change** or **Balance at Date**. Choose the **Previous Period** or **Next Period** action to change the period.  

## To view actual and budgeted amounts for several periods  
Instead of viewing the actual and budgeted amounts for all accounts within a single period, you can view a number of periods for a single account.  

1. In the top right corner, choose the **Search for Page or Report** icon ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon"), enter **Chart of Accounts**, and then choose the related link.  
2. In the **Chart of Accounts** window, select the relevant general ledger account, and then choose the **G/L Account Balance/Budget** action.  
3. Fill in the fields as necessary.   
4. To see a specification of an amount shown, choose the field.  

## See Also
[Business Intelligence](bi.md)
[How to: Work with Account Schedules](bi-how-work-account-schedule.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
