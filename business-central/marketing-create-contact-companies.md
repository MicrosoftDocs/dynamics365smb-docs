---
title: Create Contact Companies| Microsoft Docs
ddescription: Outlines the tasks to create contact companies, including assigning relevant data about prospects and defining the business relationships you have with companies.
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
# Create Contacts
You regularly meet persons from other companies that may develop into business relationships, such as a customer relation. When such a new contact is made, as much information as possible must be recorded on a contact card so that communication can continue.

You can create the contact as type **Company**, for example, if the relation not an individual person but an entity, such as a contractor or a bank. You an also create the contact as type **Person**. Functionality is more or less the same for both types and both can be changed as the relationship evolves.

When a contact card is converted to a customer card, for example, the contact person or contact company becomes the name of the customer. The contact card remains, and data on the two cards will be synchronized going forward if you link them.

## Person or Company
You can decide to set up a contact as a person or a company, typically depending on whether you know the name of the contact person at the time of creation. You do this when you fill in the **Type** field on the **Contact Card** page. You can also maintain contact cards for both a company and one or more persons working in the company. This happens automatically when you fill in the **Company Name** field on a contact card of type **Person**.

Functionality is the same for both types, except that the options for additional information changes depending on the type. For example, you can only assign job responsibilities to a person and industry group to a company. This is indicated in the UI by graying out the fields and actions that do not apply. You can change the value of the **Type** field later, or you can use the fields on the **Inheritance** FastTab on the **Marketing Setup** page to control which data is shared between a person and the person's related company. For more information, see [Setting Up Contacts](marketing-setup-contacts.md).

## To create a contact manually
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Choose the **New** action.
3. In the **No.** field, enter a number for the contact.

    Alternatively, if you have set up a number series for contacts on the **Marketing Setup** page, you can press the Enter key to insert the next available contact number.  
5. Fill in the remaining fields as required. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To create a contact from a customer, vendor, or bank account
If you have customers, vendors, and bank accounts that you want to create contact cards for, you can use the **Create Contacts from** batch jobs to create contacts on the basis of the existing data. When you create a contact this way, the contact information is afterwards synchronized with the related customer, vendor, or bank account information. For more information, see [Synchronizing Contacts with Customers, Vendors, and Bank Accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-and-bank-accounts).

> [!NOTE]  
> Before you can create contacts based on existing data, you must specify a business relation code for customers, vendors, or bank accounts on the **Interactions** FastTab on the **Marketing Setup** page. For more information, see [Set up Contacts](marketing-setup-contacts.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter one of the following, depending what you want to create contacts from, and then choose the related link.
   * **Create Contacts from Customers**
   * **Create Contacts from Vendors**
   * **Create Contacts from Bank Accounts**
2. On the request page that opens, in the **Customer**, **Vendor**, or **Bank Account** section, set filters if you want to create contacts from specific customers, vendors, or bank accounts.
3. Choose the **OK** button to start creating contacts.

The next contact numbers in the number series are assigned to the new contacts. The business relations that are specified on the **Marketing Setup** page is assigned to the newly created contacts.

> [!TIP]  
> You can also do this the other way around, namely by creating a customer, vendor, or bank account from a contact. For more information, see [To create a contact as a customer, vendor, or bank account](marketing-create-contact-companies.md#to-create-a-customer-vendor-or-bank-account-from-a-contact).

## To create a customer, vendor, or bank account from a contact
If you have a customer, vendor, or bank account for the company that you want to create a contact for, you can use the **Create as** function. When you create a contact this way, the contact information is afterwards synchronized with the related customer, vendor, or bank account information. For more information, see [Synchronizing Contacts with Customers, Vendors, and Bank Accounts](marketing-create-contact-companies.md#synchronizing-contacts-with-customers-vendors-and-bank-accounts).

> [!NOTE]  
> Before you can create customers, vendors, or bank accounts from contacts, you must specify a business relation code for customers, vendors, or bank accounts on the **Interactions** FastTab on the **Marketing Setup** page. For more information, see [Setting up Contacts](marketing-setup-contacts.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Select the contact you want to create as a customer, vendor, or bank account.
3. Choose the **Create As** action, and then choose either **Customer**, **Vendor**, or **Bank**.
4. Choose the **OK** button.

The contact information is transferred from the contact card to a new customer, vendor, or bank account card. You may want to add specific information to each of the cards, such as invoicing and payment details. For more information, see, for example, [Register New Customers](sales-how-register-new-customers.md).

## To link a contact to an existing customer, vendor, or bank account
If you have a contact and either a customer, vendor, or bank account for the same company, you can link the two entities so that common data is synchronized.

1. Open the contact that you want to link.
2. Choose the **Link with existing** action, and then choose the **Customer**, **Vendor**, or **Bank** action.
3. On the page that opens, select the customer, vendor, or bank account to link to.
4. In the **Current Master Fields** field, specify whose fields to prioritize in case of conflicting information in fields common to the contact and customer, vendor, or account. For example, if the salesperson code is different on the contact card than on the customer card, you can choose to keep the one on the contact card by selecting **Contact**.
5. Choose the **OK** button.

## Synchronizing Contacts with Customers, Vendors, and Bank Accounts
If some of your contacts are also customers, vendors, or bank accounts, you can synchronize the contact information with the related customer, vendor, or bank account.

The following benefits exist when a contact is synchronized with a customer, vendor, bank account.

* You only have to update information in one place. For example, if you modify the phone number on the contact, the phone number is automatically updated with the same modification on the customer, the vendor, or the bank account.
* If you have specified a number series for contacts, when you create a customer card, a vendor card, or a bank account card, a contact card is automatically created for the customer, vendor or bank account.
* You can create sales quotes and orders and purchase quotes and orders from the contact.
* You can have your interactions recorded when you perform actions, such as printing orders, blanket orders, creating sales service orders, sending e-mails, and so on.
* If you delete a contact linked to a customer, vendor, or bank account, only the contact is removed. The customer, vendor, or bank account remains.
* If you delete a customer, vendor, bank account that is linked to a contact, the contact remains.

> [!NOTE]  
> Certain details, such as invoicing and posting details, do not appear on the contact card. Therefore, you may want to add them manually on the customer card, vendor card, or bank account card when you create contacts as customers, vendors or bank accounts.

Synchronization of common data between contacts and the related customers, vendors, or bank accounts is enabled in three ways:

* When you create contacts from customers, vendors, or bank accounts. See [To create a contact from a customer, vendor, or bank account](marketing-create-contact-companies.md#to-create-a-contact-from-a-customer-vendor-or-bank-account).
* When you create customers, vendors, or bank accounts from contacts. See [To create a customer, vendor, or bank account from a contact](marketing-create-contact-companies.md#to-create-a-customer-vendor-or-bank-account-from-a-contact).
* When you link contacts with existing customers, vendors, or bank accounts from the contact card. See [To link a contact to an existing customer, vendor, or bank account](marketing-create-contact-companies.md#to-link-a-contact-to-an-existing-customer-vendor-or-bank-account).

## To view which customer, vendor, or bank account a contact is related to
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Select the line for a contact, choose the **Related Information** action, and then choose the **Customer/Vendor/Bank Acc** action.

The page for the related card opens.

## See Also
[Managing Contacts](marketing-contacts.md)  
[Setting Up Contacts](marketing-setup-contacts.md)  
[Working with Business Central](ui-work-product.md)
