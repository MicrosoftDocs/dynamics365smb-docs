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

# Get assistance filling in fields with Copilot (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Copilot includes an autofill feature that lets you fill in editable fields on your page automatically. The autofill feature is available on card and document pages, like a sales order, an item, or a customer card. Use autofill when you're creating or modifying a record.

Copilot provides field values as suggestions that you can keep, replace, or discard. Suggestions can be based on your Business Central data, such as the values most frequently or recently used on records. They can also be AI-generated, based on a field's option values, lookup values, or page context.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Supported languages

[!INCLUDE[copilot-geo-and-language-availability](includes/copilot-language-support.md)]

## Prerequisites

The autofill feature is activated. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

## Use autofill

Copilot is available on most editable fields on a page. For example, it's not available on fields that set a date or fields that get their value from a number series. To check whether it's available on a field, select the field. If the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon appears, Copilot is available. Select the icon to get suggestions.

![Shows a card page with a Copilot icon for generating suggestions for field values.](media/autofill-field.svg).

When Copilot finds suggestions, they're automatically entered in the fields with the ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** and ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** buttons.

![Shows a suggested field with the accept and discard buttons.](media/autofill-field.svg).

Review the suggestions for each field. Suggestions aren't saved until you accept them.

- Select the ![Shows the details icon for a suggestion](media/autofill-info.png) to see the reasoning behind it.
- Select **Accept the suggestion** to save the value in Business Central, similar to entering it manually without Copilot.
- Select **Discard the suggestion** to clear the value and delete the changes.

When you leave the page, any suggestions that you didn't accept are automatically discarded.

The first time you use Copilot, you're asked to accept the terms to continue.

## Related information

[Responsible AI FAQ for autofill (preview)](faqs-autofill.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
