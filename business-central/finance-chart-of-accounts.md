---
title: Understanding the Chart of Accounts
description: Describes the chart of accounts, how to set it up, and how to use it.
author: kennienp
ms.topic: concept-article
ms.search.keywords: analysis, history, track
ms.search.form: Report_1, 18, 20, 37, 65, 99_Primary, 312, 314, 313, 395, 552, 569, 570, 634, 790, 791, 1158
ms.date: 08/20/2025
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
---

# Understanding the Chart of Accounts

A chart of accounts (COA) serves as a comprehensive directory of financial accounts and their corresponding reference numbers. A COA typically has of two main categories of accounts:

* Balance sheet accounts: These accounts track your company’s assets, debts, and net worth.
* Income statement accounts: These accounts record income from various sources and also track expenses.

Balance sheet accounts are further categorized into three groups:

* Asset accounts: These accounts track all the valuable resources owned by your company.
* Liability accounts: They record your company’s debts.
* Equity accounts: Represent the residual value in the business after subtracting liabilities from assets.

Income accounts are divided into two groups:

* Revenue accounts: These accounts capture your company’s income from various sources.
* Expense accounts: These accounts capture all your company’s expenses.

Use the COA to record transactions in your organization’s general ledger. Each account typically has an identifier (account number) and a descriptive caption or header, and they're systematically coded based on their account type.

[!INCLUDE[prod_short](includes/prod_short.md)] includes a standard chart of accounts that is ready to support your business.

The composition of your company’s chart of accounts is a strategic decision made by your management (or by country-specific regulation). It varies based on your company’s industry, business model, and financial structure. For instance, depending on your industry, you might have specific asset accounts tailored to your company's unique operations and needs:

* A retail business might emphasize inventory and accounts receivable.
* A technology company might focus on intangible assets like patents and software.
* A manufacturing plant would track fixed assets and supplies.

## The chart of accounts page

The chart of accounts shows all general ledger accounts. From the chart of accounts, you can do things like:  

* View reports that show general ledger entries and balances.  
* Close your income statement.  
* Open the General Ledger Account Card, where you can add or change settings.  
* See a list of posting groups for that account.
* View separate debit and credit balances for a single account.

You can add, change, or delete general ledger accounts. However, to prevent discrepancies, you can't delete a general ledger account if its data is used in the chart of accounts. Also, you can block the accidental deletion of accounts in sensitive periods. To learn more about protecting accounts from deletion, go to [Deleting accounts](finance-setup-chart-accounts.md#delete-accounts).  

## The code hierarchy in G/L accounts

Businesses typically create a hierarchical structure in G/L account codes to reflect where they belong in the chart of accounts. For instance, in some implementations, G/L account codes that start with **1** denotes asset accounts, whereas G/L account codes that start with 3 denotes equity accounts. In some regions, there are local regulations for using a standard chart of accounts. To help users understand this hierarchy without the need to know the internal code structure, you can define headers and subtotals in your chart of accounts that encapsulate these internal structures.

## Designing your chart of accounts

Each line in the chart of accounts is a G/L account of one of the types:

* Posting (journals can post lines to these accounts)
* Heading (defines an overall heading in the chart of accounts)
* Total (defines a formula for a subtotal in the chart of accounts)
* Begin-Total (defines a beginning heading for a subtotal in the chart of accounts. All subsequent lines until an End-Total line are indented)
* End-Total (defines an ending heading for a subtotal and the formula for it in the chart of accounts. All subsequent lines after this End-Total line are outdented)

A minimalist chart of accounts can consist of only lines of posting accounts. You use the other four types to define how the chart of accounts also shows a financial statement with headers and subtotals. Totaling accounts are frequently used in financial reporting.

> [!TIP]
> If you use account types other than **Posting** in your chart of accounts, you can define different views to show the "raw" posting accounts without the reporting-type account types for totalling and headings. For example, Show only posting accounts and Hide blocked accounts.

## Use dimensions to simplify your chart of accounts

Dimensions are values that categorize entries so you can track and analyze them on documents, such as sales orders. Dimensions can, for example, indicate the project or department an entry came from. So, instead of setting up separate general ledger accounts for each department and project, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts.

To learn more about dimensions, go to [Work with Dimensions](finance-dimensions.md).

## Organize general ledger (G/L) data using account categories

The **G/L Account Categories** page lets you create simple financial reports based on your chart of accounts.  

By providing categories, subcategories, and account mapping to your chart of accounts, [!INCLUDE [prod_short](includes/prod_short.md)] includes basic financial reporting out of the box. If you're just getting started with financial reporting, the standard reports are excellent options until you become more experienced.

For more information, see [Organize general ledger (G/L) data using account categories](bi-account-categories.md).

## Get a quick overview of your finances

The **Chart of Accounts** page displays accounts in a hierarchical list that offers fast access to the key information for each account. However, the list is static, and if you have many accounts, you might have to scroll to view different accounts. If you just want a quick overview of the basics, such as net changes and balances, the **Chart of Accounts Overview** page is a useful alternative. The column layout on the page is the same as the **Chart of Accounts** page (though with fewer columns), so it's easy to understand. You can expand or collapse the hierarchical levels. To make it easy to switch between the pages, the **Chart of Accounts Overview** page is available from the **Chart of Accounts** page.

## Find out where a general ledger account is used in setup tables

When you set up [!INCLUDE [prod_short](includes/prod_short.md)], you fill in setup tables (for example, the posting group tables) to specify which G/L account is used as posting accounts for which types of transactions.

The **Chart of Accounts** and **G/L Account Card** pages offer a **Where-Used** action that opens an overview of which setup tables use the selected G/L account.

Each line refers to one line in a setup table. The page can list several lines from the same setup table if, for example, the account is used for more than one posting group code in a posting setup table.

You can review details for a line by choosing the **Show Details** action.

## Access to create and edit the chart of accounts

In a small organization, such as the CRONUS demonstration company, most users can edit the chart of accounts, except those users with a TEAM MEMBER license. However, larger organizations typically use roles and permissions to limit access to editing the chart of accounts. If you're an administrator, or have the Business Manager or Accountant role, you can control user permissions to give the right people access to the relevant tables. To learn more, go to [Get an overview of a user's permissions](ui-define-granular-permissions.md#get-an-overview-of-a-users-permissions).  

## Audit changes to G/L accounts setup

You can use the Change Log feature to capture changes users make to your G/L accounts. [!INCLUDE [include-audit-what-who-when](includes/include-audit-what-who-when.md)] 

The following table lists the table for G/L accounts and its ID.

| Table | Table ID |
| ----- | -------- |
| G/L Account | 15 |

[!INCLUDE [include-audit-changes-to-setup-learn-more-link](includes/include-audit-changes-to-setup-learn-more-link.md)]



<!-- ## Standard chart of accounts in different regions
Uncomment when we have more examples added to our localization documentation

Some regions have defined standards for the chart of accounts structure you should use in your company. 

Here are some examples of such standards that have been implemented in localized versions of [!INCLUDE[prod_short](includes/prod_short.md)]:

* [Standard chart of accounts in Denmark](localfunctionality/denmark/how-to-set-up-standard-coa.md)
-->

## Chart of accounts best practices

Here are some best practices that you might consider when you develop and maintaining your charts of accounts:

* Compose your company’s chart of accounts to support the financial reporting needs for your management to take strategic decisions.
* Consider starting simple with fewer G/L accounts. You can always add more detailed accounts if needed.
* Define headers and subtotals in your chart of accounts that summarize the internal structures in G/L accounts.
* Use dimensions to simplify your chart of accounts. Don't have specific G/L accounts for each product or department.
* Add new G/L accounts as they come in, but remove accounts from your chart of accounts only during period-end of your finance period.

## Related information

[Set Up or Changing the Chart of Accounts](finance-setup-chart-accounts.md)    
[Organize general ledger (G/L) data using account categories](bi-account-categories.md)   
[Understand the general ledger](finance-general-ledger.md)  
[Financial analytics](bi.md)    
[Finance overview](finance.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
