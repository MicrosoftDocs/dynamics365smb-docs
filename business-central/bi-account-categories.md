---
title: Organize report data using account categories
description: Learn how to categorize general ledger accounts for reporting purposes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 07/11/2024
ms.custom: bap-template
ms.search.keywords: bi, power BI, analysis, KPI, account schedule, financial report
ms.search.form: 108, 490, 790
ms.service: dynamics-365-business-central
---

# Organize report data using account categories

The **G/L Account Categories** page lets you create simple, out of the box financial reports based on your chart of accounts.  

By identifying categories, subcategories, and providing account mapping to your chart of accounts, Business Central includes basic financial reporting out of the box. If you do not yet have established financial reporting, choose this option. 

## Use G/L account categories 

By designating the Account Category for each general ledger account, the first layer of financial reporting is created. You can use six categories: 

* Assets
* Liabilities
* Equity
* Income
* Cost of Goods
* Expense 

These can be designated on the G/L Account Card or on the G/L Account Categories page. Their purpose is to identify the major sections of primary financial reports like the Balance Sheet and Income Statement.  

## Use account subcategories

Subcategories can also be identified for each account to aid in mapping more detail for accounts in each category. The subcategories can also be designated on the G/L Account Card or on the G/L Account Categories page. Their purpose is to identify the subsections of primary financial reports like the Balance Sheet and Income Statement. Subcategories are more flexible than categories and can be defined by the user.  

## Map general ledger accounts

The most important feature of the out-of-the-box financial reports is mapping of the GL Accounts to the Category. Every account in the chart of accounts should be listed in the selected category and subcategory so the automated generation of financial reports will include all mapped accounts.  

## Generate financial reports

Once the categories and subcategories have been set up, and all accounts on the chart of accounts have been mapped, choose Generate Financial Reports. This action will be run briefly and financial reports with the M- prefix will be updated with the mapping provided to your chart of accounts.  

To control which reports are updated when generate financial reports is run, update the fields in the reporting section of the general ledger setup.  

These reports can be remapped or updated at any time. If you choose to regenerate them at any time, you may choose to keep the original reports and create copies with the new mapping.

Keep in mind that if you decide to manually make changes to any of these system generated reports, you will get the following message.  

## See also