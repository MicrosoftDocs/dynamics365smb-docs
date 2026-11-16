---
title: Customer - Trial Balance (Report)
description: Reconcile customer opening balances, debit and credit totals, and ending balances in local currency for a period and fiscal year to date.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_129_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 10/07/2024
ai-usage: ai-assisted
---

# Customer - Trial Balance (report)

The **Customer - Trial Balance** report summarizes customer balances in local currency, grouped by customer posting group.

Specify a range in **Date Filter**. For each customer, the report shows the following amounts for both the selected period and the fiscal year to date:

* Beginning balance
* Total debits and credits
* Ending balance

The report shows customer and posting-group totals, not individual transactions, remaining amounts, or due dates. The amounts are always in local currency.

> [!TIP]
> To see individual transactions and due dates, use [Customer - Detail Trial Balance (report)](report-104.md).

## Use cases

[!INCLUDE [report-129-scenario](../includes/report-129-scenario-include.md)]

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Customer - Trial Balance

## Report description
Shows a detail balance for selected customers. You can use the report to verify that the balance for a customer posting group is equal to the balance on the corresponding G/L account on a certain date. Use the report at the close of an accounting period or fiscal year, for example. 

### What the report does
You can specify a date range in the date filter and for each customer the report will display the beginning balance, each transaction within the period, with its remaining amount and due date, and the ending balance. 

You can choose to run the report in your local currency or in the customer's currency. Customers that have not had any transactions for the period can also be excluded.

### Use cases
Analyze and reconcile your customer balances at the end of the period by seeing the opening balance, each transaction within the period and the closing balance grouped by customer.

Please include your data sources and URLs
-->

Sales representatives use the report to:

* Follow up on pending payments by tracking outstanding balances for customers.
* Verify that customer balances are accurate before making sales decisions or recommendations.
* Review period debit and credit totals for selected customers.

Sales managers use the report to:

* Monitor the financial health of key accounts by reviewing their balances and transaction history.
* Analyze the effect of recent sales transactions on customer accounts and identify trends and areas for improvement.
* Ensure that customer balances are accurate before making strategic decisions.

Finance analysts use the report to:

* Reconcile customer balances with the general ledger and ensure accurate financial records.
* Analyze transaction patterns and identify potential financial risks or opportunities.
* Serve as a source for financial forecasting and planning.

Accounts receivable specialists use the report to:

* Review period-end balances by customer posting group.
* Identify accounts with high outstanding balances and prioritize collection efforts.
* Provide customers with accurate account information upon request.

Finance managers use the report to:

* Review selected-period and fiscal-year-to-date movement in receivables.
* Compare customer posting-group totals with general ledger control accounts.
* Ensure compliance with accounting standards and regulations by reconciling customer balances with the general ledger and audit trails.

## Try the report

Try the report here: [Customer - Trial Balance](https://businesscentral.dynamics.com?report=129)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]

