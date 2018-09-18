---
title: Migrate Data from Dynamics GP with the Data Migration Extension | Microsoft Docs
description: Use the Dynamics GP Data Migration extension to migrate customers, vendors, inventory items, general ledger accounts, open payables and open receivables transactions from Dynamics GP to Business Central .
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, import, implement
ms.date: 03/29/2017
ms.author: edupont

---
# The Dynamics GP Data Migration Extension for Business Central 
This extension makes it easy to migrate customers, vendors, inventory items, general ledger accounts, open payables and open receivables transactions from Dynamics GP to [!INCLUDE[d365fin](includes/d365fin_md.md)]. If your business uses Dynamics GP today, you can export the relevant records and then open an assisted setup guide to add the data to [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md).

## Exporting Data from Dynamics GP
You must have exported some or all of your existing customers, vendors, inventory items, and general ledger accounts using data export functionality within Dynamics GP. When selecting the data to export the following types can be selected:

* Account  
* Customer  
* Item  
* Vendor  

When the export file is created you will have a zip file that contains several txt files that will be determined by what you selected during the export data process.  There will also be additional txt files that are generated that contain supporting information needed for setup within your new [!INCLUDE[d365fin](includes/d365fin_md.md)] company.

The Dynamics GP Data Migration extension automatically maps the exported data so that your data is quickly available to you in your new [!INCLUDE[d365fin](includes/d365fin_md.md)] company. 

## What's New in the Fall Release

With the Fall Relase we have expanded the amount of data we bring into [!INCLUDE[d365fin](includes/d365fin_md.md)] from Dynamics GP.

Within the migration wizard you now can choose how you want your Dynamics GP chart of accounts to migrate across.  You can migrate the existing chart of accounts or you can create a new chart of accounts based off the existing chart of accounts.

If you choose to use the existing chart of accounts, the accounts will be set up as the main account segment from Dynamics GP and the additional segments will be setup as dimensions within [!INCLUDE[d365fin](includes/d365fin_md.md)].  

If you choose to create a new chart of accounts, you will get an additional account info page in the wizard that gives you the ability to download the workbook and import the workbook to change your accounts.


You will need to download the excel workbook and map a new account number to each account number within the excel spreadsheet, each account will be required to have its own number, or the migration will error.  Once the workbook has been completed you can continue walking through the migration wizard by importing the excel workbook you just updated.  The wizard will validate that each row has a unique Account Number and that no rows have an empty new account number in them.
With the change to the mapping of the chart of account options the user will also notice a change to the type of data that comes across into the general journal for the account numbers.  
•	If you choose to use the existing account numbers, we will bring over the beginning balance of the main segment (new account number) as a summation of the main account number at the time of the migration.  
•	If you choose to create new account numbers, we will bring over 2 “years” worth of summary information based on the fiscal periods you have setup within Dynamics GP.
Previously on Customers and Vendors we migrated a summary transaction for the customer/vendor balance within Dynamics GP.  Now we will be bringing in the detail open transactions for customers and vendors at the time of the migration.  What does this mean?  If your customer has 3 outstanding transactions within the receivables module we will bring those transactions into Business Central with the outstanding amount as the document amount.  This is the same for the payables module for vendors.
Inventory items will be brought into the system with the cost valuation method that was selected when the company setup wizard was run.  Service items will automatically be assigned the FIFO valuation method.   Currently we bring in the Quantity on Hand for the items at the time of migration.  This quantity is brought into the blank location.  
The last option you will see within the Data Migration wizard for Dynamics GP is the ability to specify your posting option.  This option will allow you to choose to automatically post all the transactions in the general journals as soon as the migration moves the data into Business Central or you can choose to post manually meaning all the transactions will sit in batches inside the General Journal page so you can verify the information before you post.  This option is visible on the Chart of Accounts options page.


## See Also
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions ](ui-extensions.md)  
