---
title: Overview of Tasks to Manage Receivables | Microsoft Docs
description: Outlines tasks to manage receivables and apply payments to customer or vendor ledger entries.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customer payment, debtor, balance due, AR
ms.date: 04/30/2018
ms.author: sgroespe

---
# Managing Receivables
A regular step in any financial rhythm is to reconcile bank accounts, which requires that you apply incoming payments to customer or vendor ledger entries to close sales invoices and purchase credit memos as paid.

While most customers in B2B environments pay some time after delivery, leaving the posted sales invoices open for the Accounts Receivable department to close (apply) when payment is received, some sales invoices can be paid immediately, for example with PayPal. Such invoices are immediately applied as paid when they are posted and, therefore, do not appear as payments to be processes in AR. For more information, see, for example, [Invoice Sales](sales-how-invoice-sales.md).  

In [!INCLUDE[d365fin](includes/d365fin_md.md)], one of the fastest ways to register payments from the **Payment Reconciliation Journal** window by importing a bank statement file or feed. The payments are applied to open customer or vendor ledger entries based on data matches between payment text and entry information. You can review and change the matches before you post the journal, and close bank account ledger entries for ledger entries when you post the journal. The bank account is reconciled when all payments are applied.

Other windows exist where you can either apply payments or reconcile bank accounts:

* The **Bank Account Reconciliations** window, where you reconcile bank accounts by matching imported bank statement lines with your system bank account ledger entries. Here, you can also reconcile check payments. For more information, see [Reconcile Bank Accounts Separately](bank-how-reconcile-bank-accounts-separately.md). Here, you cannot apply payments.
* The **Payment Registration** window, where you can manually apply payments received as cash, check, or bank transaction against a generated list of unpaid sales documents. Note that this functionality is available only for sales documents. Here, you cannot apply outgoing payments, and you cannot reconcile bank accounts.
* The **Cash Receipt Journal** window, where you manually post receipts to the relevant general ledger, customer, or other account by entering a payment line. You can either apply the receipt or refund to one or more open entries before you post the cash receipt journal, or from the customer ledger entries. Here, you cannot reconcile bank accounts.  

Another part of managing receivables is to collect outstanding balances, including finance charges, and issue reminders. [!INCLUDE[d365fin](includes/d365fin_md.md)] offers ways to do those things as well. For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).  

The following table describes a sequence of tasks, with links to the topics that describe them.  

| To | See |
| --- | --- |
| Apply payments to open customer or vendor ledger entries based on an imported bank statement file or feed, and reconcile the bank account when all payments are applied. |[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Apply payments to open customer ledger entries based on manual entry in a list of unpaid sales documents. |[Reconcile Customer Payments Manually From a List of Unpaid Sales Documents](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md) |
| Post cash receipts or refunds for customers in the cash receipt journal and apply to customer ledger entries, either from the journal or from posted ledger entries. |[Reconcile Customer Payments Manually](receivables-how-apply-sales-transactions-manually.md) |
| Remind customers of overdue amounts, calculate interest and finance charges, and manage accounts receivable. |[Collect Outstanding Balances](receivables-collect-outstanding-balances.md) |
|Ensure that you know the cost of shipped items by assigning added item costs, such as freight, physical handling, insurance, and transportation that you incur after selling.|[Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md)|
|Set up a tolerance by which the system closes an invoice even though the payment, including any discount, does not fully cover the amount on the invoice.|[Work with Payment Tolerances and Payment Discount Tolerances](finance-payment-tolerance-and-payment-discount-tolerance.md)|
## See Also
[Sales](sales-manage-sales.md)  
[Managing Payables](payables-manage-payables.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
## [!INCLUDE[d365fin](includes/training_link_md.md)]
