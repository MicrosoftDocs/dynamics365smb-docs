---
title: Create interactions on contacts and segments
description: Learn how to create interactions in Business Central for communication that you have with your contacts and segments.
author: brentholtorf
ms.author: bholtorf
ms.topic: how-to
ms.reviewer: bholtorf
ms.date: 12/13/2023
ms.custom: bap-template
ms.search.keywords: relationship, prospect
ms.search.forms: 5077, 5078, 5074, 5076, 5186, 5075, 5079
ms.service: dynamics-365-business-central
---
# Create interactions on contacts and segments

You can create interactions to track the communications you have with a single contact, or with multiple contacts in your segments. To make it easy to create interactions, [!INCLUDE [prod_short](includes/prod_short.md)] provides the **Create Interaction** assisted setup guide. The guide helps you capture the important details about the interaction.

Before you create interactions though, you must set up interaction templates. To learn more about interaction templates, go to [Set Up Interaction Templates](marketing-interactions.md).

## To create an interaction with a contact

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Contacts**, **Salesperson**, or **Interaction Log Entry**, and then choose the related link.
2. Choose the **Create Interaction** action.
3. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> If you need to stop before you've finished the interaction, you can choose **Cancel** and then specify whether you want to save your settings so you can continue later. To learn more about postponed interactions, go to [To finish setting up a postponed interaction](#to-finish-setting-up-a-postponed-interaction).

## To create an interaction on a segment

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Segments**, and then choose the related link.
2. Choose the **Create Interaction** action.
3. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

> [!TIP]
> After you assign an interaction to a segment, there are several other actions you can take on the **Segment** page:
>
> * Personalize the interaction for each particular contact within the segment, for example, by selecting another interaction template on the lines.  
>* Log the segment and interactions by choosing the **Log** action to open the **Log Segment** page.
> * Create a new segment containing the same contacts by choosing the **Create Follow-up Segment** checkbox. This setting requires that a number series is specified for segments on the **Marketing Setup** page.

An interaction is recorded for each contact within the segment in the **Interaction Log Entry** table, and the segment is logged. Logged segments are available on the **Logged Segment** page.

## To finish setting up a postponed interaction

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Postponed Interactions**, and then choose the related link.
2. Choose the interaction you want to finish, and then choose the **Resume** action.

## Related information

[Recording Interactions](marketing-interactions.md)  
[Managing Contacts](marketing-contacts.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Work with Business Central](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
