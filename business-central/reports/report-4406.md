---
title: Trial Balance/Budget (Excel report)
description: Use Excel to view a snapshot of your chart of accounts at a given point to check the debit and credit net change and closing balance compared to the budget.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
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

The **Trial Balance/Budget Excel** report shows general ledger data subtotaled by general ledger account for net change, percent of budget net, net budget, balance, percent of budget balance and budget balance. Amounts are in local currency (LCY).

Data is aggregated for the period specified in the **Datefilter** parameter on the report's request page, and summarized by the two global dimensions per G/L account category.

The Excel workbook contains two worksheets that you can use to analyze your trial balance vs. budget:

- Trial Balance vs. Budget,
- TrialBalanceBudgetData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Trial Balance vs. Budget worksheet

This worksheet shows the trial balance vs. the budget with amounts in LCY.

Filters and slicers let you zoom in on the balance as seen from global dimensions, or by account categories and subcategories.

:::image type="content" source="../media/excel-trial-balance-vs-budget-worksheet.png" alt-text="Screenshot of the Trial Balance (LCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## TrialBalanceBudgetData worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-trial-balance-vs-budget-data.png" alt-text="Screenshot of the TrialBalanceData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

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

- Analyze the financial performance of the business. Review the variances between actual and budgeted amounts of each account in the chart of accounts.
- Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
- Use the report data to prepare financial reports for stakeholders such as investors or executives.

Accountants use the report to:

- Use the report data in comparison with budget amounts to prepare financial statements, such as income statements, balance sheets, and cash flow statements.
- Verify the accuracy of the financial data by ensuring that debits and credits balance, and compare the actual vs. budgeted amounts.
- Analyze the financial health of the business. Review the variances between the actual and budgeted amounts of each account in the chart of accounts.

Controllers use the report to:

- Monitor the financial performance of the business. Review the variances between actual and budgeted amounts for each account in the chart of accounts.
- Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
- Use the report data to prepare financial reports for internal and external stakeholders such as board members or regulatory agencies.

## Try the report

Try the report here: [Trial Balance/Budget Excel](https://businesscentral.dynamics.com?report=4406)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your balance. To learn more, go to:

- [Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)
- [Trial Balance/Budget (legacy)](../reports/report-9.md)
- [Financial Reporting](../bi-how-work-account-schedule.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)  
[Trial Balance/Budget (legacy)](../reports/report-9.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Power BI finance app](../finance-powerbi-app.md)  
[Financial Reporting](../bi-how-work-account-schedule.md)
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]