---
title: Learn About General Ledger and COA| Microsoft Docs
description: Describes the general ledger, the chart of accounts, and account categories.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.date: 04/01/2020
ms.author: edupont

---
# Understanding the General Ledger and the COA
The general ledger stores your financial data, and the chart of accounts shows the accounts that all general ledger entries are posted to. [!INCLUDE[d365fin](includes/d365fin_md.md)] includes a standard chart of accounts that is ready to support your business.

## General Ledger Setup and General Posting Setup
The setup of the general ledger is at the core of financial processes because it defines how you post data.  

On the **General Ledger Setup** page, you specify how to handle certain accounting issues in your company, such as:  

* Invoice rounding details  
* Address formats  
* Financial reporting  

Similarly, on the **General Posting Setup** page, you specify how you want to set up combinations of general business and general product posting groups. Posting groups map entities like customers, vendors, items, resources, and sales and purchase documents to general ledger accounts. You fill in a line for each combination of business posting group and product posting group. For more information, see [Posting Group Setups](finance-posting-groups.md)  

## The Chart of Accounts
The chart of accounts shows all general ledger accounts. From the chart of accounts, you can do things like:  

* View reports that show general ledger entries and balances.  
* Close your income statement.  
* Open the G/L account card to add or change settings.  
* See a list of posting groups that post to that account.
* View separate debit and credit balances for a single account  

You can add, change, or delete general ledger accounts. However, to prevent discrepancies, you can't delete a general ledger account if it's data is used in the chart of accounts.  

## Account Categories
You can personalize the structure of your financial statements by mapping general ledger accounts to account categories.  

The **G/L Account Categories** page shows your categories and subcategories, and the G/L accounts that are assigned to them. You can create new subcategories and assign those categories to existing accounts.  

You create a category group by indenting other subcategories under a line on the **G/L Account Categories** page. This makes it easy for you to get an overview, because each grouping shows a total balance. For example, you can create subcategories for different types of assets, and then create category groups for fixed assets versus current assets.  

You can specify whether the accounts in each subcategory must be included in specific types of reports. The account categories help define the layout of your financial statements.  

For example, the default balance statement has a subcategory for Cash under Current Assets. If you want the balance statement consider petty cash and checking, you can:  

1. Add two new subcategories. One for petty cash, and one for your checking account.  
2. Specify the additional report definition **Cash Accounts** for these subcategories.  
3. Indent them under the **Cash** subcategory.  

The next time you generate account schedules your balance statement will show a total balance for cash and two lines with balances for petty cash and the checking account.  

## See Also
[Finance](finance.md)  
[Setting Up or Changing the Chart of Accounts](finance-setup-chart-accounts.md)  
[Business Intelligence](bi.md)  
