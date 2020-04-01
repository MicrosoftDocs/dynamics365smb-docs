---
title: Using the QuickBooks Migration Extension | Microsoft Docs
description: Describes how to use the extension to migrate customers, vendors, items, and accounts from QuickBooks Online to Business Central.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: extension, migrate, data, QuickBooks, import
ms.date: 04/01/2020
ms.author: bholtorf

---

# The QuickBooks Online Data Migration Extension
This extension is included in the **Data Migration** assisted setup guide to help you migrate important business data from QuickBooks Online to [!INCLUDE[d365fin](includes/d365fin_md.md)]. For example, this is useful when your business is growing, and you've decided to upgrade your business management app by starting to use [!INCLUDE[d365fin](includes/d365fin_md.md)].

## What data can I import from QuickBooks Online?
You can import the following data from QuickBooks Online to [!INCLUDE[d365fin](includes/d365fin_md.md)]:  

* Customers
* Vendors
* Items
* Chart of accounts
* Beginning balance transaction in the general ledger
* On-hand quantities for inventory items
* Open documents for customers and vendors, such as invoices, credit memos, and payments

We migrate only full amounts on sales and purchase documents. We do not update partially paid amounts. For example, if a customer has paid 300 of a total of 500 dollars on a sales invoice, we migrate the full 500. If you have received partial payments, you must update these manually, either before or after you migrate data. We recommend that you apply outstanding transactions before you migrate, just to make things easier afterward.

> [!NOTE]  
>   We do not migrate purchase orders or sales orders.

## Before you start
An important part of the migration process is to specify the accounts to migrate transactions to. It's a good idea to plan this mapping before you migrate data. For example, the accounts where you post transactions for:  

* The sale of items or services to customers.
* The purchase of items or services from vendors.  
* Adjustments in the general ledger.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] requires that general ledger accounts have account numbers assigned to them. Make sure that account numbers are assigned to your accounts in QuickBooks Online.

If transactions in QuickBooks Online have tax amounts, you must set up a tax account for your tax jurisdictions in [!INCLUDE[d365fin](includes/d365fin_md.md)] before you can post transactions.

## How do I start using the extension?
Getting started is easy. All you need to do is run the **Data Migration** assisted setup guide. Here's how:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose **Migrate business data**.
2. Follow the instructions on each step in the assisted setup guide.

## What do I do after I migrate data?
After you migrate data, transactions have the status **Unposted**, so you can review them and make adjustments. To review the transactions, go to the page where you would normally find them. For example, to review unposted sales invoices, go to the **Sales Invoices** page. To review payment journals, go to the **Payment Journals** page.   

There are a few things in particular that you should do:

* If the transactions in QuickBooks Online had markup or discount amounts, you must manually add the amounts to the related transactions in [!INCLUDE[d365fin](includes/d365fin_md.md)] before you post them.
* If you are using value added tax (VAT), you may need to add a business posting group and a product posting group to the posting setup so that you can post VAT amounts.
* Verify the beginning balances for accounts in the general ledger. QuickBooks Online does not store the current balance for all accounts, so you might need to correct beginning balances.

## See Also
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
