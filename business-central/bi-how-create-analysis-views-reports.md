---
title: Create analysis reports
description: Describes how to create new analysis reports for sales, purchases, and inventory, and set up analysis templates.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 555, 556, 557, 558, 9372, 9370, 9371 
ms.date: 04/08/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create analysis reports

Sales managers need to analyze turnover, gross profit, and other key sales performance indicators regularly. Purchasers are more interested in the dynamics of purchase volumes, vendor performance, and purchase prices. Whereas logistics/inventory managers need information on inventory turnover, analysis of inventory movement, and statistics on inventory value. So there's no one-size-fits-all analysis report.

You can customize analysis reports based on records of your posted transactions, for example, sales, purchases, transfers, and inventory adjustments. In a customizable report, the source data, which is derived from the item ledger (with associated value entries), can be combined, compared, and presented in meaningful user-defined ways. In this sense, the analysis report is similar to a PivotTable report in Microsoft Excel.  

So, for example, you can create a personalized report that focuses on your key accounts in terms of total product turnover in amounts and quantities sold, gross profit, and gross profit percentage during the current month. Then you can have it compare those figures with the results from previous months or the same month last year, and calculate deviations. All this can be done in one and the same view, enabling you to navigate to the cause of identified problem areas and even choose the drop-down to zero in on details all the way down to the level of individual transactions.  

The analysis report consists of the objects you want to analyze (such as customers, customer groups, sales people, and so on, represented as lines) and the analysis parameters, which is the way you want to analyze the object (such as profit calculations, periodic comparisons of sales amounts and volumes or periodic comparisons of actual and budgeted figures, represented as columns). 

In addition to analysis reports, you can create and view similar information in analysis views (based on dimensions). Learn more at [Analyze Data by Dimensions](bi-how-analyze-data-dimension.md).

## Example

You can set up these lines (objects you want to analyze):  

- Computers  
- Displays  
- Spare Parts  

Then you can set up these columns (how you want the objects analyzed):  

- Sales Current Month  
- Sales Last Month  
- Sales in Pct. of last Month  

## Setting up line and column layouts

On the **Analysis Report** page, you can view different line and column layouts that you set up on the:

* **Analysis Line Templates** page where you define the name of the report and the objects you want to show in the lines of your report, and the
* **Analysis Column Templates** page where you define the name of the column template and the analysis parameters that show in the report as columns. Each line on this page represents a column in your report. 

Note that analysis lines and analysis columns are independent from each other.  

Based on the lines and columns you set up, [!INCLUDE[prod_short](includes/prod_short.md)] aggregates the result of your report in the **Analysis Report** page, as shown in the following table.  

|- |Sales Current Month|Sales Last Month|Sales Last Month %|  
|-|-|-|-|  
|Computers| | | |  
|Displays| | | |  
|Spare parts| | | |  
|Total| | | |  

You can, for example, set up one group of lines and several groups of column layouts to show monthly and annual reports, respectively.

## Set up analysis column templates

The following procedure is based on sales analysis views. The steps are similar for purchase and inventory analysis views.

An analysis column template contains a set of lines, each representing an analysis column you want in the analysis report. To define a column, you must assign an analysis type code to a line. This analysis type code determines the type of source data in the item ledger entries that the analysis will be based on. Source data can include cost, sales amount, or quantity, and their associated value entries. You can set up as many column templates as you like, then use them to create new analysis reports.    

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Column Templates**, then choose the related link.  
2. Select the first empty line and fill in the fields as necessary.
3. Choose the **Columns** action.  
4. On the **Analysis Columns** page, fill the fields in to specify the columns you want in your analysis report.  

    > [!NOTE]  
    > To define a column, you must fill in the **Analysis Type Codes** field for all column types except **Formula**. Set up the analysis type codes on the **Analysis Types** page.  
    >
    > Also, in the **Ledger Entry Type** field, if you select **Item Entries**, the actual figures from the item ledger entry are copied. If you select **Item Budget Entries**, the budgeted figures from the budget are copied.  
5. Choose **OK** to save your changes.  

## Set up analysis line templates

The following procedure is based on analysis reports for sales. The steps are similar for purchase and inventory analysis reports.

An analysis line template contains a set of lines, each representing an analysis line you want in the analysis report. A line can specify one or a range of items, customers, vendors, or groups. You can also create a formula in a line to sum up the other lines. You can set up as many line templates as you like, then use them to create new analysis reports.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Line Templates**, then choose the related link.  
2. Select the first empty line, and then fill in the fields as necessary.
3. Choose the **Lines** action.  
4. On the **Analysis Lines** page, create lines for the items, customers, vendors, or salespeople you want to view figures for in your analysis report. You must fill in the **Type**, **Range**, and the **Description** fields.  

> [!NOTE]  
> Alternatively, to create many individual lines for each item, customer, and so on, you can select the appropriate insert option to fill in all the relevant fields on the line. If you need to, you can then edit the lines manually. To insert lines, choose the **Insert Items** or **Insert Item Groups** action.  

## Create a new sales analysis report

The following procedure is based on analysis reports for sales. The steps are similar for purchase and inventory analysis reports.

With analysis reports you can analyze the dynamics of your sales according to key sales performance indicators, such as sales turnover in both amounts and quantities, contribution margin, or progress of actual sales against the budget. You can also use analysis reports to analyze your average sales prices and evaluate the sales performance of your sales force.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Analysis Reports**, then choose the related link.  
2. On the **Analysis Report Sale** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **Edit Analysis Report** action.
5. On the **Sales Analysis Report** page, choose the **Show Matrix** action  

> [!NOTE]  
> Building combinations of line and column templates to create reports and assigning them unique names is optional. If you do this, you won't need to select line and column templates on the **Sales Analysis Report** page. After you have chosen a report name, you can change line and column templates independently and then later select the report name again to restore the original combination.

## Related information

[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
