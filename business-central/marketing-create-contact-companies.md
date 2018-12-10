---
title: Create Contact Companies| Microsoft Docs
ddescription: Outlines the tasks to create contact companies, including assigning relevant data about prospects and defining the business relationships you have with companies.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 12/07/2018
ms.author: edupont

---
# Creating Contact Companies
Your company regularly meets prospective companies that usually develop into future business relationships. When a new contact is made, this information needs to be recorded so that communication can continue.

By assigning as much data as possible about a specific company ensures efficient communication. For example, assigning the relevant industry group, ensures that specific companies are included in any relevant communication.

You can also define the business relationship that you have with a contact. For example, a contact could be a prospect, bank, or contractor.

## Creatinge Contact Companies
You can create a contact for each new company you interact with, for example, a customer, vendor, prospective customer, bank, law firm, consultant, and so on.

There are two ways to create a contact:
from scratch or from an existing customer, vendor, or bank account.

Before creating a contact, you may want to check the settings on the **Marketing Setup** page. For more information, see [Setting Up Relationship Management](marketing-setup-marketing.md).

### To create a company contact from scratch
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
2. Choose the **New** action.
3. In the **No. field**, enter a number for the contact.

    Alternatively, if you have set up a number series for contacts on the **Marketing Setup** page, you can press the Enter key to select the next available contact number.  
4. Set **Type** to **Company**.
5. Fill in the other fields as required.

### To create a company contact from a customer, vendor, or bank account
If you have already set up a number of customers, vendors, and bank accounts, you can create contacts on the basis of the existing data. When you create a contact this way, the contact information is synchronized with the customer, vendor, or bank account information.

> [!NOTE]  
>   Before you can create contact companies this way, you must specify a business relation code for customers, vendors, and bank accounts on the **Marketing Setup** page. If you will be creating contacts from a bank accounts, you must also specify numbers series for bank accounts on the **General Ledger Setup** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter one of the following, depending on from where you want to create contacts, and then choose the related link.
   * **Create Contacts from Customers**
   * **Create Contacts from Vendors**
   * **Create Contacts from Bank Accounts**
2. In the batch job page that opens, in the **Customer**, **Vendor**, or **Bank Account** section, set filters if you want to create contacts from specific customers, vendors, or bank accounts.
3. Choose the **OK** button to start creating contacts.

    The next contact numbers in the number series are assigned to the new contacts. The business relation for vendors that is specified on the **Marketing Setup** page is assigned to the newly created contacts.

> [!TIP]  
>   You can also create a customer, vendor, or bank account from a contact. For more information, see [Create a Customer, Vendor, or Bank Account From a Contact](marketing-how-create-contacts-new-customers-vendors-bank-accounts.md).

## Synchronizing Contacts With Customers, Vendors, and Bank Accounts
If some of your contacts are also customers, vendors, or bank accounts, you can synchronize the contact information with the related customer, vendor, or bank account. Synchronization makes information that is common between contacts and customers, vendors, or bank account the same.  

Before you can synchronize your contacts with customers, vendors, or bank accounts, you must specify a business relation code for customers, vendors, and bank accounts on the **Marketing Setup** page. For more information, see [Setting Up Relationship Management](marketing-setup-marketing.md).

### Different Ways to Synchronize Contacts with Customers, Vendors and Bank Accounts
You can synchronize your contacts with customers, vendors, or bank accounts by three methods:

* Link contacts with existing customers, vendors, or bank accounts from the contact card. For more information, see [Link Contacts With Customers, Vendors, and Bank Accounts](marketing-how-link-contact.md).
* Create customers, vendors, or bank accounts from the contact. For more information, see [Create a Customer, Vendor, or Bank Account From a Contact](marketing-how-create-contacts-new-customers-vendors-bank-accounts.md).
* Create contacts from customers, vendors or bank accounts. For more information, see [Create a company contact from a customer, vendor, or bank account](marketing-how-create-contact-companies.md).

### Consequences of Synchronization
When the contact is synchronized with the customer, vendor, bank account:

* You only have to update information in one place. For example, if you modify the phone number on the contact, the phone number is automatically updated with the same modification on the customer, the vendor, or the bank account.
* If you have specified a number series for contacts, when you create a customer card, a vendor card, or a bank account card, a contact card is automatically created for the customer, vendor or bank account.
* You can create sales quotes and orders, and purchase quotes and orders from the contact.
* You can have your interactions recorded when you perform actions such as printing orders, blanket orders, creating sales service orders, sending e-mails, and so on.
* If you delete a contact linked to a customer, vendor or bank account, only the contact is removed. The customer, vendor, or bank account remains.
* If you delete a customer, vendor, bank account linked to a contact, the contact remains.

> [!NOTE]  
>   Some details, such as invoicing and posting details, do not appear on the contact card. Therefore, you may want to add them manually on the customer card, vendor card, or bank account card when you create contacts as customers, vendors or bank accounts.

## Linking Contacts With Customers, Vendors, and Bank Accounts
If you have contact and either a customer, vendor, or bank account for the same company, you can link the two entities. Linking the two entities enables you to synchronize data that is common so that it is the same in both places.

### To link a contact to an existing customer, vendor, or bank account
1. Open the contact that you want to link.
2. Choose the **Link with existing** action, and then choose **Customer**, **Vendor**, or **Bank**.
3. Select the customer, vendor, or bank account to link to.

   In the **Current Master Fields**, you specify which fields should prioritize in case of conflicting information in fields common to the contact and customer, vendor, or account. For example, if the salesperson code is different in the contact than the customer, you can decide, by selecting **Contact**, to use the information in the contact.

## Creating a Customer, Vendor, or Bank Account From a Contact
   You may want to record some of your existing contacts as customers, vendors, or bank accounts. Creating a customer, vendor, or bank account from a contact enables you use existing data. When you create a customer, vendor, or bank account this way, it is synchronized with the contact. Synchronization makes information that is common between contacts and customers, vendors, or bank account the same.

   Before you can record contacts this way, you must specify a business relation code for customers, vendors, and bank accounts on the **Marketing Setup** page. If you will be recording contacts as bank accounts, you must also specify numbers series for bank accounts on the **General Ledger Setup** page.

### To create a contact as a customer, vendor, or bank account
   1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Contacts**, and then choose the related link.
   2. Select the contact you want to create as a customer, vendor, or bank account.
   3. Choose the **Create As** action, and then choose either **Customer**, **Vendor**, or **Bank**.
   4. Confirm the subsequent message.

   The contact information is transferred from the **Contact** card to the **Bank Account** card, the **Customer** card, or the **Vendor** card. You may want to add specific information to each of the cards, such as invoicing and payment details.

## Setting Up Business Relations on Contact Companies
You can use business relations to indicate the business relationship you have with your contacts, for example, a prospect, bank, consultant, service supplier, and so on.

Using business relations on contacts is a two-step process. First, you define the business relation code. You only have to perform this step one time for each business relation. Once you have a business relation code, you can start to assign the code to contact companies.

> [!NOTE]  
>   If you plan to synchronize your contacts with vendors, customers, or bank accounts in other parts of the application, you may want to set up a business relation for them.

### To define a business relation code
The business relation code defines a category or type of the business relationship, such as BANK or Law. You can have several business relation codes. To define the business relation, you use the **Business Relations** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Relations**, and then choose the related link.
2. Choose the **New** action, and fill in a code and description. The code can be a maximum of 11 characters, and can be any combination of numbers and letters.

### <a name="AssignBusRelContact"></a> To assign business relations to a contact
You cannot assign business relations to a contact person - only companies.

1. Open the contact.
2. Choose the **Company** action, and then the **Business Relations** action.

    The **Contact Business Relations** page opens.
3. In the **Business Relation Code** field, select the business relation you want to assign.

Repeat these steps to assign as many business relations as you want. You can also assign business relations from the contact list by following the same procedure.

The number of business relations you have assigned to the contact is displayed in the **No. of Business Relations** field in the **Segmentation** section on the **Contact** page.

After you have assigned business relations to your contacts, you can use this information to select contacts for your segments. For more information, see [Add Contacts to Segments](marketing-add-contact-segment.md).

## See Also
[Creating Contact Persons](marketing-create-contact-persons.md)   
[Working with Business Central](ui-work-product.md)
