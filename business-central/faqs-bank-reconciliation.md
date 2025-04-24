---
title: FAQ for bank account reconciliation assist with Copilot (preview)
description: This FAQ provides information about the AI technology used for reconciling bank accounts and statements in Business Central. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 04/01/2025
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI 
ms.collection:
  - bap-ai-copilot
---

# FAQ for bank account reconciliation assist with Copilot

These frequently asked questions (FAQ) describe the AI impact of Microsoft Copilot assistance with bank account reconciliation in [!INCLUDE[prod_short](includes/prod_short.md)].

## What is bank reconciliation assist?

Bank reconciliation is a common accounting task where organizations review their bank account statements to identify transactions that should be registered in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, this task is used to identify periodic bank fees or small employee expenses.

Bank reconciliation is typically a multi-step process. First, bank statements are imported into [!INCLUDE[prod_short](includes/prod_short.md)]. Next, transactions are matched with ledger entries. Finally, new ledger entries are posted to reflect any residual transactions that weren't previously known to your ledgers.

Copilot in [!INCLUDE[prod_short](includes/prod_short.md)] reduces the manual effort by matching more transactions and suggesting general ledger (G/L) accounts that you can post to.

## What are the capabilities of bank reconciliation assist?

Copilot provides AI-powered assistance with two distinct tasks:

- Improved matching of transactions with ledger entries

    [!INCLUDE[prod_short](includes/prod_short.md)] offers automated rules that automatically match many bank transactions with ledger entries. However, these rules are inflexible and often result in many unmatched transactions, each of which requires manual inspection and comparison. Copilot uses AI technology to inspect those unmatched transactions and identify more matches, based on the dates, amounts, and descriptions. For example, if a customer paid multiple invoices in one lump sum, Copilot reconciles the single bank statement line with the multiple invoice ledger entries.

- Suggested G/L accounts

    For residual bank transactions that can't be matched to any ledger entries, Copilot uses AI technology to compare the transaction description with G/L account names and then suggest the most likely G/L account to post to. For example, if unmatched transactions have the narrative *Fuel Stop 24*, Copilot might suggest that you post them to the *Transportation* account.

Copilot doesn't connect to your bank to retrieve or send transactions. This task remains fully within your control. It's a prerequisite for using Copilot's assistance, regardless of whether the transactions are added to [!INCLUDE[prod_short](includes/prod_short.md)] by using a digital bank connection, imported from a bank statement file, or manually entered.

## What is the intended use of bank reconciliation assist?

Bank account reconciliation assist is designed to improve the accuracy of ledgers by helping customers identify new transactions that they should account for in [!INCLUDE[prod_short](includes/prod_short.md)]. It isn't intended for fraud detection or to identify whether customers paid on time.

## How was bank reconciliation assist evaluated? What metrics are used to measure performance?

Bank account reconciliation assist was tested by using combinations of synthetic bank transaction data and similar G/L accounts and ledger entries that cover the typical variations and data limits for each field and in different languages. Test data represents both typical usage and usage by bad actors. Performance was measured in comparison to manual reconciliation of the same data.

## What are the limitations of bank reconciliation assist? How can users minimize the impact of these limitations when they use the system?

Bank account reconciliation assist performs best when G/L account names, ledger entry descriptions, and bank transaction descriptions are all in the same language. Mixed languages or mixed languages for transaction descriptions often result in fewer matches and suggestions.

Suggested ledger accounts performs best in one of the supported languages (see the next section for a list of languages). Users might experience fewer transaction matches and fewer suggested ledger accounts in other languages.

## In which geographies and languages is bank reconciliation assist available? 

[!INCLUDE[copilot-geo-and-language-availability](includes/copilot-geo-and-language-availability.md)]

## What is expected of system users when they operate bank account reconciliation assist?

### During bank account reconciliation

AI-powered matches and suggestions might sometimes be incorrect or incomplete. Users of bank account reconciliation assist must review the accuracy of the matches and suggestions that Copilot provides before they choose to keep them. Copilot's matches and suggestions aren't saved to the [!INCLUDE[prod_short](includes/prod_short.md)] database until you select the **Keep it** button and close the Copilot window. You can edit and correct any matches or suggestions before you choose to keep them.

### After bank account reconciliation is completed

We recommend that users also verify accuracy and correct any discrepancies after they close the Copilot window. This process should include the following activities:

- Review the reconciliation test report.
- Ensure that your organization has the appropriate review and audit processes in place.
- Reopen any posted reconciliations by using the **Undo** function.
- Correct any erroneous ledger entries through reverse posting of entries.

## What is expected of administrators and system users when they operate bank account reconciliation assist?

System users, such as accountants, treasurers, or other people who work on business accounting, should always review the accuracy of matches and suggestions that Copilot provides before they choose to keep them. After reconciliation with Copilot, we recommend that these users review the reconciliation test report to verify accuracy and identify any discrepancies.

Administrators should ensure that the appropriate accounting users are granted access to this capability.

## Is Copilot the only means of completing bank account reconciliation?

No. Use of Copilot is optional. [!INCLUDE[prod_short](includes/prod_short.md)] offers traditional, non-AI-powered means of importing bank statements, running predefined matching rules, and manually applying matches and posting to appropriate ledger accounts. Both the traditional approach and Copilot can be used simultaneously in an organization.

## How do I give feedback about AI-generated content?

Each time that Copilot provides matches or suggestions, you can provide feedback to Microsoft directly from the Copilot window by using the like (thumbs up) and dislike (thumbs down) controls. Your feedback remains anonymous, and we use this data to improve the quality of the service.

## Related information

[Reconcile bank accounts with Copilot](bank-reconciliation-with-copilot.md)  
[Copilot data movement across geographies](/dynamics365/business-central/ai-copilot-data-movement)  
