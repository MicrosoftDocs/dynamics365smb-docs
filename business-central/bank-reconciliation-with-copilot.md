---
title: Reconcile bank accounts using reconciliation assist
description: Leran about how to use Copilot to reconcile bank accounts in Business Central.
author: jswymer 
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to 
ms.collection: get-started
ms.date: 10/25/2023
ms.custom: bap-template 
---

# Reconcile bank accounts using bank reconciliation assist (preview)

[!INCLUDE[ai-preview](includes/ai-preview.md)]

This article explains how to use bank reconciliation assist to improve and bank reconciliation process. Bank reconciliation assist is a set of AI-powered features that assist you in reconciling bank accounts. Bank reconciliation assist offers you two distinct tasks through Copilot:

- Improved matching of transactions with ledger entries

   Although Business Central offers automated rules that automatically match many bank transactions with ledger entries, these rules are inflexible and often result in many unmatched transactions, which require manual inspection and comparison. Copilot uses AI technology to inspect remaining transactions and identify more matches, based on the dates, amounts and descriptions. For example, if multiple invoices were paid as one lump sum by a customer, Copilot reconciles the single bank statement line with the multiple invoice ledger entries.

- Suggested general ledger accounts

  For residual bank transactions that could not be matched to any ledger entries, Copilot uses AI technology to compare the transaction description with G/L account names, suggesting the most likely G/L account to post to. For example, Copilot may suggest that transaction with narrative “Fuel Stop24” be posted to the “Transportation” account.

   
## Prerequisites

- Bank reconciliation assist is enabled and activated. [Learn more about enabling Copilot and AI capabilities](enable-ai.md). This task is done by an administrator.
- You're familiar with bank account reconciliation in Business Central as described in [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).
- Any bank accounts in Business Central that you want to reconcile are linked to an online bank account or set up bank statement import format.
 

<!--H2s. Required. A how-to article explains how to do a task. The bulk of each H2 should be a procedure.-->
## Reconcile bank accounts with Copilot

Similar to the **Match Automatically** capability on the **Bank Acc. Reconciliation** page, bank reconciliation assist can also automatically matches transactions in banks statements with bank entries. The difference is that **Match Automatically** uses a native rules-based algorithm, while bank reconciliation assist is based AI technology though Copilot. Bank reconciliation assist is intended to supplement the **Match Automatically** capability. While **Match Automatically** is fairly successful at matching transactions, there are some instances where it can't&mdash;which is where bank reconciliation assist comes. By using the **Reconcile with Copilot** action on **Bank Acc. Reconciliation** page, you can find even more matches.

There are two ways to reconcile bank account with Copilot:

- From the 







## Reconcile
## Next steps

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
