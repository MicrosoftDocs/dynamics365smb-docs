---
title: Create Interactions on Contacts and Segments| Microsoft Docs
description: Describes how to create interactions for communication that you have with your contacts and segments in Business Central, for example, direct mail.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 04/01/2020
ms.author: jswymer

---
# Create Interactions on Contacts and Segments
You can create interactions to record all the interactions and communications you have with your contacts and segments, for example, direct mail.

Before you create interactions, you must set up interaction templates. For more information, see  [Set Up Interaction Templates](marketing-interactions.md).

## To create an interaction
1. Open the contact, salesperson, or interaction log entry.
2. Choose the **Create Interaction** action.
3. Fill in the fields, and then choose the **OK** button.

> [!NOTE]  
>   If you need to perform another task before finishing the interaction, you can choose **Cancel** and then finish the interaction at a later time. This postpones the interaction.

## To finish and delete postponed interactions
1. Open the contact, salesperson, or interaction log entry.
2. Choose **Postponed Interactions**.
3. Select the interaction you want to finish, and then choose the **Resume** action.

## To create an interaction on a segment
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Segments**, and then choose the related link.
2. In the **Segment page**, in the **Interaction** section, fill in the fields to specify which interaction you want to assign to the segment.

    After you have assigned an interaction to the segment, you can personalize the interaction for each particular contact within the segment, for example, by selecting another interaction template on the lines on the **Segment** page.  
3. To log the segment and interactions, choose the **Log** action. The **Log Segment** page opens.
4. If you want to create a new segment containing the same contacts, select the **Create Follow-up Segment** check box. To create a follow-up segment, you must have specified number series for segments on the **Marketing Setup** page.

An interaction is recorded for each contact within the segment in the **Interaction Log Entry** table, and the segment is logged. Logged segments can be found on the **Logged Segment** page.

If you have selected the **Create Follow-up Segment** check box, a new segment is created that contains the same contacts as the segment you have just logged.

## See Also
[Recording Interactions](marketing-interactions.md)  
[Managing Contacts](marketing-contacts.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Working with Business Central](ui-work-product.md)
