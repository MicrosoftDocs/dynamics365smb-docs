---
title: Manage bank accounts
description: You must regularly reconcile bank ledger entries with the related bank transactions in your bank accounts.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: reconcile
ms.search.form: 377, 378, 165, 1284
ms.date: 07/24/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Manage and reconcile your bank accounts

A bank reconciliation should be completed at regular intervals for all your bank accounts to ensure that the company's cash records are correct. You do this by comparing and matching entries in your internal bank accounts with bank transactions at your bank, and then posting the balances to your internal bank accounts to make totals available to finance managers. Bank reconciliation is also a practical way to discover and resolve missing payments and bookkeeping errors.

You can perform the task on the **Bank Acc. Reconciliation** page where you match (reconcile) bank statement lines in the left-hand pane with your internal bank account ledger entries in the right-hand pane. Alternatively, you can perform this task on the **Payment Reconciliation Journal** page as part of processing the payments that are represented on a bank statement. On both pages, you can fill in the bank statement information by importing a file or feed and you can use automatic matching suggestions.

> [!NOTE]  
> In the North American versions, you can also perform bank reconciliation on the **Bank Rec. Worksheet** page, which is better suited for checks and deposits but does not offer import of bank statement files. To use this page instead of the **Bank Acc. Reconciliation** page, deselect the **Bank Recon. with Auto. Match** field on the **General Ledger Setup** page. For more information, see [Reconcile Bank Accounts](LocalFunctionality/UnitedStates/how-to-reconcile-bank-accounts.md) under United States Local Functionality.

Before you can manage your bank accounts within [!INCLUDE[prod_short](includes/prod_short.md)], you must set up each bank account as a bank account card. In addition, you must set up electronic services that you may use for bank statement import and payment file export. For more information, see [Setting Up Banking](bank-setup-banking.md).

The following table describes a sequence of tasks, with links to the articles that describe them.

| To | See |
| --- | --- |
| Reconcile bank accounts as a separate task on the **Bank Acc. Reconciliation** page. |[Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md) |
| Reconcile bank accounts in connection with payment processing on the **Payment Reconciliation Journal** page. |[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md) |

> [!TIP]
> Use bank reconciliation to help verify that your books are up-to-date, and do not post the reconciliation until you are satisfied with the reconciliation.

## Related information

[Setting Up Banking](bank-setup-banking.md)  
[Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md)  
[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md)  
[Transfer Bank Funds](bank-how-transfer-bank-funds.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Managing Payables](payables-manage-payables.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
