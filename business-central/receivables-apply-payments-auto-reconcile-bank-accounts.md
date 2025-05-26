---
title: Reconcile bank accounts and apply payments
description: Outlines tasks to reconcile your bank, receivables, and payables accounts, post cash receipts or expenses, and apply payments automatically.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.search.form: 1290, 1291, 1293, 1294
ms.date: 07/25/2024
ms.service: dynamics-365-business-central
---

# Apply payments automatically and reconciling bank accounts
You must regularly reconcile your bank, receivables, and payables accounts by applying payments recorded in the bank to their related open (unpaid) invoices and credit memos or other open entries in [!INCLUDE[prod_short](includes/prod_short.md)].  

You can perform this task on the **Payment Reconciliation Journal** page, for example, by importing a bank statement file or feed to quickly register the payments. Payments are applied to open customer or vendor ledger entries based on matches between payment text and entry information. You can review and change automatic applications before you post the journal. You can choose to close any open bank account ledger entries related to the applied ledger entries when you post the journal. The bank account is automatically reconciled when all payments are applied.

On the **Payment Application Rules** page, you can set up prioritized rules that govern how payment text is automatically matched with entry information.

You can also reconcile bank accounts without simultaneously applying payments. You perform this work on the **Bank Acc. Reconciliation** page. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).

To import bank statements as a bank feed, you must first set up and enable the Envestnet Yodlee Bank Feed service, and then link your bank accounts to the related online bank accounts. For more information, see [set up the Envestnet Yodlee bank feeds service](bank-how-setup-bank-statement-service.md).  

> [!TIP]
> You can also import bank statement files in comma or semicolon delimited format (.CSV). Use the **Set up a bank statement file format** assisted setup to define bank statement import formats and attach the format to a bank account. You can then use these formats when you import bank statements in the **Bank Account Reconciliation** page.

Alternatively, you can use the AMC Banking 365 Fundamentals extension to convert a bank statement file, from any format, to a data stream that you can import into [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [use the AMC banking 365 fundamentals extension](ui-extensions-amc-banking.md).  

The following table describes a sequence of tasks, with links to the articles that describe them.  

| To | See |
| --- | --- |
| Apply payments to open customer or vendor ledger entries by importing a bank statement, and then reconcile the bank account after you apply all payments. |[Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md) |
| Manually apply payments by viewing detailed information about matched data and suggestions for candidate open entries to apply payments to. |[Review or Apply Payments After Automatic Application](receivables-how-review-apply-payments-auto-application.md) |
| Resolve payments that can't be applied automatically to their related open ledger entries. For example because the amounts differ, or because a related ledger entry doesn't exist. |[Reconcile Payments that Can't be Applied Automatically](receivables-how-reconcile-payments-cannot-apply-auto.md) |
| Link text on payments to specific customer, vendor, or general ledger accounts to always post recurring cash receipts or expenses to those accounts when no documents exist to apply to. |[Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md) |
|Set up the rules to govern how payments/bank transactions should be automatically applied to their related open ledger entries when you use the **Apply Automatically** function on the **Payment Reconciliation Journal** page.|[Set Up Rules for Automatic Application of Payments](receivables-how-set-up-payment-application-rules.md)|

## Related information
[Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
