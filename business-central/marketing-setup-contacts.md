---
title: Set Up Information for Contacts| Microsoft Docs
description: Outlines the tasks to specify information and codes, for example, about industry groups and business relationships, before you set up contacts.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 12/07/2018
ms.author: jswymer

---
# Setting Up Contacts
When creating contacts, you can enter specific information, such as the industry that the contact companies belong to and your business relationship with the contacts.

Before you create contacts and record details about your business relationships, you must set up the different codes that you will use to assign this information to your contact companies and people. Codes can be set up for mailing groups, industry groups, business relationships, Web sources, organizational levels and job responsibilities.

By having this information set up, creating contacts is much more organized and being able to find all contacts based on a certain group will be more efficient. Every group at your company will be able to find the is information making communication with the contacts more successful.

In connection with setting up your contacts, you must set up the business relationship that you have with your contacts, for example, prospect, bank, consultant, and service supplier. For more information, see [Setting Up Business Relations on Contacts Companies](marketing-business-relations.md).

## Setting Up Industry Groups for Contact Companies
You use industry groups to indicate the type of industry to which your contacts belong, for example, the retail industry or the automobile industry.

Using industry groups on contacts is a two-step process. First, you define the industry group code. You only have to perform this step one time for each industry group. Once you have an industry group code, you can start to assign the code to contact companies.

> [!NOTE]  
>   If you plan to synchronize your contacts with vendors, customers, or bank accounts in other parts of the application, you may want to set up a business relation for them.

### To define an industry group code
The industry group code defines the type or category of the group, such as ADVERT for advertising, or PRESS, for TV and radio. You can have several industry group codes. To define the industry groups, you use the **Industry Groups** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Industry Groups**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

### <a name="AssignIndustryGroupContact"></a> To assign industry groups to a contact
You cannot assign industry groups to a contact person - only companies.

1. Open the contact.
2. Choose the **Company** action, and then the **Industry Groups** action. The **Contact Industry Groups** page opens.
3. In the **Industry Groups Code** field, select the industry groups you want to assign.

Repeat these steps to assign as many industry groups as you want. You can also assign industry groups from the contact list by following the same procedure.

The number of industry groups that you have assigned to the contact is displayed in the **No. of Industry Groups** field in the **Segmentation** section on the **Contact** page.

After you have assigned industry groups to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## Setting Up Mailing Groups for Contacts
You can use mailing groups to identify groups of contacts that you want to receive the same information. For example, you can set up a mailing group for the contacts that you want to send a notification of an office move, or another group for sending holiday gifts.

Using mailing groups on contacts is a two-step process. First, you define the mailing group code. You only have to perform this step one time for each mailing group. Once you have a mailing group code, you can start to assign the code to contact companies.

### To define mailing group codes
The mailing group code defines the type or category of the group, such as MOVE for office move, or GIFT for holiday gift. You can have several industry group codes. To define the industry groups, you use the **Mailing Groups** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Mailing Groups**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

### <a name="AssignMailGroupContact"></a> To assign mailing groups to a contact
1. Open the contact.
2. Choose the **Mailing Groups** action. The **Contact Mailing Groups** page opens.
3. In the **Mailing Groups Code** field, select the mailing group that you want to assign.

Repeat these steps to assign as many mailing groups as you want. You can also assign mailing groups from the contact list by following the same procedure.

The number of mailing groups you have assigned to the contact is displayed in the **No. of Mailing Groups** field in the **Segmentation** section on the **Contact** page.

After you have assigned mailing groups to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## Setting Up Alternate Addresses for Contacts
You can assign an alternate address where your contacts are sometimes sent mail and information, for example, their summer cottage. You can also assign one or several date ranges to each alternate address you have entered for your contacts to specify when each address is valid.

### To assign an alternate address
1. Open the contact.
2. Choose the **Alternative Address** action, and then choose **Card**. The **Contact Alt. Address List** page opens.
3. Enter a new alternate address and fill in the fields on the **Contact Alternative Address** page.

Repeat these steps to assign as many alternate addresses as you want. For each alternate address you may want to specify one or several date ranges.

You can also assign alternate addresses from the contact list page by following the same procedure.

### To assign an alternate address date range
1. Open the contact.
2. Choose the **Alternate Address** action, and then choose **Date Range**. The **Contact Alt. Addr. Date Ranges** page opens.
3. Choose **New** action.
4. In the **Contact Alt. Address Code** field, select an alternate address for this contact, and then fill in the **Starting Date** and **Ending Date** fields.

Repeat these steps to assign as many date ranges as you want.

## Setting Up Job Responsibilities for Contact Persons
You can add information about the job responsibilities of contact persons to indicate what the contact person is responsible for within their company, for example, IT, management, or production. You can use this information when entering information about your contacts.

Using job responsibilities on contacts is a two-step process. First, you define the job responsibility code. You only have to perform this step one time for each job responsibility. Once you have a job responsibility code, you can start to assign the code to contact persons.

### To define a job responsibility code
The job responsibility code defines the type or category of the job, such a MARKETING or PURCHASE. You can have several job responsibility codes. To define the job responsibility, you use the **Job Responsibilities** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Responsibilities**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

### To assign job responsibilities to a contact person
You cannot assign job responsibilities to contact companies.

1. Open the contact person.
2. Choose the **Person** action, and then choose the **Job Responsibilities** action. The **Contact Job Responsibilities** page opens.
3. In the **Job Responsibility Code** field, select the job responsibility that you want to assign.

Repeat these steps to assign as many job responsibilities as you want. You can also assign job responsibilities from the contact list by following the same procedure.

The number of job responsibilities you have assigned to the contact is displayed in the **No. of Job Responsibilities** field in the **Segmentation** section on the **Contact** page.

After you have assigned job responsibilities to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## Setting Up Organizational Levels for Contact Persons
You can use organizational levels on your contacts to specify which position they have in the company, for example, top management. You can use this information when entering information about your contacts.

Using organizational levels on contacts is a two-step process. First, you define the organizational level code. You only have to perform this step one time for each organizational level. Once you have an organizational level code, you can start to assign the code to contact persons.

### To define an organizational level code
The organizational level code defines the type or category of the organizational level, such a CEO  or CFO. You can have several organizational level codes. To define the organizational level, you use the **Organizational Levels** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Organizational Levels**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

### To assign organizational levels to a contact person
You can assign organizational levels to contact persons only, not contact companies. You can only assign one organizational level to each contact.

1. Open the contact.
2. In the **Organizational Levels** field, select the code you want to assign.

After you have assigned organizational levels to your contacts, you can use this information to create segments.

After you have assigned job responsibilities to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## Setting Up Web Sources for Contact Companies
You can use web sources with your contact companies to identify, for example, search engines and web sites, on the Internet that you want to use to search for information about the contacts. When assigning web sources, you specify which search engine and search word the application will use to find the requested information.

Using web sources on contacts is a two-step process. First, you define the web source code. You only have to perform this step one time for each web source. Once you have a web source code, you can start to assign the code to contact persons.

### To define a web source code
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Web Sources**, and then choose the related link.
2. Choose the **New** actions.
3. Fill in the **Code**, **Description**, and **URL** fields.

    Type %1 in the **URL** field to insert a placeholder for a search word in the URL. When you launch the web source from a contact, the %1 is replaced with the search word, for example, the name of the company that you have entered on the **Contact Web Sources** page.

Repeat these steps to set up as many web sources as you want.

### To assign web sources to a contact company
When assigning web sources, you specify which search engine and search word that the application will use to find the requested information.

1. Open the contact.
2. Choose the **Company** action, and then choose the **Web Sources** action. The **Contact Web Sources** page opens.
3. In the **Web Source Code** field, choose the web source you want to assign.
4. In the **Search Word** field, enter the search word that you want to use to find the information.

Repeat these steps to assign as many web sources as you want.

You can also assign web sources from the **Contact List** page by following the same procedure.

## See Also
[Managing Contacts](marketing-contacts.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
