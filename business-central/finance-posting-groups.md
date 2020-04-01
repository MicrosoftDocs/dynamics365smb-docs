---
title: Posting Group Setup| Microsoft Docs
description: Overview of the posting groups you can use to save time and avoid mistakes when you post transactions.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting setup, initialize
ms.date: 04/01/2020
ms.author: bholtorf

---
# Setting Up Posting Groups
Posting groups map entities like customers, vendors, items, resources, and sales and purchase documents to general ledger accounts. They save time and help avoid mistakes when you post transactions. The transaction values go to the accounts specified in the posting group for that particular entity. The only requirement is that you have a chart of accounts. For more information, see [Set Up the Chart of Accounts](finance-setup-chart-accounts.md).  

Posting groups are covered under three umbrellas:  

* General - Define who you sell to and buy from, and what you sell and what you buy. You can also combine groups to specify things like the income statement accounts to post to, or use groups to filter reports.  
* Specific - Use sales documents, for example, instead of posting directly to the general ledger. When you create entries in the customer ledger, corresponding entries are made in the general ledger.  
* Tax - Define the tax percentages and calculation types that apply to who you sell to and buy from, and what you sell and what you buy.

The following tables describe the posting groups under each umbrella.  

| General Posting Groups | Description |
| --- | --- |
| General Business Posting Groups |Assign this group to customers and vendors to specify who you sell to, and who you buy from. Set these up on the **Gen. Business Posting Groups** page. When you do, think about how many groups you'll need to break down sales and purchases. For example, group customers and vendors by geographical area, or by the type of business. |
| General Product Posting Groups |Assign this group to items and resources to specify what you sell, and what you buy. Set these up on the **Gen. Product Posting Groups** page. When you do, consider the number of groups you'll need to break down sales by product (items and resources) and purchases by items. For example, divide these groups by raw materials, retail, resources, capacity, and so on. |
| General Posting Setups |Combine business and product posting groups and choose the accounts to post to. For each combination of business and product posting groups, you can assign a set of general ledger accounts. For example, this means you can post the sale of the same item to different sales accounts in the general ledger because customers are assigned to different business posting groups. Set these up on the **General Posting Setup** page. |

| Specific Posting Groups | Description |
| --- | --- |
| Customer Posting Groups |Define the accounts to use when you post accounts receivable transactions. If you use inventory with receivables, the general business posting group assigned to your customer, and the general product posting group assigned to the inventory item determine the accounts that the sales order lines post to. See "General Business Posting Groups" and "General Product Posting Groups" under **General Posting Groups** above. Set these up on the **Customer Posting Groups** page. |
| Vendor Posting Groups |Define where to post transactions for payables accounts, service charge accounts, and payment discount accounts. This is similar to customer posting groups. Set these up on the **Vendor Posting Groups** page. |
| Inventory Posting Groups |Define inventory posting groups that you then assign to the relevant item accounts on the **Inventory Posting Setup** page. This way, when you post entries concerning an item, the system will post to the G/L account that is set up for the combination of inventory posting group and location that is linked to the item. Inventory posting groups also provide a good way to organize your inventory, so you can separate items by their posting group when you generate reports. Set these up on the **Inventory Posting Groups** page. |
| Bank Account Posting Groups |Define accounts for bank accounts. For example, this can simplify the processes of tracing transactions and reconciling bank accounts. Set these up on the **Bank Account Posting Groups** page. |
| Fixed Assets Posting Groups |Define accounts for different types of expenses and costs, such as acquisition costs, accumulated depreciation amounts, acquisition costs on disposal, accumulated depreciation on disposal, gains on disposal, losses on disposal, maintenance expenses, and depreciation expenses. Set these up on the **FA Posting Groups** page. |

| Tax Posting Group | Description |
| --- | --- |
| Tax Business Posting Groups |Determine how to calculate and post sales tax for customers and vendors. Set these up on the **Tax Business Posting Groups** page. When you do, think about how many groups you need. For example, this can depend on factors like local legislation, and whether you trade both domestically and internationally. |
| Tax Product Posting Groups |Indicate the tax calculations needed for the types of items or resources you buy or sell. |
| Tax Posting Setup |Combine tax business posting groups and tax product posting groups. When you fill in a general journal line, purchase line, or sales line, we'll look at the combination to identify the accounts to use. |

## Example of linking posting groups
Here's a scenario.  

These posting groups are chosen on the customer card:  

* General business posting group
* Customer posting group  

These posting groups are chosen on the item card:  

* General product posting group  
* Inventory posting group  

When you create a sales document, the sales header uses the customer card information, and the sales lines use the item card information.  

* The revenue posting (income statement) is determined by the combination of the general business posting group and the general product posting group.  
* The accounts receivable posting (balance sheet) is determined by the customer posting group.  
* The inventory posting (balance sheet) is determined by the inventory posting group.  
* The cost of goods sold posting (income statement) is determined by the combination of general business posting group and general product posting group.  

Your setup determines when posting happens. For example, the timing is affected by when you do periodic activities, such as posting inventory cost or adjusting cost item entries.

## Copying posting setup lines
The more product and business posting groups you have, the more lines you see in the General Posting Setup page. This can mean a lot of data entry to set up the general posting setup for the company. While there may be many different combinations of business and product posting groups, different combinations may still post to the same general ledger accounts. To limit the amount of manual entry, copy the general ledger accounts from an existing line on the **General Posting Setup** page.

## See also
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
