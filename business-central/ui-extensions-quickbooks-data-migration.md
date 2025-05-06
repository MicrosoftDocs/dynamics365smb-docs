---
title: QuickBooks Data Migration Extension
description: Describes how to use the extension to import customers, vendors, items, and accounts from QuickBooks Desktop to Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: app, add-in, manifest, customize, import, implement
ms.search.form: 1911, 1912, 1913, 1914, 1915, 1916, 1918, 1919
ms.date: 06/24/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# The QuickBooks Data Migration Extension

This extension makes it easy to migrate customers, vendors, items, and accounts from QuickBooks to [!INCLUDE[prod_short](includes/prod_short.md)]. If your business uses QuickBooks today, you can export the relevant information and then open an assisted setup guide to upload the data to [!INCLUDE[prod_short](includes/prod_short.md)].  
For more information, see [Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md).

## Data from QuickBooks desktop

You can import the following data from QuickBooks Online to Business Central:

- Customers  
- Vendors  
- Items  
- Chart of Accounts  
- Beginning Balance transactions in General Ledger  
- On-hand Quantities for Inventory Items  
- Open documents for customers and vendors, such as invoices, credit memos and payments  

We migrate only full amounts on sales and purchase documents. We do not update partially paid amounts. For example, if a customer has paid 300 of a total of 500 dollars on a sales invoice, we migrate the full 500. If you have received partial payments, you must update these manually, either before or after you migrate data. We recommend that you apply outstanding transactions before you migrate, just to make things easier afterward.

> [!NOTE]
> We do not migrate purchase orders or sales orders.

## Before you start

An important part of the migration process is to specify the accounts to migrate transactions to. It's a good idea to plan this mapping before you migrate data. For example, the accounts where you post transactions for:

- The sale of items or services to customers  
- The purchase of items or services from vendors  
- Adjustments in the general ledger  

Business Central requires that general ledger accounts have account numbers assigned to them. Make sure that account numbers are assigned to your accounts in QuickBooks.
If transactions in QuickBooks have tax amounts, you must set up a tax account for your tax jurisdictions in Business Central before you can post transactions.

In order to get your data out of the QuickBooks desktop application you will need to download the Microsoft Data Exporter Tool.  The instructions for the tool are in the Data Migration Wizard in [!INCLUDE[prod_short](includes/prod_short.md)]. The tool will connect to your QuickBooks application and export the applicable data to a .zip file.  

> [!NOTE]
> Currently the data exporter tool only works with QuickBooks 2017 and 2018.

## Finding the QuickBooks data migration extension

The QuickBooks Data Migration extension is installed and ready to go as an integrated part of the Data Migration assisted setup guide. If you are ready to get started now, and have exported your data from QuickBooks, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link. Choose **Migrate business data**, and then follow the steps in the guide.  

## What do I do after I migrate data?

After you migrate data, transactions have the status Unposted, so you can review them and make adjustments. To review the transactions, go to the page where you would normally find them. For example, to review unposted sales invoices, go to the Sales Invoices page. To review payment journals, go to the Payment Journals page.
There are a few things in particular that you should do:
If the transactions in QuickBooks had markup or discount amounts, you must manually add the amounts to the related transactions in Business Central before you post them.
If you are using value added tax (VAT), you may need to add a business posting group and a product posting group to the posting setup so that you can post VAT amounts.
Verify the beginning balances for accounts in the general ledger. QuickBooks does not store the current balance for all accounts, so you might need to correct beginning balances.

## Related information

[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
