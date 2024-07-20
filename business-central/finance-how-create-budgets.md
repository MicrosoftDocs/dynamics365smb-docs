---
title: Creating G/L budgets
description: Describes how to create G/L budgets to forecast different financial activities and assign dimensions for business intelligence purposes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: postpone
ms.search.form: 113, 120, 121, 154, 350, 422, 7132, 7133, 7138, 7139, 9203, 9219, 9239, 9373, 9374
ms.date: 06/10/2024
ms.service: dynamics-365-business-central

---
# Create G/L budgets

Budgets play an important role in business intelligence. Examples include a financial statement based on financial reports that include budget entries or when analyzing budgeted versus actual amounts in the chart of accounts. Learn more at [Financial Reporting](bi.md).
 
You can create budgets for any given time period but most often businesses set up budgets covering their fiscal year. You can create multiple budgets for the same period so you can work with multiple budget versions or revisions if needed. Budgets can be created for dimensions too, so you can analyses budget variances per dimension. You can work with up to 4 dimensions in a budget. Learn more at [Work with Dimensions](finance-dimensions.md).

In cost accounting, you work with cost budgets in a similar way. Learn more at [Creating Cost Budgets](finance-create-cost-budgets.md).  

## To create a new G/L budget

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Budgets**, and then choose the related link.  
2. Choose the **Edit List** action, then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Choose the **Edit Budget** action.
4. At the top of the **Budget** page, fill in the fields as necessary to define what is displayed.  

   The page shows only entries that contain the budget name you entered in the **Budget Name** field. Because you just created the budget name, there are no entries that match the filter. Therefore, the page is empty.  
5. To enter an amount, choose the relevant cell in the matrix. The **G/L Budget Entries** page opens.  
6. Create a new line and fill in the **Amount** field. Close the **G/L Budget Entries** page.  
7. Repeat steps 5 and 6 for all amounts in the budget.  

> [!NOTE]  
> On the **Filters** FastTab, you can filter the budget information by the budget dimensions you set up under the budget name.

## Exporting and importing G/L budgets with Excel

You can export data on budget pages to Microsoft Excel for further processing or analysis and then import budget data back in [!INCLUDE[prod_short](includes/prod_short.md)].

> [!NOTE]
> The chart of accounts, which general ledger (G/L) budgets are based on, has lines of the account type Heading. These lines contain the total of the lines below it. When you export a G/L budget, you export data on all lines regardless of the account type. However, you can only import data on lines of the Posting account type. Similarly, when you import a G/L budget, any values on Heading lines are deleted. They're deleted to avoid incorrect totals after you import data that was created or edited in Excel.

### Exporting G/L budgets to Excel

Exporting a G/L budget to an Excel workbook allows you to work offline and leverage Excel's powerful data manipulation features. Do as follows to export the budget to Excel:

1. Open the Budget: Select the budget you want to work on from the list of G/L budgets. Choose the **Edit Budget** action.
1. To export to Excel, on the **Budget** page, choose the **Actions** tab.
1. Choose **Export to Excel**.
1. Choose the dimensions and filters you want to include in the export. For instance, you might want to filter by specific departments or projects. Now choose **OK** to generate the Excel file.
1. Save the exported Excel file to your local drive for further editing.

### Editing G/L budgets in Excel

With the G/L budget exported to Excel, you can now fill in your budget data. Here's a few tips to be more effective and reduce errors

- When enterin budget data, populate the budget amounts for each combination of dimensions and periods. Ensure that the data is accurate and adheres to the formatting requirements of Business Central. For example, numerical values should not contain any special characters or formatting.
- Take advantage of Excel features such as formulas, data validation, and conditional formatting to streamline data entry and ensure accuracy.
- Once you've entered all the budget data, ensure that the Excel file has been saved. 
- Consider keeping backup copies of your budgets locally.

### Importing G/L budgets to Excel

After filling out budget numbers in a local Excel workbook, the next step is to import it back into [!INCLUDE[prod_short](includes/prod_short.md)]. Do as follows to import the budget from Excel:

1. Open the Budget: Select the budget you want to work on from the list of G/L budgets. Choose the **Edit Budget** action.
1. To import from Excel, on the **Budget** page, choose the **Home** tab.
1. Choose **Import from Excel**.
1. Choose the Excel file from your local drive. You will be given the option to choose which budget you are uploading to and if you would like to add or replace the entries. The **add** action will add the entries from Excel to any entries already existing. The **replace** action will overwrite any entries all ready in the budget. 
1. If everything looks correct, choose **OK** to complete the import process. [!INCLUDE[prod_short](includes/prod_short.md)] will then update the budget with the imported data.

### Scenario

You know that the new budgeted salaries cost is going to be local currency (LCY) 1.200.000. You want to enable the Salaries department to budget for the three specific lines (of the Posting account type) for full-time employees, part-time employees, and temp help. The three lines are grouped under a Salaries heading line.

You enter 1.200.000 on the Heading line, export the budget to Excel, then send it to the Salaries department, telling them to distribute the LCY 1.200.000.

The Salaries department distributes the amount on the three posting accounts. When you import back into the G/L budget, the three accounts are filled in with the new Excel data, summing to LCY 1.200.000, and the Heading line is blank.

## Tips for Effective Budget Management

When working with budgets, here are some tips for effective budget management:

- Regular Updates: Periodically update your G/L budgets to reflect changes in your financial plans and business environment. You can copy any of the budgets and turn them into forecasts.
- Version Control: Maintain different versions of your budget to compare actual performance against various scenarios.
- Collaboration: Encourage collaboration by involving relevant stakeholders in the budgeting process, ensuring that the budget is comprehensive and realistic.

## Contributors

*This article is maintained by Microsoft. Some content was originally written by the following contributors.*

* [Michelle Serna](https://www.linkedin.com/in/michelleserna1/) | Director of ERP systems.

## See also

[Exporting Your Business Data to Excel](about-export-data.md)  
[Finance](finance.md)  
[Business Intelligence](bi.md)  
[Setting Up Finance](finance-setup-finance.md)  
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
