---
title: Analyze Data by Dimensions
description: This article describes how you can analyze business data by dimensions to gain greater insight into your business.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 545, 555, 556, 557, 558, 9372, 9370, 9371
ms.date: 09/22/2022
ms.author: bholtorf
---
# Analyze Data by Dimensions

In financial analysis, a dimension is data you add to an entry as a kind of marker. This data is used to group entries with similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis. Dimensions can be used on entries in journals, documents, and budgets. 

Each "dimension" describes the focus of analysis. So, a two-dimensional analysis, for example, would be sales per area. By using more than two dimensions when creating an entry, you can carry out a more complex analysis, such as sales per sales campaign per customer group per area. That gives you greater insight into your business, such as how well your business is operating, where it is thriving and where it is not, and where more resources should be allocated, so you can make more informed decisions as you move forward. Learn more at [Work with Dimensions](finance-dimensions.md).

> [!TIP]
> As a quick way to analyze transactional data by dimensions, you can filter totals in the chart of accounts (COA) and entries in all **Entries** pages by dimensions. Look for the **Set Dimension Filter** action.

> [!NOTE]
> If you discover an incorrect dimension value has been used on posted general ledger entries, you can correct it and update your analysis views. Learn more in the [Troubleshooting and Correcting Dimensions](finance-troubleshooting-correcting-dimensions.md#changing-dimension-assignments-after-posting) section.

## Set up an analysis view

An analysis by dimensions uses a selected combination of dimensions. You store, retrieve, and update that dimension set by creating an **Analysis View** card. 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Analysis Views**, then choose the related link.  
2. On the **Analysis View List** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To add other dimension codes in addition to the four on the **Dimensions** FastTab, choose the **Filter** action, fill in the fields, then choose the **OK** button.  
5. To update the view, choose the **Update** action.

## Analyze by dimensions

Use analysis views you've already set up with the **Analysis by Dimensions** matrix to view the amounts in your general ledger.   

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Analysis Views**, then choose the related link.  
2. Select the relevant analysis view, then choose the **Analysis by Dimensions** action.
3. On the **Analysis by Dimensions** page, fill in the fields to define which data is shown and how.
4. Choose the **Show Matrix** action to open the respective matrix page for the defined analysis view.
5. To see a specification of an amount shown in the matrix page, choose the amount to drill down.  

- The leftmost columns contain information based on what you've selected in the **Show as Lines** field in the header.  
- The rightmost columns contain information based on what you've selected in the **Show as Columns** field in the header.

> [!IMPORTANT]  
> You cannot select a period length shorter than the period specified for the date compression on the **Analysis View** card. The **Next Set** and **Previous Set** commands are inactive if you've selected **Period** in either the **Show as Lines** or **Show as Columns** field.  

> [!NOTE]  
> You can use the **Dimensions - Detail** report to display a detailed classification of how dimensions have been used on entries over a selected period. You can use the **Dimensions - Total** report to display only the total amounts.  

> [!TIP]  
> You can also change the view by changing the contents of the **Show as Lines** and **Show as Columns** fields. To reverse a view setting, choose the **Reverse Lines and Columns** action.

## Update an analysis view

The amounts displayed on the **Analysis by Dimensions** page give you a picture of the company's state at the time of the last update. To get a picture of the current state, you must update the analysis view by running the update function.

Use the following procedure to update an analysis view from the **Analysis by Dimensions** page. The steps are similar to those for updating the **Analysis View Card** and **Analysis View List** pages.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Analysis Views**, then choose the related link.
2. Select the relevant analysis view, then choose the **Analysis by Dimensions** action.
3. On the **Analysis by Dimensions** page, choose the **Analysis View Code** field.  
4. Select the line with the relevant analysis view.  
5. On the **Analysis Views** page, select the analysis view, then choose the **Update** action.  

> [!TIP]  
> If you select the **Update on Posting** check box on an analysis view card, the view is automatically updated when an associated transaction is posted.

> [!NOTE]  
> To update some or all analysis views at the same time, you must use the **Update Analysis Views** batch job.  

## See also

[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with Dimensions](finance-dimensions.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
