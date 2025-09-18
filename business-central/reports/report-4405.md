---
title: Trial Balance (Excel report)
description: Use Excel to view a snapshot of your chart of accounts at a given point to check the debit and credit net change and closing balance. 
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_4405_Primary
ms.date: 06/15/2025
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/13/2024
ai.usage: ai-assisted
---

# Trial Balance Excel (report)

The **Trial Balance Excel** report shows aggregated and summarized general ledger data for a trial balance with debit and credit columns for net change and balance.

Your trial balance shows in both your local currency (LCY) and additional reporting currency (ACY). However, the report only shows data for the latter if you have setup the additional reporting currency feature.

Data is aggregated for the period specified by the Datefilter parameter on the report's request page and summarized by the two global dimensions per G/L account category.

The Excel workbook contains three worksheets that you can use to analyze your trial balance:

- Trial Balance (LCY)
- Trial Balance (ACY)
- TrialBalanceData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## Trial Balance (LCY) worksheet

This worksheet shows the trial balance with amounts in LCY. The accounts from the chart of account hierarchy don't display as a hierarchy in the report. You can't expand or collapse an account in the report to summarize its data.

Filters and slicers let you zoom in on the balance as seen from global dimensions, or by account categories and subcategories.

:::image type="content" source="../media/excel-trial-balance-trial-balance-lcy.png" alt-text="Screenshot of the Trial Balance (LCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Trial Balance (ACY) worksheet

This worksheet shows the trial balance with amounts in ACY. The report requires that you use ACY.

Filters and slicers let you zoom in on the balance as seen from global dimensions, or by account categories and subcategories.

:::image type="content" source="../media/excel-trial-balance-trial-balance-acy.png" alt-text="Screenshot of the Trial Balance (ACY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## TrialBalanceData worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-trial-balance-trial-balance-data.png" alt-text="Screenshot of the TrialBalanceData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4405-scenario](../includes/report-4405-scenario-include.md)]

Use the report to verify the accuracy of your financial data by ensuring that debits and credits balance. Businesses typically use the report at the end of an accounting period to prepare financial statements and assess their financial health.

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with core finance.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 
Do not start lines with ""Use the data to""

## Report name
Trial Balance

## Report description
Shows the chart of accounts with balances and net changes. You can choose to see a trial balance for selected dimensions or use the report at the close of an accounting period or fiscal year.

### What the report does
Shows G/L accounts with a balance at date, and net change over the specified period. Can be filtered by Dimensions.

The report also includes subtotalling accounts and can be configured to show figures in the additional reporting currency.

### Use cases
View a snapshot of your chart of accounts at a given point in time, to check the debit and credit net change and closing balance.
This report helps businesses verify the accuracy of their financial data by ensuring that debits and credits are balanced. It's typically used at the end of an accounting period to prepare financial statements and assess the financial health of the business.

Please include your data sources and URLs

-->

Financial analysts use the report to:

- Analyze the financial trends of the business by reviewing the balances and net changes of each account in the chart of accounts over time.
- Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
- Use the report data to prepare financial reports for stakeholders such as investors or executives.

Accountants use the report to:

- Use the report data to prepare financial statements, such as income statements, balance sheets, and cash flow statements.
- Verify the accuracy of the financial data by ensuring that debits and credits balance.
- Analyze the financial health of the business by reviewing the net changes and closing balances of each account in the chart of accounts.

Controllers use the report to:

- Monitor the financial performance of the business by reviewing the balances and net changes of each account in the chart of accounts.
- Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
- Use the report data to prepare financial reports for internal and external stakeholders such as board members or regulatory agencies.

## Try the report

Try the report here: [Trial Balance Excel](https://businesscentral.dynamics.com?report=4405)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your balance. To learn more, go to:

- [Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)
- [Trial Balance (legacy)](../reports/report-6.md)
- [Financial Reporting](../bi-how-work-account-schedule.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)  
[Trial Balance (legacy)](../reports/report-6.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Power BI finance app](../finance-powerbi-app.md)  
[Financial Reporting](../bi-how-work-account-schedule.md)
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]