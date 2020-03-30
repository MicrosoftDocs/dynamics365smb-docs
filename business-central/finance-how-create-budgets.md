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
ms.date: 04/01/2020
ms.author: sgroespe

---
# Create G/L Budgets
You can have multiple budgets for identical time periods by creating budgets with separate names. First, you set up the budget name and enter the budget figures. The budget name is then included on all the budget entries you create.  

When you create a budget, you can define four dimensions for each budget. These budget-specific dimensions are called budget dimensions. You select the budget dimensions for each budget from among the dimensions you have already set up. Budget dimensions can be used to set filters on a budget and to add dimension information to budget entries. For more information, see [Working with Dimensions](finance-dimensions.md).

Budgets play an important role in business intelligence, such as in financial statement based on account schedules that include budget entries or when analyzing budgeted versus actual amounts in the chart of accounts. For more information, see [Business Intelligence](bi.md).

In cost accounting, you work with cost budgets in a similar way. For more information, see [Creating Cost Budgets](finance-create-cost-budgets.md).    

## To create a new G/L budget  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Budgets**, and then choose the related link.  
2. Choose the **Edit List** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choose the **Edit Budget** action.
4. At the top of the **Budget** page, fill in the fields as necessary to define what is displayed.  

    Only entries that contain the budget name that you entered in the **budget Name** field are shown. Because the budget name has just been created, there are no entries that match the filter. Therefore, the page is empty.  
5. To enter an amount, choose the relevant cell in the matrix. The **G/L Budget Entries** page opens.  
6. Create a new line and fill in the **Amount** field. Close the **G/L Budget Entries** page.  
7. Repeat steps 5 and 6 until you have entered all of the budget amounts.  

> [!NOTE]  
>  On the **Filters** FastTab, you can filter the budget information by budget dimensions you have set up under the budget name.

## Exporting and Importing G/L Budgets with Excel
As for practically all other pages, you can export data on budget pages to Excel for further processing or analysis. For more information, see [Exporting Your Business Data to Excel](about-export-data.md).

> [!NOTE]
> The chart of accounts, that G/L budgets are based on, have lines of account type Heading that contain the total of the lines below it. When you export a G/L budget, data on all lines is exported regardless of the account type. However, only data on lines of account type Posting can be imported back in. Accordingly: <br /><br /> **When you import a G/L budget, any values that existed on Heading lines will be deleted.** <br /><br /> This is to avoid wrong totals after importing data that has been created or edited in Excel.<br /><br /> **Scenario**: You know that the new budgeted salaries cost is going to be LCY 1.200.000. You want to let the Salaries department budget for the three specific lines (of account type Posting) for Full-time Employees, Part-time Employees, and Temp Help. The three lines are grouped under a Salaries heading line.<br /><br />You enter 1.200.000 on the Heading line, export the budget to Excel, and then send it to the Salaries department, telling them to distribute the LCY 1.200.000.<br /><br /> The Salaries department distributes the amount on the three posting accounts. When you import back into the G/L budget, the three accounts are filled in with the new Excel data, summing to LCY 1.200.000, and the Heading line is blank.

## See Related Training at [Microsoft Learn](/learn/modules/budgets-exchange-rates-dynamics-365-business-central/index)

## See Also
[Exporting Your Business Data to Excel](about-export-data.md)  
[Finance](finance.md)  
[Business Intelligence](bi.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
