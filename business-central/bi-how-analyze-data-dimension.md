---
title: Analyze data by dimensions
description: This article describes how you can analyze business data by dimensions to gain greater insight into your business.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 545, 555, 556, 557, 558, 9372, 9370, 9371
ms.date: 04/19/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Analyze data by dimensions

In financial analysis, a dimension is data you add to an entry as a kind of marker to group entries with similar characteristics. For example, dimensions often group entries for customers, regions, products, and salespeople. The groups let you easily retrieve data about them for analysis. You can use dimensions on entries in journals, documents, and budgets.

Each dimension describes the focus of analysis. So, a two-dimensional analysis, for example, would be sales per area. By using more than two dimensions when you create an entry, you can carry out a more complex analysis. An example of a complex analysis is exploring sales per sales campaign per customer group per area. That gives you greater insight into your business, such as how well your business is operating, where it is or isn't thriving, and where you should allocate more resources. That insight helps you make more informed business decisions. Learn more at [Work with Dimensions](finance-dimensions.md).

> [!TIP]
> As a quick way to analyze transactional data by dimensions, you can filter totals in the chart of accounts (COA) and entries in all **Entries** pages by dimensions. Look for the **Set Dimension Filter** action.

> [!NOTE]
> If you discover that an incorrect dimension value was used on posted general ledger entries, you can correct it and update your analysis views. To learn more, go to [Troubleshooting and Correcting Dimensions](finance-troubleshooting-correcting-dimensions.md#changing-dimension-assignments-after-posting).

## Set up an analysis view

An analysis by dimensions uses a selected combination of dimensions. You store, retrieve, and update that dimension set by creating an **Analysis View** card.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Analysis Views**, then choose the related link.  
2. On the **Analysis View List** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To add other dimension codes in addition to the four on the **Dimensions** FastTab, choose the **Filter** action, fill in the fields, then choose the **OK** button.  
5. To update the view, choose the **Update** action.

## Analyze by dimensions

Use analysis views you've already set up with the **Analysis by Dimensions** matrix to view the amounts in your general ledger.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Analysis Views**, then choose the related link.  
2. Select the relevant analysis view, then choose the **Analysis by Dimensions** action.
3. On the **Analysis by Dimensions** page, fill in the fields to define what data to show, and how.
4. Choose the **Show Matrix** action to open the matrix page for the analysis view.
5. To access details of an amount in the matrix page, choose the amount.  

- The columns on the left contain information based on what you've selected in the **Show as Lines** field in the header.  
- The columns on the right contain information based on what you've selected in the **Show as Columns** field in the header.

> [!IMPORTANT]  
> You can't select a period length that's shorter than the period specified for the date compression on the **Analysis View** card. The **Next Set** and **Previous Set** actions aren't available if you've selected **Period** in either the **Show as Lines** or **Show as Columns** fields.  

> [!NOTE]  
> You can use the **Dimensions - Detail** report to display a detailed classification of how dimensions have been used on entries over a selected period. You can use the **Dimensions - Total** report to display only the total amounts.  

> [!TIP]  
> You can also change the view by changing the contents of the **Show as Lines** and **Show as Columns** fields. To reverse a view setting, choose the **Reverse Lines and Columns** action.

## Update an analysis view

The amounts on the **Analysis by Dimensions** page give you a picture of the company's state at the time of the last update. To get the current state, run the update action to update the analysis view.

Use the following procedure to update an analysis view from the **Analysis by Dimensions** page. The steps are similar to those for updating the **Analysis View Card** and **Analysis View List** pages.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Analysis Views**, then choose the related link.
2. Select the relevant analysis view, then choose the **Analysis by Dimensions** action.
3. On the **Analysis by Dimensions** page, choose the **Analysis View Code** field.  
4. Select the line with the relevant analysis view.  
5. On the **Analysis Views** page, select the analysis view, then choose the **Update** action.  

> [!TIP]  
> If you select the **Update on Posting** checkbox on an analysis view card, the view automatically updates when someone posts an associated transaction.

> [!NOTE]  
> To update some or all analysis views at the same time, use the **Update Analysis Views** batch job.  

## Related information

[Financial analytics overview](bi.md)   
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with Dimensions](finance-dimensions.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
