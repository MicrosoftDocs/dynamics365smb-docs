---
title: Vendor - Detail Trial Balance (report)
description: Analyze and reconcile vendor balances at the end of a period.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: Report_304_Primary
ms.date: 10/14/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Vendor - Detail Trial Balance (report)

The **Vendor - Detail Trial Balance** report shows vendor balances at the end of a period. The report groups the following information by vendor:

* Opening balance
* Transactions within a given period
* Closing balance

If you specify a date range in the date filter, the report displays the following information for each vendor:

* Beginning balance
* Each transaction within the period, and its remaining amount and due date
* Ending balance

You can run the report either in your local currency or in the vendor's currency. You can also exclude vendors that didn't have transactions in the period.

## Use cases - A version (persona version)

[!INCLUDE[report-304-scenario](../includes/report-304-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.  

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names.  

## Report description  
Shows all the vendor ledger entries within the specified date filter. The report shows the vendor's beginning balances relative to the date filter.  
  
### What the report does  
You can specify a date range in the date filter and for each vendor the report will display the beginning balance, each transaction within the period, with its remaining amount and due date, and the ending balance.   
  
You can choose to run the report in your local currency or in the vendor's currency. Vendors that have not had any transactions for the period can also be excluded.  
  
### Use cases  
Analyse and reconcile your vendor balances at the end of the period by seeing the opening balance, each transaction within the period and the closing balance grouped by vendor.

Please include your data sources and URLs 
-->

Procurement specialists use the report to:

* Analyze vendor balances and transactions for a specific period.
* Identify vendors with outstanding balances and negotiate payment terms with them.
* Reconcile vendor accounts and ensure that all transactions are accurate.
* Monitor vendor performance and identify opportunities to save cost.

Accounts payable specialists use the report to:

* Reconcile vendor accounts and ensure that all invoices are paid in a timely manner.
* Identify overdue invoices and take appropriate action to resolve the issue.
* Monitor cash flow and vendor payments.

Controllers use the report to:

* Monitor cash flow and vendor payments.
* Identify vendors with high outstanding balances and take steps to reduce the amounts owed.
* Forecast cash flow and plan for vendor payments.
* Analyze vendor balances and transactions to identify opportunities to save cost.

Purchasing agents use the report to:

* Monitor vendor performance and identify opportunities to save cost.
* Analyze transaction data to identify trends and patterns in vendor behavior, such as late deliveries or price increases.
* Negotiate better terms with vendors and improve overall procurement efficiency.

## Use cases - B version (process version)

Make your procurement process efficient and cost-effective:

* Analyze vendor balances and transactions for a specific period.
* Identify vendors with outstanding balances and negotiate payment terms with them.
* Reconcile vendor accounts and ensure that all transactions are accurate.
* Monitor vendor performance and identify opportunities to save cost.

Ensure timely and accurate processing of vendor invoices in your accounts payable processes:

* Reconcile vendor accounts and ensure that all invoices are paid in a timely manner.
* Identify overdue invoices and take appropriate action to resolve the issue.
* Monitor cash flow and vendor payments.

For your financial planning and analysis:

* Monitor cash flow and vendor payments.
* Identify vendors with high outstanding balances and take steps to reduce the amounts owed.
* Forecast future cash flows and plan for vendor payments.
* Analyze vendor balances and transactions to identify opportunities to save cost.

Oversee your overall procurement strategy and vendor management:

* Monitor vendor performance and identify opportunities to save cost.
* Analyze transaction data to identify trends and patterns in vendor behavior, such as late deliveries or price increases.
* Negotiate better terms with vendors and improve overall procurement efficiency.

## Try the report

Try the report here: [Vendor - Detail Trial Balance](https://businesscentral.dynamics.com?report=304)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Purchase reports](../purchase-reports.md)  
[Ad hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)  
[Purchasing analytics overview](../purchasing-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
