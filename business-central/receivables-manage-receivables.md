---
title: Overview of tasks to manage receivables
description: This article outlines tasks to manage receivables and apply payments to customer or vendor ledger entries.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: customer payment, debtor, balance due, AR
ms.date: 07/08/2024
ms.service: dynamics-365-business-central

---
# Managing receivables

A regular step in any financial rhythm is to reconcile bank accounts. To close sales invoices and purchase credit memos as paid, you apply incoming payments to customer or vendor ledger entries.

While most customers in B2B environments pay some time after delivery, leaving the posted sales invoices open for the Accounts Receivable department to close (apply) when payment is received, some sales invoices can be paid immediately, for example with PayPal. Such invoices are immediately applied as paid when they're posted and, therefore, don't appear as payments to be processes in AR. For more information, see, for example, [Invoice Sales](sales-how-invoice-sales.md).  

In [!INCLUDE[prod_short](includes/prod_short.md)], one of the fastest ways to register payments is with the **Payment Reconciliation Journal** page by importing a bank statement file or feed. The payments are applied to open customer or vendor ledger entries based on data matches between payment text and entry information. You can review and change the matches before you post the journal, and close bank account ledger entries for ledger entries when you post the journal. The bank account is reconciled when all payments are applied.

Other pages exist where you can either apply payments or reconcile bank accounts:

* The **Bank Account Reconciliations** page, where you reconcile bank accounts by matching imported bank statement lines with your system bank account ledger entries. Here, you can also reconcile check payments. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md). Here, you can't apply payments.
* The **Payment Registration** page, where you can manually apply payments received as cash, check, or bank transaction against a generated list of unpaid sales documents. This functionality is available only for sales documents. Here, you can't apply outgoing payments, and you can't reconcile bank accounts.
* The **Cash Receipt Journal** page, where you manually post receipts to the relevant general ledger, customer, or other account by entering a payment line. You can either apply the receipt or refund to one or more open entries before you post the cash receipt journal, or from the customer ledger entries. Here, you can't reconcile bank accounts.

The **Payment Reconciliation Journal** page uses automatic matching logic that you can set up on the **Payment Application Rules** page. For more information, see [Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md).  

Other aspects of managing receivables include to collect outstanding balances, including finance charges and reminders, and to set bank accounts up to allow customers' payments to be withdrawn from their account automatically.

The following table describes a sequence of tasks, with links to the articles that describe them.  

| To | See |
| --- | --- |
| Get an overview of the capabilities for analyzing receivables. | [Accounts receivable analytics](receivables-reports.md) |
| Apply payments to open customer or vendor ledger entries based on an imported bank statement file or feed. Reconcile the bank account after you apply all payments. |[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Apply payments to open customer ledger entries based on a list of unpaid sales documents on the **Payment Registration** page. |[Reconcile Customer Payments from a List of Unpaid Sales Documents](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md) |
| Post cash receipts or refunds for customers in the cash receipt journal and apply to customer ledger entries, either from the journal or from posted ledger entries. |[Reconcile Customer Payments with the Cash Receipt Journal or from Customer Ledger Entries](receivables-how-apply-sales-transactions-manually.md) |
| Remind customers of overdue amounts, calculate interest and finance charges, and manage accounts receivable. |[Collect Outstanding Balances](receivables-collect-outstanding-balances.md) |
|With your customer’s consent, collect payments directly from the customer’s bank account according, in the Euro currency only.|[Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md)|
|Block a customer from being entered on documents or from posting, for example because of insolvency.|[Block Customers](receivables-how-block-customers.md)|
|Set up a tolerance by which the system closes an invoice even though the payment, including any discount, doesn't fully cover the amount on the invoice.|[Work with Payment Tolerances and Payment Discount Tolerances](finance-payment-tolerance-and-payment-discount-tolerance.md)|
| Predict when payments will be late for sales documents. | [The Late Payment Prediction Extension](ui-extensions-late-payment-prediction.md) |

## Related information

[Accounts receivable analytics](receivables-reports.md)   
[Sales](sales-manage-sales.md)  
[Managing Payables](payables-manage-payables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
