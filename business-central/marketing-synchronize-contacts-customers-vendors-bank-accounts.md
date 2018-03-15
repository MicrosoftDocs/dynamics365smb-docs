---
title: Synchronize Contacts With Customers and Vendors| Microsoft Docs
description: You couple or synchronize contact information of contacts who are also customers, vendors, or bank accounts, so you only update information in one place.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, CRM, integration, couple
ms.date: 06/06/2017
ms.author: edupont

---
# Synchronizing Contacts With Customers, Vendors, and Bank Accounts
If some of your contacts are also customers, vendors, or bank accounts, you can synchronize the contact information with the related customer, vendor, or bank account. Synchronization makes information that is common between contacts and customers, vendors, or bank account the same.  

Before you can synchronize your contacts with customers, vendors, or bank accounts, you must specify a business relation code for customers, vendors, and bank accounts in the **Marketing Setup** window. For more information, see [Setting Up Relationship Management](marketing-setup-marketing.md).

## Different Ways to Synchronize Contacts with Customers, Vendors and Bank Accounts
You can synchronize your contacts with customers, vendors, or bank accounts by three methods:

* Link contacts with existing customers, vendors, or bank accounts from the contact card. For more information, see [Link Contacts With Customers, Vendors, and Bank Accounts](marketing-how-link-contact.md).
* Create customers, vendors, or bank accounts from the contact. For more information, see [Create a Customer, Vendor, or Bank Account From a Contact](marketing-how-create-contacts-new-customers-vendors-bank-accounts.md).
* Create contacts from customers, vendors or bank accounts. For more information, see [Create a company contact from a customer, vendor, or bank account](marketing-how-create-contact-companies.md).

## Consequences of Synchronization
When the contact is synchronized with the customer, vendor, bank account:

* You only have to update information in one place. For example, if you modify the phone number on the contact, the phone number is automatically updated with the same modification on the customer, the vendor, or the bank account.
* If you have specified a number series for contacts, when you create a customer card, a vendor card, or a bank account card, a contact card is automatically created for the customer, vendor or bank account.
* You can create sales quotes and orders, and purchase quotes and orders from the contact.
* You can have your interactions recorded when you perform actions such as printing orders, blanket orders, creating sales service orders, sending e-mails, and so on.
* If you delete a contact linked to a customer, vendor or bank account, only the contact is removed. The customer, vendor, or bank account remains.
* If you delete a customer, vendor, bank account linked to a contact, the contact remains.

> [!NOTE]  
>   Some details, such as invoicing and posting details, do not appear on the contact card. Therefore, you may want to add them manually on the customer card, vendor card, or bank account card when you create contacts as customers, vendors or bank accounts.

## See Also
[Managing Contacts](marketing-contacts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
