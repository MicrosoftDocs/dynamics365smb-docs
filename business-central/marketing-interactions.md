---
title: Manage interactions with your contacts
description: Learn how to record and manage all types of interactions with your contacts—such as emails, phone calls, meetings, and letters.
author: jswymer
ms.author: jswymer
ms.reviewer: v-soumramani
ms.topic: article
ms.search.keywords: relationship, prospect
ms.search.forms: 5082
ms.date: 10/03/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Record interactions with contacts

Recording interactions with business contacts consists of these tasks:

- Setting up interaction templates  
- Creating interactions on contacts or segments  
- View and manage recorded interactions  

## Set up interaction templates

Before you can record interactions, you must set up interaction templates. An interaction template is a model that defines the basic characteristics of an interaction. When you record an interaction, you specify the interaction templates to base it on. Settings such as the mode of communication that was used, who initiated the interaction, and its cost, transfer to the interaction.

You set up an interaction template on the **Interaction Templates** page.

When you set up an interaction template, you can add an attachment. For example, you might attach a Microsoft Word document that contains notes from a meeting. Learn more at [Attachments for interactions](marketing-interaction-attachments.md) for information about attachments. Repeat the steps to set up as many interaction templates as you want.  

## Create interactions

There are two ways to record interactions:

- You can manually create interactions that are linked to a single contact or to a segment. Learn more in [Create Interactions on Contacts and Segments](marketing-how-create-interactions.md).  
- You can automatically record interactions when you perform actions in the application—for example, when you print an invoice or quote. Learn more in [Automatically Record Interactions with Contacts](marketing-auto-record-interactions.md).

## View and manage recorded interactions

You can access all recorded interactions on the **Interaction Log Entries** page. You can open this page by:

- Using the **Search for Page or Report** icon to search on **Interaction Log Entries**.
- Choosing the **Interaction Log Entries** action on a contact or segment.

  The **Interaction Log Entry** page contains the interactions you create manually and the interactions that [!INCLUDE [prod_short](includes/prod_short.md)] records automatically.

Use the Interaction Log Entries page to view the status of interactions and cancel interactions.

You can delete interaction log entries that are canceled. To delete interaction log entries, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Delete Canceled Interaction Log Entries**, choose the related link, and then fill in the information.

## Related information

[Manage Contacts](marketing-contacts.md)  
[Manage Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
