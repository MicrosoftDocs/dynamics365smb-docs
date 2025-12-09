---
title: Customer - Balance to date (report)
description: Get a detailed balance for selected customers at the close of an accounting period or fiscal year, for example.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_121_Primary
ms.date: 10/03/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Customer - Balance to date (report)

The **Customer - Balance to date** report shows the open customer ledger entries until the ending date.

This report shows similar content to the customer statement, but it doesn't indicate whether the entry is overdue.

> [!NOTE]
> The date filter applies to the detailed customer ledger entries. You might have payments that are later than the ending date, but that are applied to invoices within the date range. Those invoices appear in the report because they weren't closed by the ending date.

## Use cases

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

* Track the payment status of customers and follow up on overdue balances.
* Identify the customers with the highest outstanding balances and follow up to help collection efforts.

Sales managers use the report to:

* Monitor the performance of sales representatives in terms of collecting payments from customers.
* Identify customers that might be bad for.

Accounts receivable specialists use the report to:

* Identify customers with overdue balances and take appropriate action to collect payments.
* Review the payment history of customers and investigate discrepancies or potential issues.
* Monitor the aging of customer balances and prioritize collection efforts based on the level of delinquency.

Finance managers use the report to:

* Analyze the performance of the accounts receivable function, such as the average collection period and bad debt ratio.
* Monitor the cash flow and liquidity of the company by reviewing the accounts receivable balance.
* Review the customer aging report to identify trends and potential risks to the company's financial health.

## Try the report

Try the report here: [Customer - Balance to date](https://businesscentral.dynamics.com?report=121)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
