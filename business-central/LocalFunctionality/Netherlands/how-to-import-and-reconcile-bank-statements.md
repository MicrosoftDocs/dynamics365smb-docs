---
title: Import and Reconcile Bank Statements
description: Banks offer electronic statements detailing all your financial transactions. These statements can be imported into the bank or giro journals.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: giro journals, bank journals, Dutch version, Netherlands, electronic statements, import bank statements
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import and reconcile bank statements

Banks provide electronic bank statements for all your financial interactions. You can import these statements into the bank or giro journals.  

The import bank statement is supported by the following protocols:  

- Rabobank mut.asc  
- Rabobank vvmut.asc
- Rabobank ASCII  
- SEPA CAMT  

## Import and reconcile bank statements  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Bank/Giro Journal**, and then choose the related link.  
1. Choose the **Import Bank Statement** action, select the required import protocol, and then choose the **OK** button.  
1. If the import report displays an **Automatic Reconciliation** option, select it to match entries during import, and then choose **OK**. For SEPA CAMT, automatic matching uses the **Automatic Reconciliation** setting on the import protocol.
1. Select the electronic bank statement file.
1. Open the imported statement and review the journal lines and any unmatched entries before posting.

The electronic bank statement is imported into the bank or giro journals. Learn more in [Dutch Electronic Banking](dutch-electronic-banking.md).  

## Related information

- [Dutch Electronic Banking](dutch-electronic-banking.md)   
- [Applying Payments Automatically and Reconciling Bank Accounts](../../receivables-apply-payments-auto-reconcile-bank-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
