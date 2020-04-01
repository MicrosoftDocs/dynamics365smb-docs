---
title: Set Up Information for Contacts| Microsoft Docs
description: Outlines the tasks to specify information and codes, for example, about industry groups and business relationships, before you set up contacts.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up Contacts
When creating contacts, you can enter specific information, such as the industry that the contact belong to and your business relationship with the contacts.

Before you create contacts and record details about your business relationships, you must set up the different codes that you will use to assign this information to your contact companies and people. Codes can be set up for mailing groups, industry groups, business relationships, Web sources, organizational levels and job responsibilities. You can set these up by choosing the **New** action as you look up to the lists from the contact card.  

By having this information set up, creating contacts is much more organized and being able to find all contacts based on a certain group will be more efficient. Every group at your company will be able to find the is information making communication with the contacts more successful.

## To assign industry groups to a contact
You use industry groups to indicate the type of industry to which your contacts belong, for example, the retail industry or the automobile industry.

> [!NOTE]
> This is only possible for contacts of type **Company**.

The industry group code defines the type or category of the group, such as ADVERT for advertising, or PRESS, for TV and radio. You can have several industry group codes. To define the industry groups, you use the **Industry Groups** page.

1. Open the relevant contact card.
2. Choose the **Company** action, and then the **Industry Groups** action. The **Contact Industry Groups** page opens.
3. In the **Industry Groups Code** field, select the industry groups you want to assign.

Repeat these steps to assign as many industry groups as you want. You can also assign industry groups from the contact list by following the same procedure.

The number of industry groups that you have assigned to the contact is displayed in the **No. of Industry Groups** field in the **Segmentation** section on the **Contact Card** page.

After you have assigned industry groups to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## To assign mailing groups to a contact
You can use mailing groups to identify groups of contacts that you want to receive the same information. For example, you can set up a mailing group for the contacts that you want to send a notification of an office move, or another group for sending holiday gifts.

The mailing group code defines the type or category of the group, such as MOVE for office move, or GIFT for holiday gift. You can have several industry group codes. To define the industry groups, you use the **Mailing Groups** page.

1. Open the relevant contact card.
2. Choose the **Mailing Groups** action. The **Contact Mailing Groups** page opens.
3. In the **Mailing Groups Code** field, select the mailing group that you want to assign.

Repeat these steps to assign as many mailing groups as you want. You can also assign mailing groups from the contact list by following the same procedure.

The number of mailing groups you have assigned to the contact is displayed in the **No. of Mailing Groups** field in the **Segmentation** section on the **Contact Card** page.

After you have assigned mailing groups to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## To define a contact's alternate address
You can assign an alternate address where your contact sometimes wants to receive mail and information, for example, their summer cottage. You can also assign one or several date ranges to each alternate address you have entered for your contacts to specify when each address is valid.

1. Open the relevant contact card.
2. Choose the **Alternative Address** action, and then choose the **Card** action.

    To define that the alternate address applies in a specific period, choose the **Date Range** action instead.
3. On the **Contact Alt. Address List** page, enter a new alternate address and fill in the fields on the **Contact Alternative Address** page.

Repeat these steps to assign as many alternate addresses as you want. For each alternate address you may want to specify one or several date ranges.

## To assign job responsibilities to a contact
You can add information about the job responsibilities of contact persons to indicate what the contact person is responsible for within their company, for example, IT, management, or production. You can use this information when entering information about your contacts.

> [!NOTE]
> This is only possible for contacts of type **Person**.

The job responsibility code defines the type or category of the job, such a MARKETING or PURCHASE. You can have several job responsibility codes. To define the job responsibility, you use the **Job Responsibilities** page.

1. Open the relevant contact card.
2. Choose the **Person** action, and then choose the **Job Responsibilities** action. The **Contact Job Responsibilities** page opens.
3. In the **Job Responsibility Code** field, select the job responsibility that you want to assign.

Repeat these steps to assign as many job responsibilities as you want. You can also assign job responsibilities from the contact list by following the same procedure.

The number of job responsibilities you have assigned to the contact is displayed in the **No. of Job Responsibilities** field in the **Segmentation** section on the **Contact** page.

After you have assigned job responsibilities to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## To assign organizational levels to a contact
You can use organizational levels on your contacts to specify which position they have in the company, for example, top management. You can use this information when entering information about your contacts.

> [!NOTE]
> This is only possible for contacts of type **Person**.

The organizational level code defines the type or category of the organizational level, such a CEO  or CFO. You can have several organizational level codes. To define the organizational level, you use the **Organizational Levels** page.

1. Open the relevant contact card.
2. In the **Organizational Levels** field, select the code you want to assign.

After you have assigned organizational levels to your contacts, you can use this information to create segments.

After you have assigned job responsibilities to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## To assign web sources to a contact
You can use web sources with your contact companies to identify, for example, search engines and web sites, on the Internet that you want to use to search for information about the contacts. When assigning web sources, you specify which search engine and search word the application will use to find the requested information.

> [!NOTE]
> This is only possible for contacts of type **Company**.

When assigning web sources, you specify which search engine and search word that the application will use to find the requested information.

1. Open the relevant contact card.
2. Choose the **Company** action, and then choose the **Web Sources** action. The **Contact Web Sources** page opens.
3. In the **Web Source Code** field, choose the web source you want to assign.
4. In the **Search Word** field, enter the search word that you want to use to find the information.

Repeat these steps to assign as many web sources as you want.

## To assign business relations to a contact
You can use business relations to indicate the business relationship you have with your contacts, for example, a prospect, bank, consultant, service supplier, and so on.

> [!NOTE]
> This is only possible for contacts of type **Company**.

1. Open the relevant contact card.
2. Choose the **Company** action, and then the **Business Relations** action.
3. On the **Contact Business Relations** page, in the **Business Relation Code** field, select the business relation you want to assign.

Repeat these steps to assign as many business relations as you want.

The number of business relations you have assigned to the contact is displayed in the **No. of Business Relations** field in the **Segmentation** section on the **Contact** page.

After you have assigned business relations to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## Automatically Copying Specific Information from Contact Companies to Contact Persons
Some information about contact companies is identical to the information about the contact persons working within these companies, for example, the address details. On the **Inheritance** FastTab on the **Marketing Setup** page, you can specify which fields on the contact card for a company is copied to the contact card for a person each time you create a contact person for the contact company.

When you modify one of these fields on the contact company card, the same fields on the contact person card are updated, unless you have manually modified the field on the contact person card.

For more information, see [Create Contacts](marketing-create-contact-companies.md).

## Using Predefined Defaults on New Contacts
You can decide that the application automatically assigns a specific language code, territory code, salesperson code, and country/region code as defaults to each new contact you create. You can also enter a default sales cycle code that application automatically assigns to each new opportunity you create. You set this up on the On the **Defaults** FastTab on the **Marketing Setup** page

The inheritance of fields overwrites the default values you have set up. For example, if you have set up English as the default language, but the contact company's language is German, application will automatically assign German as the language code for the contact persons recorded for that company.

## Synchronizing Contacts with Customers, Vendors, and Bank Accounts
In order to synchronize the contact card with a linked customer, vendor, or bank account card, you must fill in the relevant field in the **Bus. Relation Code for** section on the **Interactions** FastTab on the **Marketing Setup** page.  

For more information, see [Synchronizing contacts with customers, vendors, and bank accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-and-bank-accounts).

## Searching for Duplicate Contacts
You can choose to have application automatically search for duplicates each time you create a contacts, or you can choose to search manually after you have created contacts. You can also choose to have application update the search strings automatically each time you modify contact information or create a contact. You can decide the search hit percentage, that is, the percentage of identical strings two contacts must have for application to consider them as duplicates. You set this up on the **Duplicates** FastTab on the **Marketing Setup** page.

When you have found a duplicate contact, you can use the **Merge Duplicate** page to merge it into an existing contact record that you want to keep. For more information, see [Merge Duplicate Records](sales-how-merge-duplicate-records.md).

## See Also
[Managing Contacts](marketing-contacts.md)  
[Create Contacts](marketing-create-contact-companies.md)  
[Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
