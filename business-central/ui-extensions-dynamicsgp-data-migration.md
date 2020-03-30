---
title: Migrate Data from Dynamics GP with the Data Migration Extension | Microsoft Docs
description: Use the Dynamics GP Data Migration extension to migrate customers, vendors, inventory items, general ledger accounts, open payables and open receivables transactions from Dynamics GP to Business Central.

documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, import, implement
ms.date: 04/01/2020
ms.author: edupont

---
# The Dynamics GP Data Migration Extension 
This extension makes it easy to migrate customers, vendors, inventory items, general ledger accounts, open payables and open receivables transactions from Dynamics GP to [!INCLUDE[prodshort](includes/prodshort.md)]. If your business uses Dynamics GP today, you can export the relevant records and then open an assisted setup guide to add the data to [!INCLUDE[prodshort](includes/prodshort.md)]. The migration extension works for all supported versions of Microsoft Dynamics GP. For more information, see [Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md).

> [!NOTE]
>  This extension will be deprecated in the 15.3 update. We recommend that users who want to migrate from Dynamics GP start using the **Cloud Migration** wizard instead. The **Cloud Migration** extension has more robust functionality and brings more data into Business Central from Dynamics GP.

## Exporting Data from Dynamics GP
You must have exported some or all of your existing customers, vendors, inventory items, and general ledger accounts using data export functionality within Dynamics GP. When selecting the data to export the following types can be selected:

* Account  
* Customer  
* Item  
* Vendor  

When the export file is created you will have a zip file that contains several txt files that will be determined by what you selected during the export data process.  There will also be additional txt files that are generated that contain supporting information needed for setup within your new [!INCLUDE[prodshort](includes/prodshort.md)] company.

The Dynamics GP Data Migration extension automatically maps the exported data so that your data is quickly available to you in your new [!INCLUDE[prodshort](includes/prodshort.md)] company.

## What's New in the October 2018 Release

In this version, we have expanded the amount of data we bring into [!INCLUDE[prodshort](includes/prodshort.md)] from Dynamics GP.

In the migration wizard, you can now choose how you want to migrate the Dynamics GP chart of accounts. You can migrate the existing chart of accounts, or you can create a new chart of accounts based on the existing chart of accounts.  

If you choose to use the existing chart of accounts, the accounts will be set up as the main account segment from Dynamics GP and the additional segments will be setup as dimensions within [!INCLUDE[prodshort](includes/prodshort.md)].  

If you choose to create a new chart of accounts, you will get an additional account information page in the wizard so that you can download the workbook, make the relevant changes, and then import the workbook again to change your accounts.  

You will have to download the Excel workbook and map a new account number to each account number in the Excel spreadsheet. Each account will be required to have its own number, or the migration will error. When you have completed the mapping, you can continue through the migration wizard by importing the Excel workbook that you just updated. The wizard will validate that each row has a unique account number and that no rows have an empty new account number in them.  

With the change to the mapping of the chart of account options, you will also note a change to the type of data that comes across into the general journal for the account numbers.  

- If you choose to use the existing account numbers, we will bring over the beginning balance of the main segment (new account number) as a summation of the main account number at the time of the migration.  
- If you choose to create new account numbers, we will bring summary information for the equivalent of two fiscal years based on the fiscal periods you have set up in Dynamics GP.

In earlier versions of [!INCLUDE[prodshort](includes/prodshort.md)], the wizard migrated a summary transaction for the customer/vendor balance in Dynamics GP. Now we bring in the detailed open transactions for customers and vendors at the time of the migration. What does this mean? If your customer has 3 outstanding transactions registered in the Receivables module, the wizard brings those transactions into [!INCLUDE[prodshort](includes/prodshort.md)] with the outstanding amount as the document amount. This is the same for the Payables module for vendors.  

Inventory items are imported with the cost valuation method that was selected when the company setup wizard was run. Service items are automatically assigned the FIFO valuation method. Currently we bring in the Quantity on Hand for the items at the time of migration.  This quantity is brought into the blank location.  

The last option you see in the Data Migration wizard for Dynamics GP is the ability to specify your posting option. This setting specifies if you want to automatically post all transactions in the general journals as soon as the migration moves the data into [!INCLUDE[prodshort](includes/prodshort.md)], or if you want to post manually so that all transactions will sit in batches inside the General Journal page so you can verify the information before you post. This option is visible on the Chart of Accounts options page.


## See Also
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Customizing [!INCLUDE[prodshort](includes/prodshort.md)] Using Extensions ](ui-extensions.md)  
