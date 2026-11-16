---
title: Customer - Balance to Date (Report)
description: Review customer balances and supporting entries at a historical ending date, with options for currency, unapplied entries, and zero balances.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_121_Primary
ms.date: 11/13/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
ai-seo-date: 10/07/2024
ai-usage: ai-assisted
---

# Customer - Balance to date (report)

The **Customer - Balance to date** report shows the open customer ledger entries until the ending date.

This report shows similar content to the customer statement, but it doesn't indicate whether the entry is overdue.

> [!NOTE]
> The date filter applies to the detailed customer ledger entries. You might have payments that are later than the ending date, but that are applied to invoices within the date range. Those invoices appear in the report because they weren't closed by the ending date.

Enter **Ending Date** to calculate historical remaining amounts. You can show amounts in local currency, include unapplied entries, show entries with zero balance, or start a new page per customer. Use an aged receivables report if you need overdue or aging information.

## Use cases

[!INCLUDE [report-121-scenario](../includes/report-121-scenario-include.md)]

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with sales.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Customer - Balance to date

### What the report shows
The *Customer - Balance to date* report shows the open customer ledger entries until the ending date. 

This report shows similar content as the customer statement but with no indication if the entry is overdue. 

**Note:** The date filter is applied to the detailed customer ledger entries. You might have payments later than the ending date but are applied to invoices within the date range. Those invoices appear in the report because they weren't closed as per the ending date.

### Use cases
Accounting Period Closure: It helps verify that the balance for a customer posting group matches the balance on the corresponding General Ledger (G/L) account at the end of an accounting period or fiscal year.
Manage and review outstanding balances owed by customers, ensuring accurate and up-to-date records.
Analyze your accounts receivable and overall financial health.
Generate customer statements, providing a clear summary of amounts due, which can be shared with customers for payment follow-ups.

add examples as seen from account receivables and finance perspective

Please include your data sources and URLs
-->

Sales representatives use the report to:

* Review the balances that customers owed at the ending date.
* Identify the customers with the highest outstanding balances and follow up to help collection efforts.

Sales managers use the report to:

* Review balances for selected customer accounts at period end.
* Identify larger balances that need further investigation.

Accounts receivable specialists use the report to:

* Review entries and applications that make up a balance at the ending date.
* Investigate differences between historical balances and current balances.
* Support reconciliation of receivables at period end.

Finance managers use the report to:

* Review total receivables as of an accounting period or fiscal year end.
* Monitor the cash flow and liquidity of the company by reviewing the accounts receivable balance.
* Compare historical balances with other financial reports for the same ending date.

## Try the report

Try the report here: [Customer - Balance to date](https://businesscentral.dynamics.com?report=121)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
