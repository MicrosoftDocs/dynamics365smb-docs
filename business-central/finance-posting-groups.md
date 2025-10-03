---
title: Posting group setup
description: Learn how to use posting groups to save time and avoid mistakes when you post transactions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: install-set-up-deploy
ms.search.keywords: posting setup, initialize
ms.search.form: 312, 313
ms.date: 08/13/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Set up posting groups

Posting groups map entities to general ledger accounts. Examples of entities are customers, vendors, items, resources, and sales and purchase documents. Posting groups save time and help avoid mistakes when you post transactions. The transaction values go to the accounts specified in the posting group for that particular entity. The only requirement is that you have a chart of accounts. For more information, see [Set Up the Chart of Accounts](finance-setup-chart-accounts.md).  

Posting groups are covered under three umbrellas:  

* General

  Define who you sell to and buy from, and what you sell and what you buy. You can also combine groups to specify things like the income statement accounts to post to, or use groups to filter reports.  
* Specific

  Use sales documents, for example, instead of posting directly to the general ledger. When you create entries in the customer ledger, corresponding entries are made in the general ledger.  
* Tax

  Define the tax percentages and calculation types that apply to who you sell to and buy from, and what you sell and what you buy.

The following sections describe the posting groups under each umbrella.  

## General posting groups

The following table describes the general posting groups.

| Type | Description |
| --- | --- |
| General Business Posting Groups |Assign this group to customers and vendors to specify who you sell to, and who you buy from. Set up these posting groups on the **Gen. Business Posting Groups** page. When you do, think about how many groups you need to break down sales and purchases. For example, group customers and vendors by geographical area, or by the type of business. |
| General Product Posting Groups |Assign this group to items and resources to specify what you sell, and what you buy. Set up these posting groups on the **Gen. Product Posting Groups** page. When you do, consider the number of groups you need to break down sales by product (items and resources) and purchases by items. For example, divide these groups by raw materials, retail, resources, capacity, and so on. |
| General Posting Setups |Combine business and product posting groups and choose the accounts to post to. For each combination of business and product posting groups, you can assign a set of general ledger accounts. For example, you can post the sale of the same item to different general ledger accounts because customers are assigned to different business posting groups. Set these configurations up on the **General Posting Setup** page. |

## Specific posting groups

The following table describes the posting groups that are specific to types of data.

|Type | Description |
| --- | --- |
| Customer Posting Groups |Define the accounts to use when you post accounts receivable transactions. If you use inventory with receivables, the accounts that the sales order lines post to are determined by the general business posting group assigned to your customer, and the general product posting group assigned to the inventory item. See *General Business Posting Groups* and *General Product Posting Groups* in the [General posting groups](#general-posting-groups) section. Set up these posting groups on the **Customer Posting Groups** page. |
| Vendor Posting Groups |Define where to post transactions for payables accounts, service charge accounts, and payment discount accounts. This is similar to customer posting groups. Set up these posting groups on the **Vendor Posting Groups** page. |
| Inventory Posting Groups |Define inventory posting groups that you then assign to the relevant item accounts on the **Inventory Posting Setup** page. This way, when you post entries concerning an item, the system posts to the G/L account that is set up for the combination of inventory posting group and location that is linked to the item. Inventory posting groups also provide a good way to organize your inventory, so you can separate items by their posting group when you generate reports. Set up these posting groups on the **Inventory Posting Groups** page. |
| Bank Account Posting Groups |Define the general ledger accounts that bank account entries are posted to. For example, this can simplify the processes of tracing transactions and reconciling bank accounts. Set up these posting groups on the **Bank Account Posting Groups** page. We recommend that these G/L accounts have the **Direct Posting** field set to *No*. |
| Fixed Assets Posting Groups |Define accounts for different types of expenses and costs, such as acquisition costs, accumulated depreciation amounts, acquisition costs on disposal, accumulated depreciation on disposal, gains on disposal, losses on disposal, maintenance expenses, and depreciation expenses. Set up these posting groups on the **FA Posting Groups** page. |

### Allow alternative posting groups on documents

You can let people choose other customer, vendor, or employee posting groups than the default groups when they're working with sales or purchase documents and journals. Alternative posting groups can replace their default posting group.

To allow people to choose alternative posting groups, turn on the **Allow Multiple Posting Groups** toggle on the following pages:

* **Sales & Receivable Setup** for customer posting groups. If you use service management features, also turn on the toggle on the **Service Management Setup** page.
* **Purchase & Payables Setup** page for vendor posting groups.
* **Human Resources Setup** page for employee posting groups.

On the **Customer Posting Groups**, **Vendor Posting Groups**, and **Employee Posting Groups** pages, you can use the **Alternative Groups** action to specify the posting groups to allow as substitutes.

The last step in the setup is to turn on the **Allow Multiple Posting Groups** toggle on the card pages for the relevant customers, vendors, or employees.

After you set this up, you can choose from the allowed alternative posting groups when you post sales or purchase documents and journals. The alternative posting groups are copied to posted documents and journals, and payable or receivable G/L entries are posted to their G/L accounts.

When you apply, for example, an invoice and payment that are posted with different posting groups (different G/L accounts), [!INCLUDE[prod_short](includes/prod_short.md)] transfers the amounts between the G/L accounts to balance them.

## Tax posting groups

The following table describes the tax-related posting groups.

| Type | Description |
| --- | --- |
| Tax Business Posting Groups |Determine how to calculate and post sales tax for customers and vendors. Set up these posting groups on the **Tax Business Posting Groups** page. When you do, think about how many groups you need. For example, it might depend on factors like local legislation, and whether you trade both domestically and internationally. |
| Tax Product Posting Groups |Indicate the tax calculations needed for the types of items or resources you buy or sell. |
| Tax Posting Setup |Combine tax business posting groups and tax product posting groups. When you fill in a general journal line, purchase line, or sales line, we look at the combination to identify the accounts to use. |

If your country/region uses value-added tax (VAT), see [Set Up Calculations and Posting Methods for Value-Added Tax](finance-setup-vat.md).  

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

## Copy posting setup lines

The more product and business posting groups you have, the more lines you'll have on the **General Posting Setup** page. While there might be many different combinations of business and product posting groups, different combinations might still post to the same general ledger accounts. To limit the amount of manual entry, copy the general ledger accounts from an existing line on the **General Posting Setup** page.

## Set up posting groups on the go

To get users started faster, [!INCLUDE[prod_short](includes/prod_short.md)] can show notifications of missing G/L accounts in various posting group setups. To get these notifications, make sure that the **G/L Account is missing in posting group or setup** notification is selected in the **My Notifications** page, which you can access from the **Change when I receive notifications** field in the **My Settings** page.  

This way, when you work on a document that uses a posting group or a setup that is missing a required general ledger account, you get a notification. Choose the link in the notification to open a page where you can make the relevant changes, provided you have permission to do so.  

> [!NOTE]
> In order to take you directly to the posting group or setup that is missing a general ledger account, [!INCLUDE[prod_short](includes/prod_short.md)] will create a placeholder posting group or setup. Posting groups and setups are a way for the accountant to control how entries are posted to the general ledger, so such the just-in-time creation of posting groups and setups might not be allowed in your organization.  
>
> In that case, disable the *G/L Account is missing in posting group or setup* notification, and then work with your accountant to make the relevant changes to the posting group, setup, or your document. This is an important step, because after documents are posted, you can't delete incorrectly used posting groups or setups because general ledger entries are created for them.

Use the **Blocked** field in the **General Posting Setup** page to prevent users from mistakenly using a setup that is no longer relevant for new postings. 

## Access all fields and accounts when you set up a posting group  

Posting groups can be complex to set up. Because some types of accounts aren't frequently used, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't show them as columns on the lines. Also, to make it a bit easier to choose the right accounts, [!INCLUDE [prod_short](includes/prod_short.md)] filters the accounts that you can choose in field lookups. 

If you want to access all accounts on the lines and in the field lookups, there are a couple of settings that can help:

* To show all accounts as columns on the lines, turn on the **Show All Accounts** toggle.
* On individual lines, to access all accounts in the field lookups, choose the **View All Accounts on Lookup** checkbox.

> [!NOTE]
> The **Show All Accounts** toggle might not seem to work on the **General Posting Setup** page. That's because [!INCLUDE [prod_short](includes/prod_short.md)] always shows all accounts as columns on the lines on that page.

## Troubleshooting posting group errors

Posting groups are one of the more advanced concepts to set up in [!INCLUDE[prod_short](includes/prod_short.md)]. If they aren't set up correctly, errors can occur when posting documents or journal lines. For example, these errors are typically caused by a mistake in how general ledger accounts are assigned, or how posting groups are combined.

When something is wrong, [!INCLUDE[prod_short](includes/prod_short.md)] will display the **Error Messages** page. The **Error Messages** page can make it easier to identify and resolve the issue. The page offers a description of the error that points out the posting group setup that needs attention. For example, the message might read "Sales Prepayment account is missing a General Posting Setup." There's also a link to open the page that's the source of the issue, so you can quickly resolve it.  

> [!NOTE]
> The error handling described above is not available on item, resource, employee, and fixed asset journals, or for G/L accounts added in local versions of posting groups.

## Audit changes to posting groups

You can use the Change Log feature to capture changes users make to your posting group setup. [!INCLUDE [include-audit-what-who-when](includes/include-audit-what-who-when.md)]

The following table lists the table for posting group and their IDs.

| Table | Table ID |
| ----- | -------- |
| Gen. Product Posting Group | 251 |
| Customer Posting Group | 92 |
| Inventory Posting Group | 94 |
| FA Posting Group | 5606 |
| Vendor Posting Group | 93 |


[!INCLUDE [include-audit-changes-to-setup-learn-more-link](includes/include-audit-changes-to-setup-learn-more-link.md)]


## Related information

[The General Ledger and the Chart of Accounts](finance-general-ledger.md)    
[Setting Up Finance](finance-setup-finance.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
