---
title: FAQs for chat (preview) with Copilot
description: This FAQ provides information about the AI technology used for chatting with Copilot in Business Central. It includes key considerations and details about how AI is used, how it was tested and evaluated, and any specific limitations.
ms.date: 01/10/2024
ms.custom: 
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: copilot, AI, chat 
---
# FAQ for chat with Copilot (preview)

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

These frequently asked questions (FAQ) describe the AI impact of Copilot assistance with bank account reconciliation in [!INCLUDE[prod_short](includes/prod_short.md)]. 

## What is chat with Copilot?


## What are capabilities of chat with Copilot?

Copilot provides AI-powered assistance with two distinct tasks: 


## What is the intended use of chat with Copilot?



## How waschat with Copilot? What metrics are used to measure performance?



## What are the limitations of chat with Copilot? How can users minimize the impact of the chat with Copilot limitations when using the system?


## What operational factors and settings allow for effective and responsible use of the feature?


## In which geographies and languages is chat with Copilot available? 

This capability is available to any environment country/region localization and in any user language. For customer environments located in countries/regions where Azure OpenAI Service isn't deployed, administrators must first consent to allowing movement of data across boundaries for [!INCLUDE[prod_short](includes/prod_short.md)] to connect to Azure OpenAI service and for this capability to be available. 

For more information on language, see previous question about limitations.  

## What is expected of end-users when operating chat with Copilot? 

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

## How do I give feedback about AI-generated content?

Each time Copilot provides matches or suggestions, you can provide feedback to Microsoft directly from the Copilot window, using the like and dislike controls. Your feedback remains anonymous and we use this data to improve the quality of the service.

## See also

[Reconcile bank accounts using bank reconciliation assist (preview)](bank-reconciliation-with-copilot.md)
