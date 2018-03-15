---
title: Set Up Industry Groups for Contact Companies| Microsoft Docs
description: Describes how to define an industry group and assign it to a contact company, for example, the retail industry or the automobile industry.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 06/06/2017
ms.author: jswymer

---
# Set Up Industry Groups for Contact Companies
You use industry groups to indicate the type of industry to which your contacts belong, for example, the retail industry or the automobile industry.

Using industry groups on contacts is a two-step process. First, you define the industry group code. You only have to perform this step one time for each industry group. Once you have an industry group code, you can start to assign the code to contact companies.

> [!NOTE]  
>   If you plan to synchronize your contacts with vendors, customers, or bank accounts in other parts of the application, you may want to set up a business relation for them.

## To define an industry group code
The industry group code defines the type or category of the group, such as ADVERT for advertising, or PRESS, for TV and radio. You can have several industry group codes. To define the industry groups, you use the **Industry Groups** window.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Industry Groups**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

## <a name="AssignIndustryGroupContact"></a> To assign industry groups to a contact
You cannot assign industry groups to a contact person - only companies.

1. Open the contact.
2. Choose the **Company** action, and then the **Industry Groups** action. The **Contact Industry Groups** window opens.
3. In the **Industry Groups Code** field, select the industry groups you want to assign.

Repeat these steps to assign as many industry groups as you want. You can also assign industry groups from the contact list by following the same procedure.

The number of industry groups that you have assigned to the contact is displayed in the **No. of Industry Groups** field in the **Segmentation** section in the **Contact** window.

After you have assigned industry groups to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## See Also
[Creating Contact Companies](marketing-create-contact-companies.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
