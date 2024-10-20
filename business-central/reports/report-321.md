---
title: Vendor - Balance to Date (report)
description: Keep track of your outstanding payables and manage your vendor relationships.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_321_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Vendor - Balance to Date (report)

The *Vendor - Balance to Date* report shows the vendor balance by the ending date of the specified date range. 

You can choose to display the vendor balance in your local currency (LCY). 

Select the **Include Unapplied Entries** field to show entries that were closed by the ending date but were unapplied (opened) at a later date. 

Select the **Show Entries with Zero Balance** to show vendors with a balance of zero by the ending date of the date filter. The date filter applies to the detailed vendor ledger entries for the entries in the report. If a payment was made after the ending date, and the payment was applied to invoices within the date range, the report includes the invoice. 

The report includes the invoice because it wasn't closed before the ending date.


## Use cases

[!INCLUDE[report-321-scenario](../includes/report-321-scenario-include.md)]

<!-- 
Prompt
Below is a report in an ERP system. Provide 3-4 use cases for different personas working with accounts payable or procurement .

Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 

## Report name
Vendor - Balance to Date

## Report description
The *Vendor - Balance to Date* report shows the vendor balance by the ending date of the specified date range. 
You can choose to display the vendor balance in your local currency (LCY). 
Select the **Include Unapplied Entries** field to show entries that were closed by the ending date but were unapplied (opened) at a later date. 
Select the **Show Entries with Zero Balance** to show vendors with a balance of zero by the ending date of the date filter. The date filter applies to the detailed vendor ledger entries for the entries in the report. If a payment was made after the ending date, and the payment was applied to invoices within the date range, the report includes the invoice. 
The report includes the invoice because it wasn't closed before the ending date.

## Use cases
This report helps businesses keep track of their outstanding payables and manage their vendor relationships effectively.

Please include your data sources and URLs

 -->

As an accounts payable clerk, use the report to:
* Reconcile vendor sub-ledgers against the payables account(s) in the general ledger to ensure that all outstanding balances are accounted for accurately and completely
* Identify any discrepancies or errors in vendor transactions and investigate further as necessary
* Prepare financial statements, such as income statements or balance sheets, based on the data obtained from the report

As a procurement officer, use the report to:
* Monitor vendor balances and payment history to ensure that all vendor transactions are accounted for accurately and completely
* Help negotiate payment terms and discounts with vendors to optimize cost savings and improve financial performance
* Prepare financial reports for stakeholders, such as investors or executives based on the data obtained from the report

As a financial analyst, use the report to:
* Analyze vendor payment history to identify patterns or trends in late payments or missed payments and proactively address potential issues
* Help identify areas for cost savings or revenue generation and make recommendations for improving financial performance
* Prepare financial reports for stakeholders, such as investors or executives based on the data obtained from the report


## Try the report

Try the report here: [Vendor - Balance to Date](https://businesscentral.dynamics.com?report=321)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]


## See also

[Accounts receivable report overview](../receivables-reports.md)  
[Key finance report overview](../finance-reports.md)  
[Ad-hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]