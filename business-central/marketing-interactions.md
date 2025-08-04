---
title: Manage interactions with your contacts
description: You can manage all types of communication or interactions between your company and your contacts; for example, letters, phone calls, meetings, and so on.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: article
ms.search.keywords: relationship, prospect
ms.search.forms: 5082,
ms.date: 04/01/2021
ms.custom: bap-template

ms.service: dynamics-365-business-central
---
# Record interactions with contacts

Recording interactions with business contacts consists of these tasks:

* Setting up interaction templates  
* Creating interactions on contacts or segments  
* View and manage recorded interactions  

## Set up interaction templates

Before you can record interactions, you must set up interaction templates. An interaction template is a model that defines the basic characteristics of an interaction. When you record an interaction, you specify the interaction templates it's based on. Settings such as the mode of communication that was used, who initiated the interaction, and its cost, transfer to the interaction.

You set up an interaction template on the **Interaction Templates** page.

When you set up an interaction template, you can add an attachment. For example, you might attach a Microsoft Word document that contains notes from a meeting. To learn more about attachments, go to [Attachments for interactions](marketing-interaction-attachments.md). Repeat the steps to set up as many interaction templates as you want.  

## Create interactions

There are two ways to record interactions:

* You can manually create interactions that are linked to a single contact or to a segment. For more information, see [Create Interactions on Contacts and Segments](marketing-how-create-interactions.md).  
* You can automatically record interactions when you perform actions in the application—for example, when you print an invoice or quote. For more information, see [Automatically Record Interactions with Contacts](marketing-auto-record-interactions.md).

## View and manage recorded interactions

You can view all the recorded interactions that have not been deleted on the **Interaction Log Entries** page. You can open this page by:

* Using the **Search for Page or Report** icon to search on **Interaction Log Entries**.
* Choosing the **Interaction Log Entries** action on a contact or segment.

  The **Interaction Log Entry** page contains the interactions you create manually and the interactions that [!INCLUDE [prod_short](includes/prod_short.md)] records automatically.

Use the Interaction Log Entries page to view the status of interactions and cancel interactions.

You can delete interaction log entries that have been canceled. To delete interaction log entries, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Canceled Interaction Log Entries**, choose the related link, and then fill in the information.

## Related information

[Managing Contacts](marketing-contacts.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Work with Business Central](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
