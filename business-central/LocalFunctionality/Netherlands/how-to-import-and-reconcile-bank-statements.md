---
title: How to import and reconcile bank statements
description: Banks offer electronic statements detailing all your financial transactions. These statements can be imported into the bank or giro journals.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: giro journals, bank journals, Dutch version, Netherlands, electronic statements, import bank statements
ms.date: 03/17/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Import and reconcile bank statements

Banks provide electronic bank statements for all your financial interactions. You can import these statements into the bank or giro journals.  

The import bank statement is supported by the following protocols:  

- Rabobank mut.asc  
- Rabobank vvmut.ac  
- Rabobank ASCII  
- SEPA CAMT  

## Import and reconcile bank statements  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank/Giro Journal**, and then choose the related link.  
1. Choose the **Import Bank Statement** action, select the required import protocol, and then choose the **OK** button.  
1. To reconcile the bank statements automatically when importing, on the **Options** FastTab, select the **Automatic Reconciliation** checkbox.  

   > [!NOTE]  
   > This function doesn't work for bank statement files of type SEPA CAMT. Instead, use the **Match Automatically** action on the **Bank Acc. Reconciliation** page. Learn more in [Reconcile Bank Accounts](../../bank-how-reconcile-bank-accounts-separately.md).  

1. Choose the **OK** button.  
1. To import the file that contains the electronic bank statement, specify the file name and path, and then choose the **Open** button.  

The electronic bank statement is imported into the bank or giro journals. Learn more in [Dutch Electronic Banking](dutch-electronic-banking.md).  

## Related information

- [Dutch Electronic Banking](dutch-electronic-banking.md)   
- [Applying Payments Automatically and Reconciling Bank Accounts](../../receivables-apply-payments-auto-reconcile-bank-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
