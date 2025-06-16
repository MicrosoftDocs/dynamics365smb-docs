---
title: Consolidate Balances for a Company that is a Customer and a Vendor
description: Describes how to consolidate balances for a customer that is also a vendor.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment process, cash receipt
ms.search.form: 5052, 21, 5050 
ms.date: 06/27/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Consolidate Balances for a Company that is a Customer and a Vendor
A company that you do business with might be both a customer and a vendor. When that's the case, you can avoid making unnecessary payments or receipts, and perhaps save on transaction fees, by consolidating the company's customer and vendor balances. Consolidation compares the company's balances as a vendor and as a customer, and then nets the amount so that that either the customer or vendor balance remains, depending on which amount was higher. 

To consolidate the balances, you must first link the customer and vendor companies through a contact that has the type **Company**. A customer or vendor can only have one contact of the type **Company**. For more information, see [Create Contacts](marketing-create-contact-companies.md).

After you link the companies, the **Customer Card** page offers the **Balance as Vendor** field, and the **Vendor Card** page includes the **Balance as Customer** field.

Though it's not a requirement, the customer and vendor companies are typically the same legal entity. 

## Before you start
Before you consolidate balances, specify a few settings on the **Marketing Setup** page. 

* On the **Interactions** FastTab, you must specify business relation codes in the **Customers** and **Vendors** fields. [!INCLUDE[prod_short](includes/prod_short.md)] uses this information to determine the type of relation to display for contacts. 
* Optional: On the **Duplicates** FastTab, turn duplicate search on or off. By default, duplicate search is turned on. For more information, see [Handling duplicates](#handling-duplicates). 

## Link an existing customer and vendor company through a contact
The following steps describe how to link a customer and a vendor through a contact.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer** or **Vendor**, and then choose the related link.
2. Choose the customer or vendor, and then choose the **Contact** action.   
3. Choose the contact, and then choose the **Link with existing** action.
4. Choose the type of entity to create a business relation with.
5. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Create a vendor from a customer, or vice versa
You can create a new vendor from an existing customer, or a new customer from a vendor. From the **Customer** or **Vendor** pages, open the **Contact** page. Choose the **Create as** action, and then either the **Customer** or **Vendor** options. 

## Create a new customer or vendor and link them through a vendor or customer contact
1. Create a new customer or vendor. For more information, see [Register New Customers](sales-how-register-new-customers.md).
2. After you set up the customer or vendor, choose the **Create** action, and then choose either the **Customer** or **Vendor** options. 

## To consolidate the customer and vendor balances for a contact company
On the **Payment Journal** page, use the **Net Customer/Vendor Balances** action to consolidate the customer and vendor balances into a single net amount. The action creates, but doesn't post, payment journal lines that contain the net balances.

> [!NOTE]
> If the customer or vendor balances contain amounts that are in different currencies, a line is created for the amount in each currency.

## Handling duplicates
If you turn on duplicate search on the **Duplicates** FastTab on the **Marketing Setup** page, a warning will display when you change the values of fields that are part of the setup for duplicate search strings. When a duplicate is found, you can take the following actions:

* Combine the duplicate contacts into a single contact that is the same for both the customer and vendor by using the **Merge With** capability on the **Contact Card** page. Typically, merging contacts is done only when the customer and vendor are the same legal entity. For more information, see [Merge Duplicate Records](sales-how-merge-duplicate-records.md). 
* Delete the vendor business relation for the vendor or customer contact, and then use the **Link to Existing** action to link to a different contact.    

## Related information
[Sales](sales-manage-sales.md)  
[Register New Customers](sales-how-register-new-customers.md)  
