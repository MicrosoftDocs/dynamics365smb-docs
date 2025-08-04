---
title: Aged Accounts Receivables (report)
description: Legacy report for analyzing customer balances at the end of each period. Used as a gauge to measure the reliability of collectable debts for your customers.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_120_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Aged Accounts Receivables (report)

> [!NOTE]
> This is a legacy version of an accounts receivables aging report. We recommend you use the **Aged Accounts Receivables Excel** report instead. To learn more, go to [About *Aged Accounts Receivables Excel*](../reports/report-4402.md).

The **Aged Accounts Receivables** report shows the number of outstanding customer invoices, credit memos, and payments.

You can configure the report's aging to generate three equal length periods as of a date you specify. For example, the periods might be the three previous months from the end of the current month. The report calculates the customer's outstanding balance for each period, and balances due before or after the three periods.

> [!TIP]
> Businesses often use the start and end dates as the names for each period, or the total number of days the periods include. For example, 1 - 31 days.

To help you easily identify the current state of customer debts, the report calculates a total percentage of outstanding amounts for each period.

The report can either show a summed balance for each customer, or a detailed breakdown of each outstanding document.

## Use cases

[!INCLUDE [report-120-scenario](../includes/report-120-scenario-include.md)]

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

* Reconcile customer subledgers against the receivables accounts in the general ledger and ensure that all outstanding balances are accurate and complete.
* Identify discrepancies or errors in customer transactions and investigate them.
* Get data to prepare financial statements such as income statements or balance sheets.

Collections specialists use the report to:

* Identify overdue customer accounts and prioritize follow-up activities based on how overdue the payments are.
* Analyze customer payment history to identify patterns or trends in late payments and proactively address issues.
* Prepare collection reports or dashboards for internal or external stakeholders.

Credit analysts use the report to:

* Analyze customer payment history to make recommendations for credit limits or payment terms.
* Identify areas to save cost or generate revenue, and make recommendations for improving financial performance.
* Get data to prepare financial reports for stakeholders such as investors or executives.

## Try the report

Try the report here: [Aged Accounts Receivables](https://businesscentral.dynamics.com?report=120)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze your aged accounts receivables. To learn more, go to:

* [Aged Receivables (Back Dating) in Power BI](../finance-powerbi-aged-receivables-back-dating.md)
* [Using data analysis to analyze accounts receivable](../ad-hoc-analysis-finance.md#example-finance-accounts-receivable)
* [Aged Accounts Receivable Excel report](report-4402.md)

## Learn more

[Accounts receivable report overview](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]