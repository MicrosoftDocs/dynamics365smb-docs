---
title: Define Business Relation Codes on Contacts| Microsoft Docs
description: Use business relations in Business Central to help with marketing and to indicate the business relationship you have with your  prospects, clients, and customers, for example, a bank or service supplier.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: marketing, prospect, contact, client, customer
ms.date: 06/06/2017
ms.author: jswymer

---
# Setting Up Business Relations on Contact Companies
You can use business relations to indicate the business relationship you have with your contacts, for example, a prospect, bank, consultant, service supplier, and so on.

Using business relations on contacts is a two-step process. First, you define the business relation code. You only have to perform this step one time for each business relation. Once you have a business relation code, you can start to assign the code to contact companies.

> [!NOTE]  
>   If you plan to synchronize your contacts with vendors, customers, or bank accounts in other parts of the application, you may want to set up a business relation for them.

## To define a business relation code
The business relation code defines a category or type of the business relationship, such as BANK or Law. You can have several business relation codes. To define the business relation, you use the **Business Relations** window.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Business Relations**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

## <a name="AssignBusRelContact"></a> To assign business relations to a contact
You cannot assign business relations to a contact person - only companies.

1. Open the contact.
2. Choose the **Company** action, and then the **Business Relations** action.

    The **Contact Business Relations** window opens.
3. In the **Business Relation Code** field, select the business relation you want to assign.

Repeat these steps to assign as many business relations as you want. You can also assign business relations from the contact list by following the same procedure.

The number of business relations you have assigned to the contact is displayed in the **No. of Business Relations** field in the **Segmentation** section in the **Contact** window.

After you have assigned business relations to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## See Also
[Creating Contact Companies](marketing-create-contact-companies.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
