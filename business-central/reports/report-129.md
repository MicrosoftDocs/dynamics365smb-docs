---
title: Customer - Trial Balance (report)
description: Analyze and reconcile your customer balances at the end of the period by viewing the opening balance, each transaction within the period, and the closing balance grouped by customer.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_129_Primary
ms.date: 10/03/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Customer - Trial Balance (report)

The **Customer - Trial Balance** report shows balance details for selected customers.

If you specify a date range in the date filter, the report displays the following details for each customer:

* Beginning balance
* Transactions in the period and their remaining amount and due date
* Ending balance

You can run the report in either your local currency or the customer's currency. You can exclude customers that didn't have transactions in the period.

> [!TIP]
> If you need a more detailed version of this type of report, use the **Customer Detail Trial Balance** (104) report.

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
Customer - Trial Balance

## Report description
Shows a detail balance for selected customers. You can use the report to verify that the balance for a customer posting group is equal to the balance on the corresponding G/L account on a certain date. Use the report at the close of an accounting period or fiscal year, for example. 

### What the report does
You can specify a date range in the date filter and for each customer the report will display the beginning balance, each transaction within the period, with its remaining amount and due date, and the ending balance. 

You can choose to run the report in your local currency or in the customer's currency. Customers that have not had any transactions for the period can also be excluded.

### Use cases
Analyse and reconcile your customer balances at the end of the period by seeing the opening balance, each transaction within the period and the closing balance grouped by customer.

Please include your data sources and URLs
-->

Sales representatives use the report to:

* Follow up on pending payments by tracking outstanding balances for customers.
* Verify that customer balances are accurate before making sales decisions or recommendations.
* Identify opportunities to up-sell or cross-sell, based on customer transaction history.

Sales managers use the report to:

* Monitor the financial health of key accounts by reviewing their balances and transaction history.
* Analyze the effect of recent sales transactions on customer accounts and identify trends and areas for improvement.
* Ensure that customer balances are accurate before making strategic decisions.

Finance analysts use the report to:

* Reconcile customer balances with the general ledger and ensure accurate financial records.
* Analyze transaction patterns and identify potential financial risks or opportunities.
* Serve as a source for financial forecasting and planning.

Accounts receivable specialists use the report to:

* Monitor past-due balances, follow up on overdue payments, and minimize the risk of bad debts.
* Identify accounts with high outstanding balances and prioritize collection efforts.
* Provide customers with accurate account information upon request.

Finance managers use the report to:

* Monitor the performance of the accounts receivable department by reviewing key metrics, such as the average collection period and bad debt ratio.
* Identify trends and patterns in customer payment behavior to inform credit policies and collection strategies.
* Ensure compliance with accounting standards and regulations by reconciling customer balances with the general ledger and audit trails.

## Try the report

Try the report here: [Customer - Trial Balance](https://businesscentral.dynamics.com?report=129)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Sales reports](../sales-reports.md)  
[Ad hoc analysis of sales data](../ad-hoc-analysis-sales.md)  
[Sales analytics overview](../sales-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
