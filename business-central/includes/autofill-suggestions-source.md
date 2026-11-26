---
author: jswymer
ms.topic: include
ms.date: 11/24/2026
ai-usage: ai-assisted
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
When you ask Copilot to autofill from a field on a page in Business Central, it suggests values for supported fields within a field group (FastTab). When you use **Auto paste**, Copilot bases its suggestions on text that you copied to your clipboard. These suggestions aren't always AI-generated. Copilot uses various mechanisms described in the following table to provide suggestions for each field.

Regardless of whether the suggested value is AI-generated, Copilot always uses AI to determine the applicable mechanisms and whether the suggestion is sufficiently relevant in the context of the record. 

|Mechanism|Description|
|-|-|
|Most Frequently Used|The value most frequently assigned to records in your company. The suggested value isn't computed using AI and comes directly from your Business Central data.|
|Most Recently Used|For fields that reference another table, the value is the most recently used reference or the most recently viewed record for that table. The suggested value isn't computed using AI and comes directly from your Business Central data.|
|Lookup selection|For fields that reference another table and have a short list of possible choices, AI is used to intelligently select from the possible values.|
|AI-generated|AI is used to intelligently generate the suggested value based on general knowledge available to AI.|
|Web Search|For fields that typically contain publicly available information, Copilot searches the web for potential matches and provides suggestions. AI is used to extract and match the best suggested value.|
|Clipboard|When you select **Auto paste**, Copilot uses text from your clipboard to suggest field values. AI is used to match the copied information to fields on the page.|
