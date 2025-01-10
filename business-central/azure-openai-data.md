---
title: Azure OpenAI Service and Business Central data
description: Learn about the Business Central data that's processed by the sAzure OpenAI service when you use Copilot
author: 
ms.author: mikebc
ms.reviewer: jswymer
ms.topic: conceptual 
ms.collection: bap-ai-copilot
ms.date: 01/10/2025
ms.custom: bap-template 
---

# Azure OpenAI Service and Business Central data 
 
Copilot in Business Central uses AI from the Azure OpenAI Service, hosted and operated by Microsoft and built with enterprise-grade security, privacy, and compliance controls. This article explains what data is processed by the service when you use Copilot. 

## How Business Central communicates with Azure OpenAI Service 

Each time you use Copilot, your inputs (prompts) and outputs (results), including any data needed for Copilot to perform the task, may be sent to the Azure OpenAI Service endpoint.

- Each request to Copilot, such as a chat message or request to match records, is converted to one or more service calls to that endpoint. 
- Prompts, results and data from any one call is never shared or accessible to other calls by other users of the service. Including business data with prompts improves the quality of Copilot responses by grounding them in the latest information from your Business Central database. This data is selected by Business Central and retrieved using Business Central’s standard mechanisms for data access, ensuring that Copilot can only access the same data that the user operating Copilot has access to, and that Copilot has no way to circumvent Business Central’s security, privacy, and compliance controls.  
- Depending on the task, user input and business data may sometimes include personal information. 
- We might store prompt and output data for up to 24 hours to monitor for abuse, but we don't look at it unless our automated systems flag it for review. 
- We don't use your data to train, retrain, or improve Azure OpenAI Service foundation models. 

> [!NOTE]
> When administrators activate a Copilot feature, or enable data movement to Azure OpenAI Service, the entire company database does not move from its location:  
>
> - It is not transferred into the Azure OpenAI Service.
> - It is not moved to another geographic region.
> - AI is not trained on that data.  

## Example Copilot features and their data flow 

For a high-level understanding of the type of data sent to Azure OpenAI Service, the following table provides 3 simplified examples of how Business Central sends prompts and data to that service.

The table is not intended to be an exhaustive list of features, nor is it intended to provide a complete and accurate picture of every datapoint sent to the service.

|Copilot feature|Example user interaction|Example contents of a prompt|
|-|-|-|
|Chat|Users asks Copilot to “show customer Adatum” |System instructions to interpret and act on the user’s message, including system-defined constraints and AI safeguards.The list of most likely table and page names, the list of available field names for those objects, along with descriptive information such as teaching tips and tooltips.| 
|Analysis assist|While viewing the Items list, the user asks Copilot to display “items by category” |The prompts will typically include:<ul><li>System instructions to generate an analysis tab, constraints, and AI safeguards.<li></li>The list of column captions from the Items list, along with tooltips and similar descriptive information.<li></li>If the list includes option fields with predefined values, the possible values are included</li></ul>|
|Bank account reconciliation assist|User activates the Reconcile Copilot action on the details page |The prompts will typically include:<ul><li>System instructions to compare records, constraints, and AI safeguards.<li></li>The list of bank statement lines (transaction descriptions, dates and amounts) that that the user requested Copilot to process, and the minimal list of bank account ledger entry records or G/L Account names they will be compared with. </li></ul>|
 
## Related information

Geos https://go.microsoft.com/fwlink/?linkid=2250267 

Configuring 

Security and Privacy FAQ

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
