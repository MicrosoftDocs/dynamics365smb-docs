---
title: Azure OpenAI Service and Business Central data
description: Understand how Azure OpenAI Service processes Business Central data when using Copilot. Learn security, privacy, and compliance aspects.
author: mikebcmsft
ms.author: mikebc
ms.reviewer: jswymer
ms.topic: article
ms.collection: bap-ai-copilot
ms.date: 04/01/2025
ms.custom: bap-template 
---
# Azure OpenAI Service and Business Central data 

Copilot in Business Central uses AI from the Azure OpenAI Service, hosted and operated by Microsoft and built with enterprise-grade security, privacy, and compliance controls. This article explains the data that the service processes when you use Copilot.

## How Business Central communicates with Azure OpenAI Service

Each time you use Copilot, your inputs (prompts) and outputs (results), including any data needed for Copilot to perform the task, are sent to the Azure OpenAI Service endpoint.

- Each request to Copilot, such as a chat message or a request to match records, is converted to one or more service calls to the endpoint.
- Prompts, results, and data from any one call is never shared or accessible to other calls by other users of the service. Including business data with prompts improves the quality of Copilot responses by grounding them in the latest information from the Business Central database. Business Central selects this data and retrieves it using Business Central's standard mechanisms for data access, ensuring that Copilot can only access the same data as the user operating Copilot. Copilot has no way to circumvent Business Central’s security, privacy, and compliance controls.  
- User input and business data might include personal information, depending on the task.
- Prompt and output data might be stored for up to 24 hours to monitor for abuse, but Microsoft only reviews the data if the automated systems flag it for review.
- Microsoft doesn't use your data to train, retrain, or improve Azure OpenAI Service foundation models.

> [!NOTE]
> When administrators activate a Copilot feature or enable data movement to Azure OpenAI Service, the entire company database remains in its location:
>
> - It isn't transferred to the Azure OpenAI Service.
> - It isn't moved to another geographic region.
> - AI isn't trained on that data.  

## Example Copilot features and their data flow

For a high-level understanding of the data sent to Azure OpenAI Service, the following table provides three examples of how Business Central sends prompts and data to the service.

The table isn't an exhaustive list of features and doesn't provide a complete and accurate picture of every data point sent to the service.

|Copilot feature|Example of user interaction|Example of data sent to Azure OpenAI Service|
|-|-|-|
|Chat|User asks Copilot to "show customer Adatum" |<ul><li>System instructions to interpret and act on the user's message, including system-defined constraints and AI safeguards.</li><li>The list of most likely table and page names, the list of available field names for those objects, along with descriptive information such as teaching tips and tooltips.</li></ul>| 
|Analysis assist|While viewing the Items list, the user asks Copilot to display "items by category" |<ul><li>System instructions to generate an analysis tab, constraints, and AI safeguards.</li><li>The list of column captions from the Items list, along with tooltips and similar descriptive information.</li><li>If the list includes option fields with predefined values, the possible values are included</li></ul>|
|Bank account reconciliation assist|User activates the **Reconcile** Copilot action on the details page |<ul><li>System instructions to compare records, constraints, and AI safeguards.</li><li>The list of bank statement lines (transaction descriptions, dates, and amounts) that the user requested Copilot to process. Additionally, the minimal list of bank account ledger entry records or G/L account names they're compared with.</li></ul>|

## Related information

[Copilot data movement across geographies](ai-copilot-data-movement.md)  
[Copilot international availability](https://aka.ms/bapcopilot-intl-report-external)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[FAQ for Copilot data security and privacy for Dynamics 365 and Power Platform](/dynamics365/faqs-copilot-data-security-privacy?toc=/dynamics365/business-central/toc.json)  
