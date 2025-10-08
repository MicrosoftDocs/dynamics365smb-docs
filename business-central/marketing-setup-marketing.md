---
title: Set up marketing and contact management information
description: Set up marketing and contact management to strengthen relationships with prospects and customers, and enhance the effectiveness of your campaigns and promotions.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: relationship, prospect, client, customer, campaign, promo
ms.search.forms: 5172, 5173, 5170, 5094, 429
ms.date: 10/03/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up relationship management

Before start to work with your contacts and marketing interests, there are a few decisions and steps that you should take. You must set up how the marketing area manages certain aspects of your contacts. For example, you can decide:

- Whether to synchronize contact data with related customers, vendors, and bank accounts.
- How you define number series.
- What salutation to use when you write to your contacts.

Managing your contacts and having a strategy in place to identify, attract, and retain customers helps optimize your business and increase customer satisfaction. Using a good contact management system also helps you create and maintain relationships with your customers. Communication is the key to these relationships. Being able to tailor communication with potential and existing customers, vendors, and business partners according to their needs, is necessary for companies to succeed. Establishing a strategy and defining how your company uses contact information is a primary step. Different groups in your company access this information, so having a good system in place helps everyone be more productive.

You set up the marketing and contact management from the **Marketing Setup** page. To open the **Marketing Setup** page, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Marketing Setup**, and then choose the related link.

## Automatically copying specific information from contact companies to contact persons

Some information about contact companies is identical to the information about the contact persons working within these companies, for example, the address details. In the **Inheritance** section of the **Marketing Setup** page, you can set the application to automatically copy specific fields from the contact company card to the contact person card each time you create a contact person for a contact company. For example, you can copy:

- The salesperson code
- Address details, such as address, address 2, city, post code, and county
- Contact information

When you modify one of these fields on the contact company card, [!INCLUDE [prod_short](includes/prod_short.md)] automatically modifies the field on the contact person card (unless you manually modified the field on the contact person card).

Learn more in [Create Contacts](marketing-create-contact-companies.md).

## Use predefined defaults on new contacts

[!INCLUDE [prod_short](includes/prod_short.md)] can automatically assign a language code, territory code, salesperson code, and country/region code as defaults to each contact you create. You can also enter a default sales cycle code that you automatically assign to each new opportunity.

The inheritance of fields overwrites the default values you set up. For example, if English is the default language and the contact company's language is German, [!INCLUDE [prod_short](includes/prod_short.md)] assigns German as the language for contacts associated with that company.

<!--You can also setup a default salutation that application automatically assigns to your contacts. You can use these salutations in your interaction template attachments (for example, Microsoft Word documents). When setting up a default salutation, you can enter a salutation text and a salutation format. For example, if the salutation text is Dear, and the salutation format is Salutation Text + Title + Name, application will automatically enter Dear Mr. John Smith as a salutation for a contact called John Smith.-->

## Automatically recording interactions

[!INCLUDE[prod_short](includes/prod_short.md)] can automatically record sales and purchase documents as interactions (for example, orders, invoices, receipts, and so on), as well as emails, phone calls, and cover sheets.

Learn more in [Automatically Record Interactions with Contacts](marketing-auto-record-interactions.md).

## Synchronize contacts with customers and more

To synchronize a contact with a customer, vendor, or bank account, you must select a business relation code for customers, vendors, and bank accounts. For example, you can only link a contact with an existing customer if you selected a business relation code for customers on the **Marketing Setup** page.

Learn more at [Synchronizing Contacts with Customers, Vendors, and Bank Accounts](marketing-create-contact-companies.md#synchronize-contacts-with-customers-vendors-employees-and-bank-accounts).  

## Assign a number series to contacts and opportunities

You can set up a number series for contacts and opportunities. If you have a number series for contacts, when you create a contact, and select **Enter** in the **No.** field on the **Contact Card** page, [!INCLUDE [prod_short](includes/prod_short.md)] enters the next available contact number.

Learn more about number series at [Create Number Series](ui-create-number-series.md).

## Search for duplicate contacts when contacts are created

You can choose to have application automatically search for duplicates each time you create a contact company, or you can choose to search manually after you created contacts. You can also choose to have application update the search strings automatically each time you modify contact information or create a contact. You can decide the search hit percentage, that is, the percentage of identical strings two contacts must have for application to consider them as duplicates.

## Related information

[Managing Contacts](marketing-contacts.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
