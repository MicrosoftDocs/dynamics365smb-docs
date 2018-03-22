---
title: Creating G/L Budgets| Microsoft Docs
description: Describes hos to create G/L budgets to forecast different financial activities and assign dimensions for business intelligence purposes.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: postpone
ms.date: 01/25/2018
ms.author: sgroespe

---
# Create G/L Budgets
You can have multiple budgets for identical time periods by creating budgets with separate names. First, you set up the budget name and enter the budget figures. The budget name is then included on all the budget entries you create.  

 When you create a budget, you can define four dimensions for each budget. These budget-specific dimensions are called budget dimensions. You select the budget dimensions for each budget from among the dimensions you have already set up. Budget dimensions can be used to set filters on a budget and to add dimension information to budget entries. For more information, see [Working with Dimensions](finance-dimensions.md).

 Budgets play an important role in business intelligence, such as in financial statement based on account schedules that include budget entries or when analyzing budgeted versus actual amounts in the chart of accounts. For more information, see [Business Intelligence](bi.md).

 Budgets play an important role in business intelligence, such as in financial statement based on account schedules that include budget entries or when analyzing budgeted versus actual amounts in the chart of accounts. For more information, see [Business Intelligence](bi.md).

In cost accounting, you work with cost budgets in a similar way. For more information, see [Creating Cost Budgets](finance-create-cost-budgets.md).    

## To create a new G/L budget  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Budgets**, and then choose the related link.  
2. Choose the **Edit List** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choose the **Edit Budget** action.
4. At the top of the **Budget** window, fill in the fields as necessary to define what is displayed.  

    Only entries that contain the budget name that you entered in the **budget Name** field are shown. Because the budget name has just been created, there are no entries that match the filter. Therefore, the window is empty.  
5. To enter an amount, choose the relevant cell in the matrix. The **G/L Budget Entries** window opens.  
6. Create a new line and fill in the **Amount** field. Close the **G/L Budget Entries** window.  
7. Repeat steps 5 and 6 until you have entered all of the budget amounts.  

> [!NOTE]  
>  On the **Filters** FastTab, you can filter the budget information by budget dimensions you have set up under the budget name.   

## See Also
[Finance](finance.md)  
[Business Intelligence](bi.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
