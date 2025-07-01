---
title: Analyze G/L entries
description: Describes how to analyze data in your general ledger either on transactional level or on the detailed level.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: postpone
ms.search.form: 20, 116_Primary
ms.date: 02/12/2025
ms.service: dynamics-365-business-central
---

# Analyze general ledger (G/L) transactions

When a transaction is posted to the general ledger, the following data is stored in the [!INCLUDE[prod_short](includes/prod_short.md)] database: a single row in the G/L register table and one or more rows in the G/L Entry table.

## Analyzing the G/L register

You can use the G/L Registers page for financial reporting and transaction tracking. The page gives you an overview of all transactions to the general ledger with the ability to navigate to related entries in subledgers, such as VAT entries or Customer Ledger Entries. You can also see which type of transaction that occured, the user who did the transaction and when it was recorded in the database.

The G/L Registers page is particularly useful during audits, as it provides auditors with easy access to related detailed transaction information. It helps identify any discrepancies, errors, or unusual entries that may require further investigation. 

## Example: use analysis mode to get an overview of G/L transaction types and volume

[!INCLUDE [gl-register-analysis-example](includes/gl-register-analysis-example.md)]


## Analyzing general ledger (G/L) entries

Depending on your need for details or aggregation when analyzing general ledger (G/L) entries, you have several options:

- use the G/L entries page in analysis mode. To learn more, go to [Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md)  
- use the Chart of Accounts page to get a summary across all your G/L accounts. To learn more, go to [Analyze finance data from the Chart of Accounts](finance-general-ledger.md).
- run or define a financial report. To learn more, go to [Primary capabilities of financial reporting](finance-financial-reporting-capabilities.md).

## See also

[Understand the general ledger](finance-general-ledger.md)  
[Understand the chart of accounts](finance-chart-of-accounts.md)  
[Ad-hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Financial analytics overview](bi.md)   
[Finance overview](finance.md)   

[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
