---
title: Get assistance filling in fields with Copilot (preview)
description: Learn how to use Copilot's autofill feature to assist you in filling in fields on card and document pages.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 09/18/2024
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: bap-template
---

# Autofill fields with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Copilot's autofill feature assists you by automatically filling in editable fields on your page. Use autofill when creating or modifying a record. It suggests field values that you can choose to keep, replace, or discard. These suggestions are based on your Business Central data, such as frequently or recently used values, or they can be AI-generated based on option values, lookup values, or page context.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

<!--
## Supported languages

[!INCLUDE[copilot-geo-and-language-availability](includes/copilot-language-support.md)]
-->
## Prerequisites

The autofill feature is activated. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

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

## Use autofill to fill in fields

Start by opening the page for editing. Copilot is available only on specific editable fields on a page. To check whether it's available on a field, select the field. If the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon appears, Copilot is available. Select the icon to get suggestions.

Open the page for editing, select a field, and then select the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon. If the icon doesn't appear, autofill isn't available for the field, so try another field.


![Shows a card page with a Copilot icon for generating suggestions for field values.](media/autofill-field.svg).

When Copilot finds suggestions, they're automatically entered in the fields along with ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** and ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** buttons.

![Shows a suggested field with the accept and discard buttons.](media/autofill-suggested-value-field.svg)

Review the suggestions for each field. Suggestions aren't saved until you accept them.

- Select the ![Shows the details icon for a suggestion](media/autofill-info.png) to see the reasoning behind the value.
- Select **Accept the suggestion** to save the value in Business Central, similar to entering it manually without Copilot.
- Select **Discard the suggestion** to clear the value and delete the changes.

When you leave the page, any suggestions that you didn't accept are automatically discarded.

The first time you use Copilot, you're asked to accept the terms to continue.

## Related information

[Responsible AI FAQ for autofill (preview)](faqs-autofill.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
