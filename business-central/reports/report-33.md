---
title: Reconcile Cust. and Vend. Accs (report)
description: Understand the transactions for control general ledger (G/L) accounts, and highlight any discrepancies between G/L and customer/vendor ledgers.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: Report_33_Primary
ms.date: 10/18/2024
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 10/18/2024
ai.usage: ai-assisted
---

# Reconcile Cust. and Vend. Accs (report)

The *Reconcile Cust. and Vend. Accs* report shows a list of all control general ledger (G/L) accounts defined on customer posting group, vendor posting group and currency tables. 

Total net change is calculated for both the general ledger as well as customer/vendor ledgers in the given date period. Any differences between the two are highlighted.

Customer and vendor ledger entries are separated by posting group and type to allow for easy identification of errors and to assist with corrections.

Realised foreign exchange gains and losses are also totalled in the (G/L), and compared to the gains/losses posted against customer/vendor ledgers by currency. 


## Use cases

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with core finance.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 
Do not start lines with ""Use the data to""

## Report name
Reconcile Cust. and Vend. Accs

## Report description
Shows the G/L entries resulting from posting customer and vendor entries split per G/L account and posting groups. Use this report to reconcile the balances on customer and vendor ledgers to general ledger balances.

### What the report does
The *Reconcile Cust. and Vend. Accs* report shows a list of all control general ledger (G/L) accounts defined on customer posting group, vendor posting group and currency tables. 
Total net change is calculated for both the general ledger as well as customer/vendor ledgers in the given date period. Any differences between the two are highlighted.
Customer and vendor ledger entries are separated by posting group and type to allow for easy identification of errors and to assist with corrections.
Realised foreign exchange gains and losses are also totalled in the (G/L), and compared to the gains/losses posted against customer/vendor ledgers by currency. 

### Use cases
Understand the transactions for control G/L accounts, and highlight any discrepancies between G/L and customer/vendor ledgers.
Understand the transactions for control general ledger (G/L) accounts, and highlight any discrepancies between G/L and customer/vendor ledgers.
This report helps ensure that all transactions involving customers and vendors are accurately reflected in the general ledger, providing a clear and accurate financial picture.


Please include your data sources and URLs

-->

As an accounts payable clerk, use the report to:
* Reconcile vendor accounts to ensure that all vendor transactions have been correctly recorded in the general ledger
* Identify any discrepancies or errors in vendor transactions and investigate further as necessary
* Prepare vendor account statements based on the data obtained from the report

As an accounts receivable clerk, use the report to:
* Reconcile customer accounts to ensure that all customer transactions have been correctly recorded in the general ledger
* Identify any discrepancies or errors in customer transactions and investigate further as necessary
* Prepare customer account statements based on the data obtained from the report

As a financial accountant, use the report to:
* Verify the accuracy of the financial data by ensuring that the balances on customer and vendor ledgers reconcile to the general ledger balances
* Identify any discrepancies or errors in financial data and investigate further as necessary
* Prepare financial statements, such as income statements, balance sheets, and cash flow statements, based on the data obtained from the report


## Try the report

Try the report here: [Reconcile Cust. and Vend. Accs](https://businesscentral.dynamics.com?report=33)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]


## See also

[Built-in key finance reports](../finance-reports.md)  
[Ad-hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]