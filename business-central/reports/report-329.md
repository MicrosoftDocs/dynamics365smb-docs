---
title: Vendor - Trial Balance (report)
description: Analyze the closing balance of vendors at the end of the period and reconcile the vendor subledger against the payables accounts in the general ledger.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_329_Primary
ms.date: 10/14/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/07/2024
ai.usage: ai-assisted
---

# Vendor - Trial Balance (report)

The **Vendor - Trial Balance** report shows the beginning balance and net change for the mandatory date range that you select in the date filter.

If you use accounting periods, the report shows the fiscal year amounts for the beginning balance, net change, and ending balance.

The report is segmented for vendors in each vendor posting group. The grouping makes it easier to reconcile the ending balance against the general ledger payables accounts.

## Use cases

[!INCLUDE[report-329-scenario](../includes/report-329-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with procurement.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report description
Shows the net changes for vendors for the period specified in the date filter, and the net change year-to-date for the corresponding fiscal year. The report is grouped by vendor posting groups and gives a different view of the vendor ledger than the Aged Accounts Payable report. Note: If you don't set up accounting periods, Business Central doesn't know which fiscal year to use. It shows the year-to-date from the most recent fiscal year, or just the selected period. The date might not be from the beginning of a year.

### What the report does
You must specify a date range in the date filter and the report will display the beginning balance and net change for the date range selected. Using the accounting periods the report will show the fiscal year amounts for beginning balance, net change and ending balance.

The report is segmented for vendors in each vendor posting group for easy reconciliation of the ending balance against the general ledger payables account(s).

### Use cases
Analyse the closing balance of vendors at the end of the period to reconcile the vendor subledger against the payables account(s) in the general ledger.

Please include your data sources and URLs
 -->

Procurement managers use the report to:

* Analyze vendor balances. The report displays the net changes for vendors for the period specified in the date filter. It also shows the year-to-date net change for the corresponding fiscal year. Use this information to analyze vendor balances and ensure that the company isn't overpaying or underpaying vendors.

Vendor managers use the report to:

* Review vendor posting group balances. The report has groups for vendor posting groups, making it easy to review vendor posting group balances. Use this information to ensure that vendors are appropriately categorized and managed.

Accounts payable specialists use the report to:

* Reconcile vendor subledgers. The report is segmented for vendors in each vendor posting group, making it easy to reconcile the ending balance against the general ledger payables accounts. Use this information to ensure accurate and timely financial reporting.

Controllers use the report to:

* Monitor vendor performance. The report provides information about net changes for vendors for the period specified in the date filter. It also shows the year-to-date net change for the corresponding fiscal year. Use this information to monitor vendor performance and identify potential issues that might affect the procurement processes.

## Try the report

Try the report here: [Vendor - Trial Balance](https://businesscentral.dynamics.com?report=329)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Purchase reports](../purchase-reports.md)  
[Ad hoc analysis of purchasing data](../ad-hoc-analysis-purchasing.md)  
[Purchasing analytics overview](../purchasing-analytics-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
