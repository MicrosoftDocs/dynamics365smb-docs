---
title: FAQs for bank account reconciliation assist (preview) with Copilot
description: This FAQ provides information about the AI technology used for reconciling bank accounts and statements Business Central. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 03/27/2024
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

# FAQ for bank account reconciliation assist with Copilot (preview)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

These frequently asked questions (FAQ) describe the AI impact of Copilot assistance with bank account reconciliation in [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## What is bank reconciliation assist?

Bank reconciliation is a common accounting task where organizations review their bank account statements to identify transactions that should be registered in [!INCLUDE[prod_short](includes/prod_short.md)]. For example, this task would be used to identify periodic bank fees or small employee expenses. This task is typically a multi-step process, starting with importing bank statements into [!INCLUDE[prod_short](includes/prod_short.md)], followed by matching transactions with ledger entries, and posting new ledger entries to reflect any residual transactions that weren't previously known to your ledgers. Copilot in [!INCLUDE[prod_short](includes/prod_short.md)] reduces manual effort by matching more transactions and suggesting general ledger accounts that you can post to. 

## What are capabilities of bank reconciliation assist?

Copilot provides AI-powered assistance with two distinct tasks: 

- Improved matching of transactions with ledger entries 

   [!INCLUDE[prod_short](includes/prod_short.md)] offers automated rules that automatically match many bank transactions with ledger entries. However, these rules are inflexible and often result in many unmatched transactions that each require manual inspection and comparison. Copilot uses AI technology to inspect remaining transactions and identify more matches, based on the dates, amounts, and descriptions. For example, if multiple invoices were paid as one lump sum by a customer, Copilot reconciles the single bank statement line with the multiple invoice ledger entries. 
 
- Suggested general ledger accounts 

   For residual bank transactions that couldn't be matched to any ledger entries, Copilot uses AI technology to compare the transaction description with G/L account names, suggesting the most likely G/L account to post to. For example, Copilot might suggest that transaction with narrative "Fuel Stop24" be posted to the "Transportation" account. 

Copilot doesn't connect to your bank to retrieve or send transactions. This task remains fully within your control and is a prerequisite to begin using Copilot's assistance, whether those transactions are added to [!INCLUDE[prod_short](includes/prod_short.md)] using a digital bank connection, imported from a bank statement file, or entered manually. 

## What is the intended use of bank reconciliation assist?

Bank account reconciliation assist is designed to help identify new transactions that customers should account for in [!INCLUDE[prod_short](includes/prod_short.md)], to improve the accuracy of their ledgers. This activity isn't intended for fraud detection or identifying if customers have paid on time.   

## How was bank reconciliation assist evaluated? What metrics are used to measure performance?

This functionality was tested using combinations of synthetic bank transaction data and similar G/L accounts and ledger entries that cover the typical variations and data limits for each field and in different languages. Test data represents both typical usage and usage by bad actors. Performance was measured in comparison to manual reconciliation of the same data. 

## What are the limitations of bank reconciliation assist? How can users minimize the impact of the bank reconciliation limitations when using the system?

Bank account reconciliation assist performs best when G/L account names, ledger entry descriptions, and bank transaction descriptions are all in the same language. Mixed languages or mixed language of transaction descriptions often result in fewer matches and suggestions. 

Suggested ledger accounts performs best in one of the supported languages (see the next section for a list of languages). Users might experience fewer transaction matches and fewer suggested ledger accounts in other languages.

## In which geographies and languages is bank reconciliation assist available? 

- Available geographies

  This Copilot feature is available in all supported [Business Central countries/regions](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). However, for customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing their data to move across boundaries for [!INCLUDE [prod_short](includes/prod_short.md)] to connect to Azure OpenAI service. Learn more at [Copilot data movement across geographies](ai-copilot-data-movement.md).

- Available languages

  [!INCLUDE[bank-recon-assist-language-support](includes/bank-recon-assist-language-support.md)]

## What is expected of end-users when operating bank account reconciliation assist? 

### While using bank account reconciliation 

AI-powered matches and suggestions might sometimes be incorrect or incomplete. Users of bank account reconciliation assist must review the accuracy of matches and suggestions provided by Copilot before choosing to keep them. Copilot’s matches and suggestions aren't saved to the [!INCLUDE[prod_short](includes/prod_short.md)] database until you choose the Keep it button and exiting the Copilot window. You can also edit and correct any matches or suggestions before choosing to keep it. 

### After completing bank account reconciliation 

It's recommended that users also verify accuracy and correct any discrepancies after exiting the Copilot window, including the following activities: 

- Review the reconciliation test report. 
- Ensure your organization has the appropriate review and audit processes in place. 
- Reopen any posted reconciliations by using the Undo function. 
- Correct any erroneous ledger entries through reverse posting of entries. 

## What is expected of administrators and end-users when operating bank account reconciliation assist? 

End-users, such as accountants, treasurers or others working on business accounting should always review the accuracy of matches and suggestions provided by Copilot before choosing to keep them. After reconciling with Copilot, we recommend reviewing the reconciliation test report to verify accuracy and identify any discrepancies. 

Administrators should ensure the appropriate accounting users have been granted access to this capability. 

## Is Copilot the only means to completing bank account reconciliation? 

No – use of Copilot is optional. [!INCLUDE[prod_short](includes/prod_short.md)] offers traditional, non-AI-powered means of importing bank statements, running predefined matching rules, and manually applying matches and posting to appropriate ledger accounts. Both the traditional approach and Copilot can be used simultaneously within an organization. 

## How do I give feedback about AI-generated content?

Each time Copilot provides matches or suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the like and dislike controls. Your feedback remains anonymous and we use this data to improve the quality of the service.


## See also

[Reconcile bank accounts using bank reconciliation assist (preview)](bank-reconciliation-with-copilot.md)
