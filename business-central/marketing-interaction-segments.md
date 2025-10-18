---
title: Keep track of segments and related interactions
description: Learn about creating segments to define groups of contacts and specifying interactions for segments.
author: jswymer
ms.topic: concept-article
ms.search.keywords: relationship, prospect
ms.search.forms: 5091, 5139
ms.date: 10/03/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ms.custom: bap-template
---

# Manage interactions for segments

The **Segment** page is a type of worksheet where you can:

* Create segments.
* Save the segmentation criteria you used to select contacts.
* Log the segment and record interactions involving the contacts within the segment.

## Segmenting

There are several ways to create segments:

* You can manually enter the contacts you want to include in the segment lines.
* You can select contacts.
* You can reuse a logged segment as the basis to create a new one.
* You can reuse saved segmentation criteria.

## Interactions

On the **Segment** page, you can create interactions for several contacts simultaneously. For example, you can merge a segment with a Microsoft Word document, so that you can send a letter to all the contacts in the segment.

You can specify information about the interaction for the segment on the **Segment** header. For example, you can decide which interaction template you want to use for all the contacts, specify a description, a correspondence type, and so on. However, you can modify this information in the segment line for each particular contact, for example, by specifying another description for one contact. If you're merging a segment with a Microsoft Word document, you can personalize the document for one or several contacts in the segment. For example, you might add individualized comments to the document.

## Logging

On the **Segment** page, when you choose **Log**, the application records the interactions on the **Interaction Log Entry** page, and logs the segment. After you log the segment, you can only find it on the **Logged Segments** page.

On the **Logged Segments** page, you can decide to create a follow-up segment containing the same contacts as the segment you logged.

## Related information

[Create Segments](marketing-how-create-segment.md)  
[Create Interactions for Segments](marketing-how-create-interactions.md)  
[Managing Segments](marketing-segments.md)  
[Recording Interactions With Contacts](marketing-interactions.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Creating and Managing Contacts](marketing-contacts.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
