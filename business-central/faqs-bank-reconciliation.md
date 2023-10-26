---
title: FAQ for generative AI
description: This FAQ provides information about the AI technology used in Business Central, along with key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 10/07/2023
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
---

# FAQ for bank reconciliation assist

These frequently asked questions (FAQ) describe the AI impact of bank reconciliation assist in Business Central.

## What is bank reconciliation?

Bank reconciliation is a common accounting task where organizations review their bank account statements to identify transactions that should be registered in Business Central. For example, this would be used to identify periodic bank fees. This is typically a multi-step process, starting with importing bank statements into Business Central, followed by matching transactions with ledger entries, and posting new ledger entries to reflect any residual transactions that were not previously known to your ledgers. Copilot in Business Central reduces manual effort by matching more transactions and suggesting general ledger accounts that you can post to. 


## What are capabilities of bank reconciliation assist?

Copilot provides AI-powered assistance with two distinct tasks: 

- Improved matching of transactions with ledger entries 

   Business Central offers automated rules that automatically match many bank transactions with ledger entries. However, these rules are inflexible and often result in many unmatched transactions that each require manual inspection and comparison. Copilot uses AI technology to inspect remaining transactions and identify more matches, based on the dates, amounts and descriptions. For example, if multiple invoices were paid as one lump sum by a customer, Copilot reconciles the single bank statement line with the multiple invoice ledger entries. 

- Suggested general ledger accounts 

   For residual bank transactions that could not be matched to any ledger entries, Copilot uses AI technology to compare the transaction description with G/L account names, suggesting the most likely G/L account to post to. For example, Copilot may suggest that transaction with narrative “Fuel Stop24” be posted to the “Transportation” account. 

Copilot does not connect to your bank to retrieve or send transactions: this task remains fully within your control and is a prerequisite to begin using Copilot’s assistance, whether those transactions are added to Business Central using a digital bank connection, imported from a bank statement file, or entered manually. 

## What is the intended use of bank reconciliation assist?

Bank reconciliation assist is designed to help identify new transactions that customers should account for in Business Central, to improve the accuracy of their ledgers. This activity is not intended for fraud detection or identifying if customers have paid on time.  

## How was bank reconciliation assist evaluated? What metrics are used to measure performance?

This functionality was tested using combinations of synthetic bank transaction data and similar G/L accounts and ledger entries, that cover the typical variations and data limits for each field and in different languages. Test data represents both typical usage as well as usage by bad actors. 

## What are the limitations of bank reconciliation assist? How can users minimize the impact of the bank reconciliation limitations when using the system?

Bank reconciliation assist performs best when G/L account names, ledger entry descriptions, and bank transaction descriptions are all in the same language. Mixed languages, or mixed language of transaction descriptions will often result in less matches and suggestions. 

Bank account reconciliation assist performs best in English language: while this feature can be operated in any of the available Business Central languages, users may experience fewer transaction matches and fewer suggested ledger accounts in other languages. 

<!--

## What operational factors and settings allow for effective and responsible use of the feature?


-->
## In which geographies and languages is bank reconciliation assist available? 

This capability is available to any environment country localization and in any user language. For customer environments located in countries/regions where Azure OpenAI Service is not deployed, administrators must first consent to allowing movement of data across boundaries for Business Central to connect to Azure OpenAI service and for this capability to be available. 

See limitations for more information on language.  

## What is expected of administrators and end-users when operating bank account reconciliation assist? 

End-users, such as accountants, treasurers or others working on business accounting should always review the accuracy of matches and suggestions provided by Copilot before choosing to keep them. After reconciling with Copilot, we recommend reviewing the reconciliation test report to verify accuracy and identify any discrepancies. 

Administrators should ensure the appropriate accounting users have been granted access to this capability. 

## Is Copilot the only means to completing bank account reconciliation? 

No – use of Copilot is optional. Business Central offers traditional means of importing bank statements, running predefined matching rules, and manually applying matches and posting to appropriate ledger accounts. Both the traditional approach and Copilot can be used simultaneously within an organization. 
This capability is available to any environment country localization and in any user language. For customer environments located in countries/regions where Azure OpenAI Service is not deployed, administrators must first consent to allowing movement of data across boundaries for Business Central to connect to Azure OpenAI service and for this capability to be available. 


## How do I give feedback about AI-generated content?

Each time Copilot provides matches or suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the like and dislike controls. Your feedback remains anonymous and we use this data to improve the quality of the service.


## See also

[Reconcile bank accounts using bank reconciliation assist (preview)](bank-reconciliation-with-copilot.md)
