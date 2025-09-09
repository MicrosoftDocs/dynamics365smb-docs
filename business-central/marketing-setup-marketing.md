---
title: Set Up Marketing and Contact Management Information
description: Set up marketing and contact management in Business Central to strengthen relationships with prospects and customers, and enhance the effectiveness of your campaigns and promotions.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: relationship, prospect, client, customer, campaign, promo
ms.search.forms: 5172, 5173, 5170, 5094, 429
ms.date: 09/09/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up relationship management

Before you get started working with your contacts and marketing interests, there are a few decisions and steps that you should take to set up how the marketing area manages certain aspects of your contacts. For example, you can decide whether to synchronize the contact card with the customer card, vendor card, and bank account card, how number series are defined, or what the standard salutation should be when writing to your contacts.

Managing your contacts and having a strategy in place to identify, attract, and retain customers helps optimize your business and increase customer satisfaction. Using a good contact management system also helps you create and maintain relationships with your customers. Communication is the key to these relationships. Being able to tailor communication with potential and existing customers, vendors, and business partners according to their needs, is necessary for companies to succeed. Establishing a strategy and defining how your company uses contact information is a primary step. This information is viewed by many different groups in your company, so having a good system in place helps everyone be more productive.

You set up the marketing and contact management from the **Marketing Setup** page. To open the **Marketing Setup** page, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Marketing Setup**, and then choose the related link.

## Automatically copying specific information from contact companies to contact persons

Some information about contact companies is identical to the information about the contact persons working within these companies, for example, the address details. In the **Inheritance** section of the **Marketing Setup** page, you can set the application to automatically copy specific fields from the contact company card to the contact person card each time you create a contact person for a contact company. For example, you can select to copy the salesperson code, address details (address, address 2, city, post code, and county), communication details (fax number, telex answer back, and phone number), and more.

When you modify one of these fields on the contact company card, application automatically modifies the field on the contact person card (unless you manually modified the field on the contact person card).

Learn more in [Create Contacts](marketing-create-contact-companies.md).

## Use predefined defaults on new contacts

You can decide that the application automatically assigns a specific language code, territory code, salesperson code, and country/region code as defaults to each new contact you create. You can also enter a default sales cycle code that application automatically assigns to each new opportunity you create.

The inheritance of fields overwrites the default values you set up. For example, if English is the default language and the contact company's language is German, the application automatically assigns German as the language code for contact persons associated with that company.

<!--You can also setup a default salutation that application automatically assigns to your contacts. You can use these salutations in your interaction template attachments (for example, Microsoft Word documents). When setting up a default salutation, you can enter a salutation text and a salutation format. For example, if the salutation text is Dear, and the salutation format is Salutation Text + Title + Name, application will automatically enter Dear Mr. John Smith as a salutation for a contact called John Smith.-->

## Automatically recording interactions

[!INCLUDE[prod_short](includes/prod_short.md)] can automatically record sales and purchase documents as interactions (for example, orders, invoices, receipts, and so on), as well as emails, phone calls, and cover sheets.

Learn more in [Automatically Record Interactions with Contacts](marketing-auto-record-interactions.md).

## Synchronize contacts with customers and more

In order to synchronize the contact card with the customer card, the vendor card, and the bank account card, you must select a business relation code for customers, vendors, and bank accounts. For example, you can only link a contact with an existing customer if you selected a business relation code for customers on the **Marketing Setup** page.

Learn more in [Synchronizing Contacts with Customers, Vendors, and Bank Accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-employees-and-bank-accounts).  

## Assign a number series to contacts and opportunities

You can set up a number series for contacts and opportunities. If you have set up a number series for contacts, when you create a contact, and select <kbd>Enter</kbd> in the No. field on the contact card, application automatically enters the next available contact number.

Learn more about number series in [Create Number Series](ui-create-number-series.md).

## Search for duplicate contacts when contacts are created

You can choose to have application automatically search for duplicates each time you create a contact company, or you can choose to search manually after you created contacts. You can also choose to have application update the search strings automatically each time you modify contact information or create a contact. You can decide the search hit percentage, that is, the percentage of identical strings two contacts must have for application to consider them as duplicates.

## Related information

- [Managing Contacts](marketing-contacts.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
