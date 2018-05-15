---
title: Manage Bank Accounts| Microsoft Docs
description: You must regularly reconcile bank ledger entries in Financials with the related bank transactions in your bank accounts.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reconcile
ms.date: 05/15/2018
ms.author: sgroespe

---
# Managing Bank Accounts
At regular intervals, you must reconcile your bank ledger entries in [!INCLUDE[d365fin](includes/d365fin_md.md)] with the related bank transactions in bank accounts at your bank, and then post the balance to your bank account. You can perform this task either as part of processing the payments represented on a bank statement in the **Payment Reconciliation Journal**. Alternatively, you can perform the task separately from payment processing, in the **Bank Acc. Reconciliation** window where you match (reconcile) bank statement lines in the left-hand pane with your internal bank account ledger entries in the right-hand pane. In both windows, you can fill in the bank statement information by importing a file or feed and you can use automatic matching suggestions.

> [!NOTE]  
> In North American versions, you can also perform bank reconciliation in the **Bank Rec. Worksheet** window, which is better suited for checks and deposits but does not offer import of bank statement files. To use this window instead of the **Bank Acc. Reconciliation** window, deselect the **Bank Recon. with Auto. Match** field in the **General Ledger Setup** window. For more information, see the "Reconcile Bank Accounts" section under United States Local Functionality.

Sometimes, you need to transfer amounts between bank account in [!INCLUDE[d365fin](includes/d365fin_md.md)] to reflect transfers at your bank. You perform this task in the **General Journal** window, in different ways depending on the currency of the funds.

Before you can manage bank accounts, you must set each bank account up as a bank account card. In addition, you must set up electronic services that you may use for bank statement import and payment file export. For more information, see [Set Up Bank Accounts](bank-setup-banking.md).

The following table describes a sequence of tasks, with links to the topics that describe them.

| To | See |
| --- | --- |
| Reconcile bank accounts in connection with payment processing in the **Payment Reconciliation Journal** window. |[Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Reconcile bank accounts, including check ledger entries, as a separate task in the **Bank Acc. Reconciliation** window. |[Reconcile Bank Accounts Separately](bank-how-reconcile-bank-accounts-separately.md) |
| Post transfers between bank accounts in the same currency or in different currencies. |[Transfer Bank Funds](bank-how-transfer-bank-funds.md) |

## See Also
[Setting Up Banking](bank-setup-banking.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Managing Payables](payables-manage-payables.md)    
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
## [!INCLUDE[d365fin](includes/training_link_md.md)]
