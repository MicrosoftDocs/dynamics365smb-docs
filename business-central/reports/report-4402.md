---
title: Aged Accounts Receivable (Excel report)
description: Analyze customer balances at the end of each period. Used as a gauge to measure the reliability of collectable debts for your customers.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_4402_Primary
ms.date: 12/13/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 12/13/2024
ai.usage: ai-assisted
---

# Aged Accounts Receivable Excel (report)

The **Aged Accounts Receivable Excel** report uses customer ledger entries to aggregate and bucket data according to the Aged as of and Period length parameters in the report's request page. Data is summarized by the two global dimensions.

The report Excel workbook contains four worksheets that you can use to analyze your aged accounts receivables:

- By period (LCY),
- By Period (FCY),
- Due by Currencies, and
- CustomerAgingData

[!INCLUDE [excel-reports-use-the-worksheets](../includes/excel-reports-use-the-worksheets.md)]

[!INCLUDE [onedrive-excel-online](../includes/onedrive-excel-online.md)]

[!INCLUDE [excel-reports-enable-content-note](../includes/excel-reports-enable-content-note.md)]

## By period (LCY) worksheet

This worksheet shows amounts in local currency by customer and with the ability to group data by a Year-Quarter-Month-Day hierarchy on the due date.

With filters and slicers, you can zoom into a single customer or a group of customers.

:::image type="content" source="../media/finance/excel-aged-accounts-receivable-By-period-(LCY).png" alt-text="Screenshot of the By period (LCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## By Period (FCY) worksheet

This worksheet shows amounts in foreign currency (FCY) by customer and with the ability to group data by a Year-Quarter-Month-Day hierarchy on the due date.

With filters and slicers, you can zoom into a single customer or a group of customers. You can also filter by one or more currency codes, if needed.

:::image type="content" source="../media/finance/excel-aged-accounts-receivable-By-period-(FCY).png" alt-text="Screenshot of the By period (FCY) worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## Due by Currencies worksheet

This worksheet shows amounts by currency code and with the ability to group data by a Year-Quarter-Month-Day hierarchy on the due date.

With filters and slicers, you can zoom into a single customer or a group of customers. You can also filter by one or more currency codes, if needed.

:::image type="content" source="../media/finance/excel-aged-accounts-receivable-Due-by-Currencies.png" alt-text="Screenshot of the Due by Currencies worksheet":::

[!INCLUDE [excel-pivottable-tip](../includes/excel-pivottable-tip.md)]

## CustomerAgingData worksheet

[!INCLUDE [excel-reports-data-worksheet](../includes/excel-reports-data-worksheet.md)]

:::image type="content" source="../media/finance/excel-aged-accounts-receivable-CustomerAgingData.png" alt-text="Screenshot of the CustomerAgingData worksheet":::

[!INCLUDE [excel-reports-get-started-with-copilot-excel](../includes/excel-reports-get-started-with-copilot-excel.md)]

## Other worksheets

[!INCLUDE [excel-reports-other-worksheets](../includes/excel-reports-other-worksheets.md)]

## Use cases

[!INCLUDE [report-4402-scenario](../includes/report-4402-scenario-include.md)]

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with accounts receivables / collection management.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Aged Accounts Receivables

## Report description
Shows the amount outstanding with customers broken down into time intervals for the overdue time. The report also displays the part of the customers' balance that isn't due and can be shown with or without document details for each customer. This report is the main report for reconciling customer ledger to G/L. Assuming you don't allow direct posting to the accounts used in the customer posting groups' receivables account, this report is a specification of the amounts you find in the G/L.

### What the report does
Shows the amount of outstanding invoices, credit memos and payments for customers.

You can configure report aging to generate three equal length periods as of the specified date (i.e. three preceding months from the end of the current month). The customer's outstanding balance is then calculated for each period, as well as any balances due before or after the three periods. 

Each period can be named from the actual start/end dates, or the total number of days included (i.e. 1 - 31 days).

A total percentage of outstanding amounts are calculated for each date range, to help you easily identify the current state of collectable customer debts.

The report can either show a summed balance for each customer, or a detailed breakdown of each outstanding document for analysis.

### Use cases
Analyse customer balances at the end of each period. Used as a gauge to measure the reliability of collectable debts for your customers.
Allows easy reconciliation of the customer subledger against the receivables account(s) in the general ledger, assuming that direct posting is disabled. 
This report helps businesses manage and analyze their accounts receivable by providing a clear view of which invoices are overdue and by how long. It's particularly useful for credit and collections teams to prioritize follow-ups and improve cash flow management.

Please include your data sources and URLs

-->

Accounts receivable professionals use the report to:

- Reconcile customer subledgers against the receivables accounts in the general ledger and ensure that all outstanding balances are accurate and complete.
- Identify discrepancies or errors in customer transactions and investigate them.
- Get data to prepare financial statements, such as income statements or balance sheets.

Collections specialists use the report to:

- Identify overdue customer accounts and prioritize follow-up activities based on how overdue the payments are
- Analyze customer payment history to identify patterns or trends in late payments and proactively address issues.
- Prepare collection reports or dashboards for internal or external stakeholders.

Credit analysts use the report to:

- Analyze customer payment history to make recommendations for credit limits or payment terms.
- Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
- Get data to prepare financial reports for stakeholders such as investors or executives.

## Try the report

Try the report here: [Aged Accounts Receivable Excel](https://businesscentral.dynamics.com?report=4402)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Make the report your own

[!INCLUDE [excel-reports-make-it-your-own](../includes/excel-reports-make-it-your-own.md)]

## Alternative reports

There are several other ways to analyze your aged accounts receivables. To learn more, go to:

- [Aged Receivables (Back Dating) in Power BI](../finance-powerbi-aged-receivables-back-dating.md)
- [Using data analysis to analyze accounts receivable](../ad-hoc-analysis-finance.md#example-finance-accounts-receivable)

## Contributors

[!INCLUDE [contributor_credit](../includes/contributor_credit.md)]

- [Kim Dallefeld](https://www.linkedin.com/in/kim-dallefeld/) | Microsoft MVP

## Related information

[Accounts receivable report overview](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]