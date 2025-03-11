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

When Copilot generates suggestions, it only accesses the business data you can access. Copilot never saves suggestions automatically but presents them for you to decide what to keep. Copilot uses AI, and suggestions might not be correct.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

<!--Suggestions are based on Business Central that only you have access to.-->

## Prerequisites

Autofill is activated, and you have the required permissions to use it. Learn more in [Configure Copilot and agent capabilities](enable-ai.md).

## Supported languages

[!INCLUDE[copilot-geo-and-language-availability](includes/copilot-language-support.md)]

## Availability

The autofill feature is available on card and document pages, like a **Customer card** or a **Sales Order**. It's available on editable fields within FastTabs on these pages, excluding those displaying values like IDs, dates/times, or multiple lines of text.

It's unavailable in various places, including entity list pages like **Customers** and **Sales Orders**, worksheet pages like the **Put-away Worksheet**, and fields in columns and FactBoxes.

## Use autofill on fields

Open the page for editing, select a field, and then select the ![Shows the Copilot icon for generating suggestions for field values.](media/copilot-star-unfilled.png) **Suggest a value for this field and related fields** icon or press <kbd>Alt</kbd>+<kbd>i</kbd>. If the icon doesn't appear, autofill isn't available for the field, so try another field.

![Shows a card page with a Copilot icon for generating suggestions for field values.](media/autofill-field.svg).

Suggestions are generated only for fields in the FastTab that you are on. When Copilot finds suggestions, they're automatically entered in the fields in italics along with the ![Shows the details icon for a suggestion](media/autofill-info.png) **Show details** icon. Fields remain unchanged if suggestions aren't found or they don't support the autofill feature.

![Shows a suggested field with the accept and discard buttons.](media/autofill-suggested-value-field.svg)

When you hover over or select a field that includes a suggestion, the ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** and ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** buttons appear.

### Review suggestions

Review the suggestion for each field and take appropriate action. Suggestions aren't saved until you accept them.

- To learn more about a suggestion, select the ![Shows the details icon for a suggestion](media/autofill-info.png) **Show details** icon next to the field, or press <kbd>Alt</kbd>+<kbd>i</kbd>. The details include the source of the suggestion, like the most frequently or recently used value. Use the thumbs-up and thumbs-down icons to give feedback.
- To keep a suggestion, select ![Shows the accept button for a Copilot suggestion](media/autofill-accept.png) **Accept the suggestion** or press <kbd>Enter</kbd>.
- To reject a suggestion and keep the original value, select ![Shows the discard button for a Copilot suggestion](media/autofill-discard.png) **Discard the suggestion** or press <kbd>Delete</kbd>.
- To change a suggestion, select **Change** in the details or press <kbd>F2</kbd>.

You can also use the **Keep all** button in the upper right corner of the page to accept or discard suggestions on all fields.

When you leave the page, any unaccepted suggestions are automatically discarded.

<!--The first time you use Copilot, you're asked to accept the terms to continue.-->

## Related information

[Responsible AI FAQ for autofill (preview)](faqs-autofill.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
[Troubleshoot Copilot and AI capabilities](ai-copilot-troubleshooting.md)  
[Keyboard shortcuts](keyboard-shortcuts.md)
