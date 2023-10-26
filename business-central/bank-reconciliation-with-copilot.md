---
title: Reconcile bank accounts using reconciliation assist
description: Learn about how to use Copilot to reconcile bank accounts in Business Central.
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

This article explains how to use bank reconciliation assist to help you reconcile bank transactions with ledger entries in Business Central. Bank reconciliation assist is a set of AI-powered features that assist you in reconciling bank accounts. Bank reconciliation assist offers you two distinct tasks through Copilot:

- Improved matching of transactions with ledger entries

   Although the **Match Automatically** action on **Bank Acc. Reconciliation** page automatically matches most bank transactions with ledger entries, the rules-based algorithms it uses can often result in many unmatched transactions, which require manual inspection and comparison. Copilot uses AI technology to inspect remaining transactions and identify more matches, based on the dates, amounts, and descriptions. For example, if multiple invoices were paid as one lump sum by a customer, Copilot reconciles the single bank statement line with the multiple invoice ledger entries.

- Suggested general ledger accounts

  For residual bank transactions that can't be matched to any ledger entries, Copilot compares the transaction description with G/L account names, suggesting the most likely G/L account to post to. For example, Copilot might suggest that transactions with the narrative “Fuel Stop 24” be posted to the “Transportation” account.

   
## Prerequisites

- Bank reconciliation assist is enabled and activated. [Learn more about enabling Copilot and AI capabilities](enable-ai.md). This task is done by an administrator.
- You're familiar with bank account reconciliation in Business Central as described in [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).
- Bank accounts in Business Central that you want to reconcile are linked to an online bank account or set up bank statement import format. 
 

<!--H2s. Required. A how-to article explains how to do a task. The bulk of each H2 should be a procedure.-->
## Reconcile bank accounts with Copilot

<!-- Similar to the **Match Automatically** capability on the **Bank Acc. Reconciliation** page, bank reconciliation assist can also automatically matches transactions in banks statements with bank entries. The difference is that **Match Automatically** uses a native rules-based algorithm, while bank reconciliation assist is based AI technology though Copilot. Bank reconciliation assist is intended to supplement the **Match Automatically** capability. While **Match Automatically** is fairly successful at matching transactions, there are some instances where it can't&mdash;which is where bank reconciliation assist comes. By using the **Reconcile with Copilot** action on **Bank Acc. Reconciliation** page, you can find even more matches.-->

Copilot in bank reconciliation is intended to be used as a supplement to the **Match Automatically** operation. For this reason, when you use Copilot, the **Match Automatically** operation runs silently first to make the initial matches. Then, Copilot runs to try and match transactions that weren't matched by **Match Automatically** operation.   

There are two ways to reconcile bank accounts with Copilot. You can use Copilot to start a new reconciliation on a bank account from scratch, directly from **Bank Acc. Reconciliation** list, or you can use Copilot on an existing reconciliation


1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Account Reconciliation**, and then choose the related link.
1. Select the **Reconcile with Copilot**.
1. On the **Reconcile with Copilot** windows, set **Perform reconciliation for this bank account** field to the bank account that you want to reconcile.

   ![Shows the reconcile with copilot window for reconciling from scratch](media/reconcile-bank-accounts-new-copilot.svg) 
 
1. If the selected bank account isn't linked to an online bank account, you must import the bank statement file. To import the file, either select the value in the **Use transaction data from** field or select the paper clip button next the **Generate** button. Then, use the **Select the file to import** to import tha bank statement file by either dragging it from your device or browsing your device.
1. To reconcile with Copilot, select **Generate**.




## Reconcile with Copilot




## Next steps

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
