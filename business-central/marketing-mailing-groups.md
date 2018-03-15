---
title: Set Up Mailing Groups for Contacts| Microsoft Docs
description: You can use mailing groups to identify groups of contacts that you want to receive the same information, for example, for a marketing campaign or promo.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: marketing, campaign, promo, prospect
ms.date: 06/06/2017
ms.author: jswymer

---
# Set Up Mailing Groups for Contacts
You can use mailing groups to identify groups of contacts that you want to receive the same information. For example, you can set up a mailing group for the contacts that you want to send a notification of an office move, or another group for sending holiday gifts.

Using mailing groups on contacts is a two-step process. First, you define the mailing group code. You only have to perform this step one time for each mailing group. Once you have a mailing group code, you can start to assign the code to contact companies.

## To define mailing group codes
The mailing group code defines the type or category of the group, such as MOVE for office move, or GIFT for holiday gift. You can have several industry group codes. To define the industry groups, you use the **Mailing Groups** window.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Mailing Groups**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

## <a name="AssignMailGroupContact"></a> To assign mailing groups to a contact
1. Open the contact.
2. Choose the **Mailing Groups** action. The **Contact Mailing Groups** window opens.
3. In the **Mailing Groups Code** field, select the mailing group that you want to assign.

Repeat these steps to assign as many mailing groups as you want. You can also assign mailing groups from the contact list by following the same procedure.

The number of mailing groups you have assigned to the contact is displayed in the **No. of Mailing Groups** field in the **Segmentation** section in the **Contact** window.

After you have assigned mailing groups to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## See Also
[Creating Contact Companies](marketing-create-contact-companies.md)  
[Creating Contact Persons](marketing-create-contact-persons.md)  
[Working with Financials](ui-work-product.md)
