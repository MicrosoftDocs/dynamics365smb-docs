---
title: Autofill fields with Copilot (preview)
description: Learn how to use Copilot's autofill feature to assist you in filling in fields on card and document pages.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 03/10/2025
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: bap-template
---

# Autofill fields with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Copilot's autofill feature assists you by automatically filling in editable blank fields on your page. Use autofill when creating or modifying a record. It suggests field values that you can choose to keep or discard. These suggestions are based on your Business Central data, such as frequently or recently used values, or they can be AI-generated based on option values, lookup values, or page context.

Lets add "suggestions are based on Business Central that only you have access to"
And "Copilot never saves suggestions automatically, but presents them to you so that you can decide what to keep. Copilot uses AI and is not always correct."

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

<!--
## Supported languages

[!INCLUDE[copilot-geo-and-language-availability](includes/copilot-language-support.md)]
-->
## Prerequisites

The autofill feature is activated, and you have the permission to use it. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

## Limitations

- Languages

  [!INCLUDE[copilot-geo-and-language-availability](includes/copilot-language-support.md)]

- Pages types

  The autofill feature is available on card, document, and worksheet pages, like an item, sales order, or put-away worksheet. It isn't available in lists, FactBoxes, assisted setup guides, or other dialog boxes.
- Field types

  The autofill feature is available on editable fields in FastTabs only. It's not available on:

  - Fields in columns
  - Multiline text fields
  - Masked fields
  - Date/time fields
  - Toggle switches
  - Fields that uniquely identify a record, such as fields defined by number series.

## Use autofill on fields

<!--Start by opening the page for editing. Copilot is available only on specific editable fields on a page. To check whether it's available on a field, select the field. If the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon appears, Copilot is available. Select the icon to get suggestions.-->

Open the page for editing, select a field, and then select the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon. If the icon doesn't appear, autofill isn't available for the field, so try another field.

![Shows a card page with a Copilot icon for generating suggestions for field values.](media/autofill-field.svg).

Suggestions are generated only for fields in the FastTab that you are on. When Copilot finds suggestions, they're automatically entered in the fields along with ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** and ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** buttons. Fields remain unchanged if suggestions aren't found or they don't support autofill.

![Shows a suggested field with the accept and discard buttons.](media/autofill-suggested-value-field.svg)

Review the suggestion for each field and take appropriate action. Suggestions aren't saved until you accept them.

- To learn more about a suggestion, select the ![Shows the details icon for a suggestion](media/autofill-info.png) citation icon. The citation shows the source of the suggestion, like the most frequently or recently used value. Use the thumbs-up and thumbs-down icons to give feedback on the suggestion.
- To save a suggestion, select ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** in the field or citation.
- To reject a suggestion and keep the original value, select **Discard the suggestion** in the field or citation.

You can also use the **Keep all** button in the upper right corner of the page to accept or discard suggestions on all fields.

When you leave the page, any unaccepted suggestions are automatically discarded.

<!--The first time you use Copilot, you're asked to accept the terms to continue.-->

## Related information

[Responsible AI FAQ for autofill (preview)](faqs-autofill.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
