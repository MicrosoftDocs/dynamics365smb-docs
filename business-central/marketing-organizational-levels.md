---
title: Set Up Organizational Levels for Contact Persons| Microsoft Docs
description: You can define an organizational level and assign it to your contact to indicate the position they have in their company, for example, top management.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, client, prospect
ms.date: 06/06/2017
ms.author: jswymer

---
# Set Up Organizational Levels for Contact Persons
You can use organizational levels on your contacts to specify which position they have in the company, for example, top management. You can use this information when entering information about your contacts.

Using organizational levels on contacts is a two-step process. First, you define the organizational level code. You only have to perform this step one time for each organizational level. Once you have an organizational level code, you can start to assign the code to contact persons.

## To define an organizational level code
The organizational level code defines the type or category of the organizational level, such a CEO  or CFO. You can have several organizational level codes. To define the organizational level, you use the **Organizational Levels** window.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Organizational Levels**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

## To assign organizational levels to a contact person
You can assign organizational levels to contact persons only, not contact companies. You can only assign one organizational level to each contact.

1. Open the contact.
2. In the **Organizational Levels** field, select the code you want to assign.

After you have assigned organizational levels to your contacts, you can use this information to create segments.

After you have assigned job responsibilities to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## See Also
[Creating Contact Companies](marketing-create-contact-companies.md)  
[Creating Contact Persons](marketing-create-contact-persons.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
