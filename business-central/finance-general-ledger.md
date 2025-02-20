---
title: Understand the general ledger and Chart of Accounts
description: Describes the general ledger, chart of accounts, and account categories. Use the General Ledger Setup page to specify handling accounting issues in your company.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: analysis, history, track
ms.search.form: 18, 20_Primary, 37, 65, 99, 312, 314, 313, 395, 552, 569, 570, 634, 790, 791, 1158
ms.date: 08/06/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Understand the general ledger and Chart of Accounts

The general ledger (G/L) stores your financial data, and the chart of accounts (COA) shows the accounts that you post general ledger entries to. [!INCLUDE[prod_short](includes/prod_short.md)] includes a standard chart of accounts that's ready to support your business.

## General ledger setup and general posting setup

The setup of the general ledger is at the core of financial processes because it defines how you post data. Two pages in particular play an important part in configuring your finance processes:  

* **General Ledger Setup**
* **General Posting Setup**

### The **General Ledger Setup** page

Use the **General Ledger Setup** page to specify how to handle certain accounting issues in your company, such as:  

* Invoice rounding details  
* Address formats  
* Financial reporting

> [!TIP]
> The **General Ledger Setup** page includes generic fields, and fields that are particular to your country or region. If you're unsure of the meaning of a field, we suggest you work with your accountant to determine whether it's relevant to your organization. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

To open the page now, use the following link [General Ledger Setup](https://businesscentral.dynamics.com/?page=118).

### The **General Posting Setup** page

Use the **General Posting Setup** page to set up combinations of general business and general product posting groups. Posting groups map entities such as customers, vendors, items, resources, and sales and purchase documents to general ledger accounts. You fill in a line for each combination of business posting group and product posting group. But you can also open each line in its own posting setup card. Learn more at [Posting Group Setups](finance-posting-groups.md).  

> [!TIP]
> If you can't see the fields you're looking for in the **General Posting Setup** page, use the horizontal scroll bar at the bottom of the page to scroll to the right.  

To open the page now, use the following link [General Posting Setup](https://businesscentral.dynamics.com/?page=314).

## The chart of accounts

The **Chart of Accounts** page shows all general ledger accounts. From the chart of accounts, you can do things like:  

* View reports that show general ledger entries and balances.  
* Close your income statement.  
* Open the general ledger (G/L) account card to add or change settings.  
* See a list of posting groups for that account.
* View separate debit and credit balances for a single account.

To learn more, go to [Understanding the Chart of Accounts](finance-chart-of-accounts.md).

## Account categories

You can personalize the structure of your financial statements by mapping general ledger accounts to account categories.  

The **G/L Account Categories** page shows your categories and subcategories, and the general ledger accounts assigned to them. You can create new subcategories and assign those categories to existing accounts.  

You can create a category group by indenting other subcategories under a line on the **G/L Account Categories** page. Category groups make it easy to get an overview because each grouping shows a total balance. For example, you can create subcategories for different types of assets, then create category groups for fixed assets versus current assets.  

You can define whether specific types of reports must include the accounts in each subcategory. The account categories help define the layout of your financial statements.  

### Example

For example, the default balance statement has a subcategory for *Cash* under *Current Assets*. If you want the balance statement to consider petty cash and checking, take the following steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Account Categories**, then choose the related link.
   1. Alternatively, [open the page here](https://businesscentral.dynamics.com/?page=790).
2. Choose the **Edit List** action.
3. Add two new subcategories: One for petty cash, and one for your checking account:
   1. Select the **Current Assets** category.
   2. Choose the **New** action.
   3. Enter the subcategory name on the **Description** field.
   4. On the **G/L Accounts in Category** field, select the appropriate G/L account.
   5. On the **Additional Report Definition** field, select the **Cash Accounts** option.
4. Indent them under the **Cash** subcategory.
   1. Select the subcategory created in step 3.
   2. Choose the **Indent** action.
   3. Choose the **Move Down** action.
   4. Choose the **Indent** action to indent under the **Cash** subcategory.

When you choose the **Generate Financial Reports** action, or the next time the report is generated, your balance statement shows the following lines:

* Total balance for cash.
* Lines with balances for petty cash and the checking account.  

> [!NOTE]
> If you create a G/L account without assigning an account category, when you assign the account to a posting group [!INCLUDE[prod_short](includes/prod_short.md)] automatically assigns the account category from the G/L account immediately above the account in your chart of accounts. However, to include the new account in your financial reports, you must choose the **Generate Financial Reports** action on the **G/L Account Categories** page. Alternatively, open the G/L Account Card page, specify the account category, and then regenerate your financial report.

## Access to create and edit G/L accounts and account categories

In a small organization, such as the CRONUS demonstration company, most users can edit financial entities such as G/L accounts, account categories, and the chart of accounts, except those users with a TEAM MEMBER license. However, larger organizations typically use roles and permissions to limit access to editing these entities. If you're an administrator, or have the *Business Manager* or *Accountant* role, you can control user permissions to give the right people access to the relevant tables. To learn more, go to [Get an overview of a user's permissions](ui-define-granular-permissions.md#get-an-overview-of-a-users-permissions).  

## Use dimensions to simplify your chart of accounts

Dimensions are values that categorize entries so you can track and analyze them on documents, such as sales orders. Dimensions can, for example, indicate the project or department an entry came from. So, instead of setting up separate general ledger accounts for each department and project, you can use dimensions as a basis for analysis and avoid having to create a complicated chart of accounts.

To learn more about dimensions, go to [Set up default dimensions for customers, vendors, and other accounts](finance-dimensions.md#to-set-up-default-dimensions-for-customers-vendors-and-other-accounts).

## See also

[Understand the chart of accounts](finance-chart-of-accounts.md)  
[Work with Dimensions](finance-dimensions.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Business Intelligence](bi.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
