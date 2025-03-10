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

## Supported languages

[!INCLUDE[copilot-geo-and-language-availability](includes/copilot-language-support.md)]

## Prerequisites

The autofill capability is activated, and you have the permission to use it. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

## Availability

- The autofill feature is available on card and document pages, like the **Customer card** and **Sales order**.

  It's not available on pages that list entities, like **Customers** and **Sales Orders**, or worksheet pages like the **Put-away Worksheet**.
- On card and document pages, it's available on editable fields in FastTabs.

   It's not available in fields in columns or FactBoxes, fields that show dates and times, or fields with multiple lines of free text.

## Use autofill on fields

Open the page for editing, select a field, and then select the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon or press <kbd>Alt</kbd>+<kbd>i</kbd>. If the icon doesn't appear, autofill isn't available for the field, so try another field.

![Shows a card page with a Copilot icon for generating suggestions for field values.](media/autofill-field.svg).

Suggestions are generated only for fields in the FastTab that you are on. When Copilot finds suggestions, they're automatically entered in the fields along with ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** and ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** buttons. Fields remain unchanged if suggestions aren't found or they don't support autofill.

![Shows a suggested field with the accept and discard buttons.](media/autofill-suggested-value-field.svg)

Review the suggestion for each field and take appropriate action. Suggestions aren't saved until you accept them.

- To learn more about a suggestion, select the ![Shows the details icon for a suggestion](media/autofill-info.png) citation icon next to the field, or press <kbd>Alt</kbd>+<kbd>i</kbd>. The citation shows the source of the suggestion, like the most frequently or recently used value. Use the thumbs-up and thumbs-down icons to give feedback.
- To keep a suggestion, select ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** or press <kbd>Enter</kbd>.
- To reject a suggestion and keep the original value, select ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** or press <kbd>Delete</kbd>.
- To change a suggestion, select **Change** in the citation or press <kbd>F2</kbd>.

You can also use the **Keep all** button in the upper right corner of the page to accept or discard suggestions on all fields.

When you leave the page, any unaccepted suggestions are automatically discarded.

<!--The first time you use Copilot, you're asked to accept the terms to continue.-->

## Related information

[Responsible AI FAQ for autofill (preview)](faqs-autofill.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[Keyboard shortcuts](keyboard-shortcuts.md)
