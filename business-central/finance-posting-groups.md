---
title: Posting Group Setup| Microsoft Docs
description: Overview of the posting groups you can use to save time and avoid mistakes when you post transactions.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting setup, initialize
ms.search.form: 312, 313
ms.date: 12/17/2021
ms.author: bholtorf

---
# Setting Up Posting Groups

Posting groups map entities such as customers, vendors, items, resources, and sales and purchase documents to general ledger accounts. They save time and help avoid mistakes when you post transactions. The transaction values go to the accounts specified in the posting group for that particular entity. The only requirement is that you have a chart of accounts. For more information, see [Set Up the Chart of Accounts](finance-setup-chart-accounts.md).  

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

## Set up posting groups on the go

To get users started faster, [!INCLUDE[prod_short](includes/prod_short.md)] offers assistance through notifications of missing G/L accounts in various posting group setups in documents. To get these notifications, make sure that the **G/L Account is missing in posting group or setup** notification is selected in the **My Notifications** page, which you can access from the **Change when I receive notifications** field in the **My Settings** page.  

This way, when you work on a document that uses a posting group or a setup that is missing a required general ledger account, you'll get a notification. Choose the link in the notificationto open a page where you can make the relevant changes, provided you have permission to do so.  

> [!NOTE]
> In order to take you directly to the posting group or setup that is missing a general ledger account, [!INCLUDE[prod_short](includes/prod_short.md)] will create a placeholder posting group or setup. Posting groups and setups are a way for the accountant to control how entries are posted to the general ledger, so such the just-in-time creation of posting groups and setups might not be allowed in your organization.  
> 
> In that case, disable the **G/L Account is missing in posting group or setup** notification, and then work with your accountant to make the relevant changes to the posting group, setup, or your document. This is an important step, because once documents are posted, any incorrectly used posting groups or setups cannot be deleted because there are general ledger entries created for them. 

## Troubleshooting posting group errors
Posting groups are one of the more advanced concepts to set up in [!INCLUDE[prod_short](includes/prod_short.md)]. If they aren't set up correctly, errors can occur when posting documents or journal lines. For example, these errors are typically caused by a mistake in how general ledger accounts are assigned, or how posting groups are combined.

When something is wrong, [!INCLUDE[prod_short](includes/prod_short.md)] will display the **Error Messages** page. The **Error Messages** page can make it easier to identify and resolve the issue. The page offers a description of the error that points out the posting group setup that needs attention. For example, the message might read "Sales Prepayment account is missing a General Posting Setup." There's also a link to open the page that's the source of the issue, so you can quickly resolve it.  

> [!NOTE]
> The error handling described above is not available on item, resource, employee, and fixed asset journals, or for G/L accounts added in local versions of posting groups.

## See also
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
