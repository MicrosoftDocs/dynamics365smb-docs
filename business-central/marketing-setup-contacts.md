---
title: Set up information for contacts
description: Outlines the tasks to specify information and codes, for example, about industry groups and business relationships, before you set up contacts.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: relationship, prospect
ms.date: 09/09/2025
ms.author: bholtorf
ms.reviewer: v-soumramani
---

# Set up information for contacts

When you create contacts you can enter information about them, such as:

- The industry the contact belongs to.
- Your business relationship with them.

Before you create contacts and record details about your business relationships, you must set up some of the information that you assign to them. For example:

- Mailing groups
- Industry groups
- Business relations
- Web sources
- Organizational levels
- Job responsibilities

You can set up this information on their pages, or from the Contact Card page by choosing the **New** action in the drop-down menu for the fields.  

This information helps you organize your contacts so they're easier to find when you want to communicate with them. For example, you can find all contacts based on a certain group.

## Assign industry groups to a contact

Industry groups indicate the type of industry that your contacts are in. For example, the retail industry or the automobile industry.

> [!NOTE]
> You can only assign industry groups to contacts of type **Company**.

The industry group code defines the type or category of the group, such as ADVERT for advertising, or PRESS, for TV and radio. You can have several industry group codes. Define industry groups on the **Industry Groups** page.

1. Open the relevant contact card.
2. Choose the **Company** action, and then the **Industry Groups** action. The **Contact Industry Groups** page opens.
3. In the **Industry Groups Code** field, select the industry groups you want to assign.

Repeat these steps to assign as many industry groups as you want. You can also assign industry groups from the contact list by following the same procedure.

<!--The number of industry groups that you assigned to the contact displays in the **No. of Industry Groups** field in the **Segmentation** section on the **Contact Card** page. -->

After you assign industry groups to your contacts, you can use this information to select contacts for your segments. Learn more in [Add Contacts to Segments](marketing-add-contact-segment.md).

## Assign mailing groups to a contact

You can use mailing groups to identify groups of contacts that you want to send the same information to. For example, you can set up a mailing group for the contacts that you want to notify about an office move, or a group for sending holiday gifts.

The mailing group code defines the type or category of the group, such as MOVE for office move, or GIFT for holiday gift. You can have several mailing group codes. Define mailing groups on the **Mailing Groups** page.

1. Open the relevant contact card.
2. Choose the **Mailing Groups** action. The **Contact Mailing Groups** page opens.
3. In the **Mailing Groups Code** field, select the mailing group that you want to assign.

Repeat these steps to assign as many mailing groups as you want. You can also assign mailing groups from the contact list.

<!--The number of mailing groups you have assigned to the contact is displayed in the **No. of Mailing Groups** field in the **Segmentation** section on the **Contact Card** page.-->

After you assign mailing groups to your contacts, you can use the information to select contacts for your segments. Learn more in [Add Contacts to Segments](marketing-add-contact-segment.md).

## Define an alternate address for a contact

You can assign an alternate address where your contact sometimes wants to receive mail and information. For example, their vacation home. You can also assign date ranges that specify when to use each alternate address.

1. Open the relevant contact card.
2. Choose the **Card** action.

    To define that the alternate address applies in a specific period, choose the **Date Range** action instead.
3. On the **Contact Alt. Address List** page, enter a new alternate address and fill in the fields on the **Contact Alternative Address** page.

Repeat these steps to assign as many alternate addresses as you want. You can specify one or more date ranges for each alternate address.

## Assign job responsibilities to a contact

You can add information about the job responsibilities of contact persons to indicate what the contact person is responsible for. For example, IT, management, or production.

> [!NOTE]
> You can only specify job responsibilities for contacts of the type **Person**.

The job responsibility code defines the type or category of the job, such a MARKETING or PURCHASE. You can have several job responsibility codes. Define job responsibilities on the **Job Responsibilities** page.

1. Open the relevant contact card.
2. Choose the **Job Responsibilities** action. The **Contact Job Responsibilities** page opens.
3. In the **Job Responsibility Code** field, select the job responsibility.

Repeat these steps to assign as many job responsibilities as you want. You can also assign job responsibilities from the contact list.

<!--The number of job responsibilities you have assigned to the contact is displayed in the **No. of Job Responsibilities** field in the **Segmentation** section on the **Contact** page. -->

After you assign job responsibilities to your contacts, you can use this information to select contacts for your segments. Learn more in [Add Contacts to Segments](marketing-add-contact-segment.md).

## Assign organizational levels to a contact

You can use organizational levels on your contacts to specify where they are in their company. For example, top management.

> [!NOTE]
> You can only assign organizational levels to contacts of the type **Person**.

The organizational level code defines the type or category of the organizational level, such a CEO or CFO. You can have several organizational level codes. Define organizational levels on the **Organizational Levels** page.

1. Open the relevant contact card.
2. In the **Organizational Levels** field, select the code you want to assign.

After you assign organizational levels to your contacts, you can use this information to create segments.

After you assign job responsibilities to your contacts, you can use this information to select contacts for your segments. Learn more in [Add Contacts to Segments](marketing-add-contact-segment.md).

## Assign web sources to a contact

You can use web sources with your contact companies to identify, for example, web sites that you want to use to search for information about the contacts. When assigning web sources, you specify which search engine and search word to use to find the requested information.

> [!NOTE]
> You can only assign web sources to contacts of the type **Company**.

1. Open the relevant contact card.
2. Choose the **Web Sources** action. The **Contact Web Sources** page opens.
3. In the **Web Source Code** field, choose the web source you want to assign.
4. In the **Search Word** field, enter the search word that you want to use to find the information.

Repeat these steps to assign as many web sources as you want.

## Assign business relations to a contact

Business relations indicate the business relationship you have with your contacts. For example, a prospect, bank, consultant, service supplier, and so on.

> [!NOTE]
> You can only assign business relations to contacts of the type **Company**.

1. Open the relevant contact card.
2. Choose the **Business Relations** action.
3. On the **Contact Business Relations** page, in the **Business Relation Code** field, select the business relation you want to assign.

Repeat these steps to assign as many business relations as you want.

<!--The number of business relations you have assigned to the contact is displayed in the **No. of Business Relations** field in the **Segmentation** section on the **Contact** page. -->

After you assign business relations to your contacts, you can use this information to select contacts for your segments. Learn more in [Add Contacts to Segments](marketing-add-contact-segment.md).

## Copy information from contact companies to contact persons

Some information about contact companies is the same for their contact persons. For example, the address details. On the **Inheritance** FastTab on the **Marketing Setup** page, you can specify which fields on the contact card for a company is copied to the contact card for a person each time you create a contact person for the contact company.

When you change the value in one of these fields on the contact company, the same fields update on the contact person. The exception is if you manually change the field on the contact person.

Learn more in [Create Contacts](marketing-create-contact-companies.md).

## Use predefined default settings on new contacts

You can use the **Defaults** FastTab on the **Marketing Setup** page to specify default values that [!INCLUDE [prod_short](includes/prod_short.md)] automatically assigns to new contacts.

> [!NOTE]
> You can also enter a default sales cycle code that application automatically assigns to each new opportunity you create.

The settings for inheritance overwrite the default values you set up. For example, if you specify English as the default language, but the contact company's language is German, [!INCLUDE [prod_short](includes/prod_short.md)] assigns German as the language code for the contact persons for that company.

## Synchronize contacts with customers, vendors, and bank accounts

To synchronize the contact card with a linked customer, vendor, or bank account, fill in the relevant field in the **Bus. Relation Code for** section on the **Interactions** FastTab on the **Marketing Setup** page.  

Learn more in [Synchronizing contacts with customers, vendors, and bank accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-employees-and-bank-accounts).

## Search for duplicate contacts

When you create a contact, [!INCLUDE [prod_short](includes/prod_short.md)] can automatically search for duplicates. Avoiding duplicate contacts can help ensure that you interact with the right person for the right company.

You can specify the percentage of identical data that two contacts must have in order to consider them duplicates. You can also just use the default percentage, which is 60. You specify the percentage on the **Marketing Setup** page by entering a percentage value in the **Search Hit %** field on the **Duplicates** FastTab.

For automatic searches, when you create a contact that already has a business relation to a company, [!INCLUDE [prod_short](includes/prod_short.md)] displays a message to inform you.

To manually search for duplicates, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Duplicate Contacts**, and then choose the related link.
2. Choose the **Generate Duplicate Search String** action.
3. On the **Generate Duplicate Search String** page, enter filter criteria that determine the match, and then choose **OK**.

When you find a duplicate contact, you can use the **Merge Contacts** action to merge it with a contact record that you want to keep. Learn more in [Merge Duplicate Records](sales-how-merge-duplicate-records.md). That article describes the process from the Customer Card page, but the steps are the same for contacts.

## Related information

- [Managing Contacts](marketing-contacts.md)  
- [Create Contacts](marketing-create-contact-companies.md)  
- [Managing Sales Opportunities](marketing-manage-sales-opportunities.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
