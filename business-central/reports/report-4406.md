---
title: Trial Balance/Budget (Excel report)
description: Use Excel to view a snapshot of your chart of accounts at a given point to check the debit and credit net change and closing balance compared to the budget.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_4406_Primary
ms.date: 12/17/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/17/2024
ai.usage: ai-assisted
---

# Trial Balance/Budget Excel (report)

The **Trial Balance/Budget Excel** report shows aggregated general ledger data for the trial balance with debit/credit columns for net change and balance.

In addition to net change and balance amounts, the report also shows the net budget amounts and budget balances for comparison. 

The aggregation is for the period specified in the report's request page's Datefilter parameter and summarised per the 2 global dimensions per g/l account category.

The Excel workbook contains two worksheets that you can use to analyze your trial balance vs budget:

- Trial Balance vs. Budget
- TrialBalanceBudgetData

Each worksheet represents a different dimension for your analysis.

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

> [!NOTE]
> This report does the calculations when you view it in Excel online, or when you download and open it. If a banner displays text about external data connections, you might need to choose the **Enable content** button to load data. The report doesn't connect to any external data sources. All calculations are done in Excel with Power Query. In some cases (depending on the security configurations for your organization), you might also need to right-click on a pivot table in one of the worksheets and choose **Refresh** to update data in the reports.

## Trial Balance vs. Budget worksheet

This worksheet shows the trial balance vs. budget with amounts in local currency (LCY).

Filters and slicers let you zoom in on the balance as seen from global dimensions, or by account categories and subcategories.

:::image type="content" source="../media/excel-trial-balance-vs-budget-worksheet.png" alt-text="Screenshot of the Trial Balance (LCY) worksheet":::

## TrialBalanceBudgetData worksheet

This worksheet shows the raw data used in the report.

You can use this worksheet for data analysis assisted by built-in tools in Excel, such as [!INCLUDE [excel-copilot-name](../includes/excel-copilot-name.md)], or the What-if-analysis or Forecast Sheet tools.

:::image type="content" source="../media/excel-trial-balance-vs-budget-data.png" alt-text="Screenshot of the TrialBalanceData worksheet":::

To learn more, go to [Get started with Copilot in Excel](https://support.microsoft.com/en-us/office/get-started-with-copilot-in-excel-d7110502-0334-4b4f-a175-a73abdfc118a).

## Use cases

[!INCLUDE [report-4406-scenario](../includes/report-4406-scenario-include.md)]

Use the report to assess how well you're following your financial plans and identify variances between actual and budgeted amounts. The report is useful for financial analysis and decision-making at the end of an accounting period or fiscal year.


<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with core finance.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 
Do not start lines with ""Use the data to""


## Report description
Shows a trial balance in comparison to a budget. You can choose to see a trial balance for selected dimensions. Use this report at the close of an accounting period or fiscal year.

### What the report does
Shows G/L accounts with debit and credit net change and balance for the specified period. Also shows % of actual vs budget. Can be filtered by Dimensions.

### Use cases
View a snapshot of your chart of accounts at a given point in time, to check the debit and credit net change and closing balance compared to the budget.
This report helps businesses assess how well they are adhering to their financial plans and identify any variances between actual and budgeted amounts. It's particularly useful for financial analysis and decision-making at the end of an accounting period or fiscal year.

Please include your data sources and URLs

-->

Financial analysts use the report to:

* Analyze the financial performance of the business. Review the variances between actual and budgeted amounts of each account in the chart of accounts.
* Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
* Use the report data to prepare financial reports for stakeholders such as investors or executives.

Accountants use the report to:

* Use the report data in comparison with budget amounts to prepare financial statements, such as income statements, balance sheets, and cash flow statements.
* Verify the accuracy of the financial data by ensuring that debits and credits balance, and compare the actual vs. budgeted amounts.
* Analyze the financial health of the business. Review the variances between the actual and budgeted amounts of each account in the chart of accounts.

Controllers use the report to:

* Monitor the financial performance of the business. Review the variances between actual and budgeted amounts for each account in the chart of accounts.
* Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
* Use the report data to prepare financial reports for internal and external stakeholders such as board members or regulatory agencies.

## Try the report

Try the report here: [Trial Balance/Budget Excel](https://businesscentral.dynamics.com?report=4406)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze your balance. To learn more, go to:

- [Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)
- [Trial Balance/Budget (legacy)](../reports/report-9.md)
- [Financial Reporting](../bi-how-work-account-schedule.md)

## Related information

[Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)  
[Trial Balance/Budget (legacy)](../reports/report-9.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Power BI finance app](../finance-powerbi-app.md)  
[Financial Reporting](../bi-how-work-account-schedule.md)
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]