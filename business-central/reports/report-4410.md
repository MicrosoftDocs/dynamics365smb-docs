---
title: Consolidated Trial Balance (Excel Report)
description: Use Excel to view a snapshot of your consolidated chart of accounts at a given point to check the net change and closing balance.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_4410_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 12/13/2024
ai-usage: ai-assisted
---

# Consolidated Trial Balance Excel (report)

The **Consolidated Trial Balance Excel** report shows the net change or balances of general ledger accounts for a selected period, aggregated for each business unit.

Run it in the consolidation company after consolidating the entries you want to review. Enter an **Ending Date** and, optionally, a **Starting Date**. At least one business unit must exist. The report reads the current company's G/L entries and groups amounts by business unit and the two global dimensions. It doesn't perform consolidation or show separate debit and credit columns.

The Excel workbook contains worksheets that you can use to analyze your trial balance:

- Consolidated Trial Bal. (Print)
- Trial Balance (LCY)
- By Business Unit (LCY)
- Trial Balance (ACY)
- By Business Unit (ACY)
- TrialBalanceData, hidden by default

The **Consolidated Trial Bal. (Print)** worksheet provides a printable view.

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

Filters and slicers let you zoom in on the balance as seen from business units, global dimensions, or by account categories and subcategories.

## Trial balance (LCY) worksheet

This worksheet shows the trial balance for the consolidation company with amounts in local currency (LCY).

:::image type="content" source="../media/excel-Consolidated-Trial-Balance-Trial-Balance-LCY.png" alt-text="Screenshot of the Trial Balance (LCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## By business unit (LCY) worksheet

This worksheet shows the trial balance for the consolidation company with amounts in LCY for your business units.

:::image type="content" source="../media/excel-Consolidated-Trial-Balance-By-Business-Unit-LCY.png" alt-text="Screenshot of the By Business Unit (LCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Trial balance (ACY) worksheet

This worksheet shows the trial balance for the consolidation company with amounts in additional reporting currency (ACY). The report requires that you use ACY. If you don't use ACY, the report doesn't show data.

:::image type="content" source="../media/excel-Consolidated-Trial-Balance-Trial-Balance-ACY.png" alt-text="Screenshot of the Trial Balance (ACY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## By business unit (ACY) worksheet

This worksheet shows the trial balance for the consolidation company with amounts in ACY for your business units.

:::image type="content" source="../media/excel-Consolidated-Trial-Balance-By-Business-Unit-ACY.png" alt-text="Screenshot of the By Business Unit (ACY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## TrialBalanceData data worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/excel-Consolidated-Trial-Balance-TrialBalanceData.png" alt-text="Screenshot of the TrialBalanceData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets in the workbook

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4410-scenario](../includes/report-4410-scenario-include.md)]

## Try the report

Try the report here: [Consolidated Trial Balance Excel](https://businesscentral.dynamics.com?report=4410)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your balance. Learn more in the following articles:

- [Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)
- [Income Statement (Power BI)](../finance-powerbi-income-statement.md)
- [Financial Reporting](../bi-how-work-account-schedule.md)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP
- [Steve Chinsky ](https://www.linkedin.com/in/steve-chinsky-321a20/) | Microsoft MVP
- [Rob Delprado](https://www.linkedin.com/in/robb-delprado/) | Microsoft MVP

## Related information

[Set Up Company Consolidation](../finance-consolidated-company-reporting-setup.md)   
[Balance Sheet (Power BI)](../finance-powerbi-balance-sheet.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Power BI finance app](../finance-powerbi-app.md)  
[Financial Reporting](../bi-how-work-account-schedule.md)
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]