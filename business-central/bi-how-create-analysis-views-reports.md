---
title: Create Analysis Reports| Microsoft Docs
description: Describes how to create new analysis reports for sales, purchases, and inventory, and set up analysis templates.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 04/01/2020
ms.author: sgroespe

---
#  Create Analysis Reports
Sales managers need to analyze turnover, gross profit and other key sales performance indicators on a regular basis. Purchasers, are more interested in the dynamics of purchase volumes, vendors' performance and purchase prices. Whereas logistics/inventory managers need information on inventory turnover, analysis of inventory movement, and statistics on inventory value.  

You can use analysis reports to create customized reports based on records of your posted transactions, for example, sales, purchases, transfers and inventory adjustments. In a customizable report, the source data, which is derived from the item ledger (with associated value entries), can be combined, compared and presented in meaningful user-defined ways. In this sense, the analysis report is very similar to a PivotTable report in Microsoft Excel.  

You can create your personalized report that focuses on your key accounts in terms of total turnover both in amounts and quantities sold, gross profit and gross profit percentage during the current month, and have it compare those figures with the results from previous months or the same month last year, and calculate deviations. All this can be done in one and the same view, with the possibility to navigate to the cause of identified problem areas by choosing the drop-down button to access details on the level of individual transactions.  

The analysis report consists of the objects that you want to analyze, such as customers, customer groups, sales people and so on, represented as lines, and the analysis parameters, that is, the way you want to analyze the object, represented as columns, such as profit calculations, periodic comparisons of sales amounts and volumes or periodic comparisons of actual and budgeted figures.

In addition to analysis reports, you can create and view similar information in analysis views, which are based on dimensions. For more information, see [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

## Example  
You can set up lines like these:  
- Computers  
- Displays  
- Spare Parts  

Then you can set up columns like these:  

- Sales Current Month  
- Sales Last Month  
- Sales in Pct. of last Month  

## Setting Up Line and Column Layouts  
 On the **Analysis Report** page, you can view different line and column layouts according to what you have set up. You set up your lines or line templates on the **Analysis Line Templates** page. In this page, you can define the name of the report and the objects you want to show in the lines of your report. You set up your columns on the **Analysis Column Templates** page. In this page, you can define the name of the column template and the analysis parameters that you want to show in the report as columns. On the **Analysis Column Templates** page, each line represents a column in your report. Note that analysis lines and analysis columns are independent from each other.  

Based on the lines and columns you have set up, application will aggregate the result of your report in the **Analysis Report** matrix page, such as in this example:  

| |Sales Current Month|Sales Last Month|Sales Last Month %|  
|-|-|-|-|  
|Computers| | | |  
|Displays| | | |  
|Spare parts| | | |  
|Total| | | |  

 You can, for example, set up one set of lines and several sets of column layouts to show monthly and annual reports respectively.

 ## To set up analysis column templates
The following procedure is based on analysis views for sales. The steps are similar for purchase and inventory analysis views.

In an analysis report, your analysis parameters are shown as columns. You can define the columns that you want to include in your analysis report by setting up analysis column templates.  

A template contains a set of lines each representing the analysis columns that you see in the analysis report. To define a column you must assign an analysis type code to a line. This analysis type code determines the type of source data in the item ledger entries that the analysis will be based on. Source data includes cost, sales amount, or quantity, and their associated value entries. You can set up as many column templates as you like, and then use them to create new analysis reports.    

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Column Templates**, and then choose the related link.  
2. Select the first empty line, and then fill in the fields as necessary.
3. Choose the **Columns** action.  
4. On the **Analysis Columns** page, fill in the fields to specify the columns that you want to include in your analysis report.  

    > [!NOTE]  
    >   To define a column, you must fill in the **Analysis Type Codes** field for all column types except **Formula**. Set up the analysis type codes on the **Analysis Types** page.  
    Also, in the **Ledger Entry Type** field, if you select **Item Entries**, the actual figures from the item ledger entry are copied. If you select **Item Budget Entries**, the budgeted figures from the budget are copied.  
5.  Choose the **OK** button to save your changes.  

## To set up analysis line templates  
The following procedure is based on analysis reports for sales. The steps are similar for purchase and inventory analysis reports.

In an analysis report your analysis objects are shown on the lines. You can define the lines that you want to include in your analysis report by setting up analysis line templates.  

A template contains a set of lines representing the analysis lines that you see in the analysis report. A line can specify one or a range of items, customers, vendors, or groups. You can also create a formula in a line to sum up the other lines. You can set up as many line templates as you like, and then use them to create new analysis reports.    

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Line Templates**, and then choose the related link.  
2. Select the first empty line, and then fill in the fields as necessary.
3. Choose the **Lines** action.  
4. On the **Analysis Lines** page, create lines for the items, customers, vendors, or salespeople you want to view figures for in your analysis report. You must fill in the **Type**, **Range**, and the **Description** fields.  

> [!NOTE]  
>   Alternatively, when you want to create many individual lines for each item, customer, and so on, you can select the appropriate insert option to fill in all the relevant fields on the line. If you need to, you can then edit the lines manually. To insert lines, choose the **Insert Items** action or the **Insert Item Groups** action.  

## To create a new sales analysis report
The following procedure is based on analysis reports for sales. The steps are similar for purchase and inventory analysis reports.

You use analysis reports to analyze the dynamics of your sales according to key sales performance indicators that you select, for example, sales turnover in both amounts and quantities, contribution margin, or progress of actual sales against the budget. You can also use the report to analyze your average sales prices and evaluate the sales performance of your sales force.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Analysis Reports**, and then choose the related link.  
2. On the **Analysis Report Sale** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **Edit Analysis Report** action.
5. On the **Sales Analysis Report** page, choose the **Show Matrix** action  

> [!NOTE]  
>   Building combinations of line and column templates to create reports and assigning them unique names is optional. If you do this, selecting a report name means that you will not need to select line and column templates on the **Sales Analysis Report** page. After you have chosen a report name, you can change line and column templates independently and then later select the report name again to restore the original combination.

## See Also
[Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
