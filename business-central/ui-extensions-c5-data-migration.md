---
title: Using the C5 data migration extension | Microsoft Docs
description: Use this extension to migrate customers, vendors, items, and general ledger accounts from Microsoft Dynamics C5 2012 to Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: extension, migrate, data, C5, import
ms.search.form: 1860, 1861, 1862, 1863, 1864, 1867, 1868, 1869, 1874, 1882, 1883, 1884, 1885, 1886, 1888, 1890, 1891, 1892, 1893, 1894, 1898, 1899, 1900, 1901, 1902, 1903, 1904, 1905, 1906
ms.date: 12/11/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# The C5 data migration extension

This extension makes it easy to migrate customers, vendors, items, and your general ledger accounts from Microsoft Dynamics C5 2012 to [!INCLUDE[prod_short](includes/prod_short.md)]. You can also migrate historical entries for general ledger accounts.

> [!NOTE]
> The company in [!INCLUDE[prod_short](includes/prod_short.md)] must not contain any data. Additionally, after you start a migration, do not create customers, vendors, items, or accounts until the migration finishes.

## What data is migrated?

The following data is migrated for each entity:

### Customers

* Contacts  
* Location
* Country
* Customer dimensions (department, center, purpose)
* Shipment method
* Sales Person
* Payment terms
* Payment method
* Customer price group
* Customer invoice discount

If you migrate accounts, the following data is also migrated:

* Customer posting setup
* General journal batch
* Open transactions (customer ledger entries)

### Vendors

* Contacts
* Location
* Country
* Vendor dimensions (department, center, purpose)
* Invoice discount
* Shipment method
* Purchaser
* Payment terms
* Payment method
* Vendor invoice discount

If you migrate accounts, the following data is also migrated:

* Vendor posting setup
* General journal batch
* Open transactions (vendor ledger entries)

### Items

* Location
* Country
* Item dimensions (department, center, purpose)
* Sales line discounts
* Customer discount groups
* Item discount groups
* Sales price
* Tariff number
* Units of measure
* Item tracking code
* Customer price group
* Assembly BOMs

If you migrate accounts, the following data is also migrated:

* Inventory posting setup
* General posting setup
* Item journal batch
* Open transactions (item ledger entries)

> [!NOTE]
> If there are open transactions that use foreign currencies, the exchange rates for those currencies are also migrated. Other exchange rates are not migrated.

### Chart of accounts

* Standard dimensions: Department, Cost Center, Purpose  
* Historical G/L transactions  

> [!NOTE]
> Historical G/L transactions are treated a little differently. When you migrate data you set a **Current Period** parameter. This parameter specifies how to process G/L transactions. Transactions after this date are migrated individually. Transactions before this date are aggregated per account and migrated as a single amount. For example, let's say there are transactions in 2015, 2016, 2017, 2018, and you specify January 01, 2017 in the Current Period field. For each account, amounts for transactions on or before December 31, 2016, will be aggregated in a single general journal line for each G/L account. All transactions after this date will be migrated individually.

## File size requirements

The largest file size you can upload to [!INCLUDE[prod_short](includes/prod_short.md)] is 150 MB. If the file you export from C5 is larger than that, consider migrating data in multiple files. For example, export one or two types of entities from C5, such as customers and vendors, to a file, and then export items to another file, and so on. You can import files individually in [!INCLUDE[prod_short](includes/prod_short.md)].

## To migrate data

There are just a few steps to export data from C5, and import it in [!INCLUDE[prod_short](includes/prod_short.md)]:  

1. In C5, use the **Export Database** feature to export the data. Then send the export folder to a compressed (zipped) folder.  
2. In [!INCLUDE[prod_short](includes/prod_short.md)], [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Data Migration**, and then choose **Data Migration**.  
3. Complete the steps in the assisted setup guide. Make sure to choose **Import from Microsoft Dynamics C5 2012** as the data source.  

## Viewing the status of the migration

Use the **Data Migration Overview** page to monitor the success of the migration. The page shows information such as the number of entities that the migration includes, the status of the migration, and the number of items that have been migrated and whether they were successful. It also shows the number of errors, lets you investigate what went wrong and, when possible, makes it easy to go to the entity to fix the issues. For more information, see the next section in this article.  

> [!NOTE]
> While you are waiting for the results of the migration, you must refresh the page to display the results.

## How to avoid double-posting

To help avoid double-posting to the general ledger, the following balance accounts are used for open transactions:  

* For vendors, we use the A/P account from the vendor posting group.  
* For customers, we use the A/R account from the customer posting group.  
* For items, we create a general posting setup where the adjustment account is the account specified as the inventory account on the inventory posting setup.  

## Correcting errors

If something goes wrong and an error occurs, the **Status** field shows **Completed with Errors**, and the **Error Count** field will show how many. To view a list of the errors, you can open the **Data Migration Errors** page by choosing:  

* The number in the **Error Count** field for the entity.  
* The entity, and then the **Show Errors** action.  

On the **Data Migration Errors** page, to fix an error you can choose an error message, and then choose **Edit Record** to view the migrated data for the entity. If you have several errors to fix, you can choose **Bulk-Fix Errors** to edit the entities in a list. You still need to open individual records if the error was caused by a related entry, though. For example, a vendor won't be migrated if an email address one of their contacts has an invalid format.

After you fix one or more errors, you can choose **Migrate** to migrate only the entities you fixed, without having to completely restart the migration.  

> [!TIP]
> If you have fixed more than one error, you can use the **Select More** feature to select multiple lines to migrate. Alternatively, if there are errors that are not important to fix, you can choose them and then choose **Skip Selections**.

> [!NOTE]
> If you have items that are included in a BOM, you might need to migrate more than once if the original item is not created before the variants that reference it. If an item variant is created first, the reference to the original item can cause an error message.  

## Verifying data after migrating

One way to verify that your data migrated correctly is to look at the following pages in C5 and [!INCLUDE[prod_short](includes/prod_short.md)].

|Microsoft Dynamics C5 2012 | Dynamics 365 Business Central| Batch Job to Use |
|---------------------------|------------------------------|------------------|
|Customer Entries| General Journals| CUSTMIGR |
|Vendor Entries| General Journals| VENDMIGR|
|Item Entries| Item Journals| ITEMMIGR |
|G/L Entries| General Journals| GLACMIGR |

## Stopping data migration

You can stop migrating data by choosing **Stop All Migrations**. If you do, all pending migrations are also stopped.

## Related information

[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
