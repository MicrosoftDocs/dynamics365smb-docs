---
title: Aged Accounts Payable (report)
description: Analyze vendor balances at the end of each period. Use this report to monitor unpaid invoices and prioritize payments for overdue accounts.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_322_Primary
ms.date: 12/16/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Aged Accounts Payable (report)

The **Aged Accounts Payable** report shows the amounts on outstanding invoices, credit memos, and payments for vendors.

You can configure report aging to generate three periods of equal length as of a specified date (for example, the three preceding months from the end of the current month). The vendor's outstanding balance is calculated for each period, as are balances due before or after the three periods. You can name each period based on either the actual start and end dates, or the total number of days included (for example, 1–31 days).

To help you easily identify the company's current financial health, total percentages of outstanding amounts are calculated for each date range.

The report can show either a summed balance for each vendor or a detailed breakdown of each outstanding document.

## Use cases

[!INCLUDE[report-322-scenario](../includes/report-322-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Shows overdue balances for vendors in time intervals. The overdue amounts can show by due date, posting date, or by document date. You can choose to show the amounts in local currency (LCY) and print details of the overdue documents. The time intervals can have headings with dates or with number of dates overdue, relative to the specified aging by type.
This report is the main report for reconciling vendor ledger to G/L. Assuming that you don't post directly to the payables account for the vendor posting group, this report is a specification of the amounts in the general ledger.

### What the report does
Shows the amount of outstanding invoices, credit memos and payments for vendors.

You can configure report aging to generate three equal length periods as of the specified date (i.e. three preceding months from the end of the current month). The vendor's outstanding balance is then calculated for each period, as well as any balances due before or after the three periods. 

Each period can be named from the actual start/end dates, or the total number of days included (i.e. 1 - 31 days).

A total percentage of outstanding amounts are calculated for each date range, to help you easily identify the company's current financial health.

The report can either show a summed balance for each vendor, or a detailed breakdown of each outstanding document for analysis.

### Use cases
Analyse vendor balances at the end of each period. Used to monitor unpaid invoices, and prioritise payments for overdue accounts. 

Allows easy reconciliation of the vendor subledger against the payables account(s) in the general ledger, assuming that direct posting is disabled. 

Please include your data sources and URLs
 -->

Procurement specialists use the report to:

* Monitor vendor payments. The report provides a detailed breakdown of each outstanding document for analysis. Use this information to monitor vendor payments and ensure timely payment of outstanding invoices.

Vendor managers use the report to:

* Monitor vendor performance. The report provides information about outstanding balances for each vendor. Use this information to monitor vendor performance and identify any potential issues that might affect the organization's procurement processes.

Accounts payable specialists use the report to:

* Reconcile vendor subledgers. The report is used to reconcile the vendor subledger against the payables accounts in the general ledger, provided that direct posting is disabled. Use this information to ensure accurate and timely financial reporting.

Controllers use the report to:

* Analyze financial health. The report calculates the total percentage of outstanding amounts for each date range, making it easy to identify the company's current financial health. Use this information to analyze the company's financial position and make informed decisions.

## Try the report

Try the report here: [Aged Accounts Payable](https://businesscentral.dynamics.com?report=322)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Alternative reports

There are several other ways to analyze aged accounts payable. To learn more, go to:

* [Aged Payables (Back Dating) in Power BI](../finance-powerbi-aged-payables-back-dating.md)
* [Using data analysis to analyze accounts payable](../ad-hoc-analysis-finance.md#example-finance-accounts-payable)
* [Aged Accounts Payable Excel](../reports/report-4403.md)

## Related information

[Aged Payables (Back Dating) in Power BI](../finance-powerbi-aged-payables-back-dating.md)  
[Using data analysis to analyze accounts payable](../ad-hoc-analysis-finance.md#example-finance-accounts-payable)  
[Aged Accounts Payable Excel](../reports/report-4403.md)  
[Purchase reports](../purchase-reports.md)  
[Ad hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)  
[Purchasing analytics overview](../purchasing-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
