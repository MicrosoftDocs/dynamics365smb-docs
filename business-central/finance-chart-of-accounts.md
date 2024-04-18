---
title: Understanding the Chart of Accounts
description: Describes the chart of accounts, how to set it up, and how to use it.
author: kennienp
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: analysis, history, track
ms.search.form: 18, 20, 37, 65, 99, 312, 314, 313, 395, 552, 569, 570, 634, 790, 791, 1158
ms.date: 04/17/2024
ms.author: kepontop

ms.service: dynamics-365-business-central
---

# Understanding the Chart of Accounts (COA)

A chart of accounts (COA) serves as a comprehensive directory of financial accounts and their corresponding reference numbers. These accounts are categorized into groups such as assets, liabilities, equity, revenue, and expenses. The COA is essential for recording transactions in an organization’s general ledger. Each account may have an associated identifier (account number) and a descriptive caption or header, and they are systematically coded based on their account type.

[!INCLUDE[prod_short](includes/prod_short.md)] includes a standard chart of accounts that is ready to support your business.


## !!! TODO !!!

This is how Netsuite discusses the Chart of Accounts:

https://www.netsuite.com/portal/resource/articles/accounting/chart-of-accounts.shtml

Maybe we can get inspired and improve our article?


## The chart of accounts page

The chart of accounts shows all general ledger accounts. From the chart of accounts, you can do things like:  

* View reports that show general ledger entries and balances.  
* Close your income statement.  
* Open the general ledger (G/L) account card to add or change settings.  
* See a list of posting groups for that account.
* View separate debit and credit balances for a single account.

You can add, change, or delete general ledger accounts. However, to prevent discrepancies, you can't delete a general ledger account if its data is used in the chart of accounts. Also, starting with 2022 release wave 2, you can also block the accidental deletion of accounts in sensitive periods. Learn more in the [Deleting accounts](finance-setup-chart-accounts.md#delete-accounts) section.  


## Designing your chart of accounts

Each line in the chart of accounts is a G/L account of one of the types
* Posting (journals can post lines to this accounts)
* Heading (defines an overall heading in the chart of accounts)
* Total (defines a formula for a subtotal in in the chart of accounts)
* Begin-Total (defines a beginning heading for a subtotal in in the chart of accounts. All subsequent lines until an End-Total line are indented)
* End-Total (defines a ending heading for a subtotal and the formula for it in in the chart of accounts. All subsequent lines after this End-Total line are outdented)

A mimimalist chart of accounts can consist of only lines of posting accounts. You use the other four types to define how the chart of accounts also show a financial statement with headers and subtotals. Totalling accounts are also frequently used in financial reporting.

> [!TIP]
> If you use account types other than of type *Posting* in your chart of accounts, you can define different views such as *Show only posting accounts* and *Hide blocked accounts* to be able to see the "raw" posting accounts without the reporting-type account types for totalling and headings.


## Get a quick overview of your finances

The **Chart of Accounts** page displays accounts in a hierarchical list that offers fast access to the key information for each account. However, the list is static, and if you have many accounts, you might have to scroll to view different accounts. If you just want a quick overview of the basics, such as net changes and balances, the **Chart of Accounts Overview** page is a useful alternative. The column layout on the page is now the same as you'll find on the **Chart of Accounts** page (though with fewer columns), so you won't have to reorient yourself. You can expand or collapse the hierarchical levels to condense the view. To make it easy to switch between the pages, the **Chart of Accounts Overview** page is available from the **Chart of Accounts** page.


## Access to create and edit the chart of accounts

In a small organization, such as the CRONUS demonstration company, most users can edit the chart of accounts, except those users with a TEAM MEMBER license. However, larger organizations typically use roles and permissions to limit access to editing the chart of accounts. If you're an administrator, or have the *Business Manager* or *Accountant* role, you can control user permissions to give the right people access to the relevant tables. Learn more in the [Get an overview of a user's permissions](ui-define-granular-permissions.md#get-an-overview-of-a-users-permissions) section.  


## See also

[Set Up or Changing the Chart of Accounts](finance-setup-chart-accounts.md)  
[Understand the general ledger](finance-general-ledger.md)
[Financial analytics](bi.md)  
[Finance overview](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
