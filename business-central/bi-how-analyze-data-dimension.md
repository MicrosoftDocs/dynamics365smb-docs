---
title: Analyze Data by Dimensions| Microsoft Docs
description: Describes how to analyze various business data by dimensions.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 01/25/2018
ms.author: sgroespe

---
#  Analyze Data by Dimensions
In financial analysis, a dimension is data that you can add to an entry as a kind of marker. This data is used to group entries with similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. Dimensions can be used on entries in journals, documents, and budgets. The term dimension describes how analysis occurs. A two-dimensional analysis, for example, would be sales per area. However, by using more than two dimensions when creating an entry, you can carry out a more complex analysis, such as sales per sales campaign per customer group per area. For more information, see [Working with Dimensions](finance-dimensions.md).

Analyzing data by dimensions gives you greater insight into your business, so you can evaluate information, such as how well your business is operating, where it is thriving and where it is not, and where more resources should be allocated.

> [!TIP]
> As a quick way to analyze transactional data by dimensions, you can filter totals in the chart of accounts and entries in all **Entries** windows by dimensions. Look for the **Set Dimension Filter** action.

## To set up an analysis view  
An analysis by dimensions displays a selected combination of dimensions. You can store and retrieve each analysis you have set up. The information for setting up an analysis is stored on an **Analysis View** card to simplify future analysis.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Analysis Views**, and then choose the related link.  
2. In the **Analysis View List** window, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To add other dimension codes in addition to the four on the **Dimensions** FastTab, choose the **Filter** action, fill in the fields, and then choose the **OK** button.  
5. To update the view, choose the **Update** action.

## To analyze by dimensions
You can use the **Analysis by Dimensions** matrix to view the amounts in your general ledger by using the analysis views that you have already set up. You fill in the **Analysis by Dimensions** window to define what will be shown in the matrix, and then you choose the **Show Matrix** action to view the matrix.  

- The leftmost columns contain information based on what you have selected in the **Show as Lines** field in the header.  
- The rightmost columns contain information based on to what you have selected in the **Show as Columns** field in the header.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Analysis by Dimensions**, and then choose the related link.  
2. Select the relevant analysis view,  and then choose the **Edit Analysis View** action.
3. At the top of the **Analysis by Dimensions** window, fill in the fields to define what is shown.
4. 5. To see a specification of an amount shown in the matrix window, choose the amount.  

> [!IMPORTANT]  
>   You cannot select a period length shorter than the period specified for the date compression on the **Analysis View** card. The **Next Set** and **Previous Set** commands are inactive if you have selected **Period** in either the **Show as Lines** or the **Show as Columns** field.  

> [!NOTE]  
>   You can use the **Dimensions - Detail** report to display a detailed classification of how dimensions have been used on entries over a selected period. You can use the **Dimensions - Total** report to display only the total amounts.  

> [!TIP]  
>   You can also change the view by changing the contents of the **Show as Lines** field and **Show as Columns** field. To reverse a view setting, choose the **Reverse Lines and Columns** action.

## To update an analysis view  
The amounts that are displayed in the **Analysis by Dimensions** window give you a picture of the company’s state at the time of the last update. To get a picture of the current state, you must update the analysis view by running the update function.

The following procedure is for updating an analysis view from the **Analysis by Dimensions** window. The steps are similar from the **Analysis View Card** and the **Analysis View List** windows.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Analysis by Dimensions**, and then choose the related link.  
2. In the **Analysis by Dimensions** window, choose the **Analysis View Code** field.  
3. Select the line with the relevant analysis view.  
4. Choose the **Update** action.  

> [!TIP]  
>   If you select the **Update on Posting** check box on an analysis view card, the view is automatically updated when an involved transaction is posted.

> [!NOTE]  
>   To update some or all analysis views at the same time, you must use the **Update Analysis Views** batch job.  

## See Also
[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working with Dimensions](finance-dimensions.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
