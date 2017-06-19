---
title: Set Up Intercompany Transaction Posting| Microsoft Docs
description: Create your intercompany vendors and customers as so-called IC partners, and set up an intercompany chart of accounts.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: IC, group, consolidation, affiliate, subsidiary
ms.date: 06/19/2017
ms.author: sgroespe

---
# How to: Set Up Intercompany

## Intercompany Chart of Accounts and Intercompany Dimensions  
 To send a transaction (such as a sales journal line) from one company and have the corresponding transaction (such as a purchase journal line) automatically created in the partner company, the companies involved need to agree on a common chart of accounts and set of dimensions for use on intercompany transactions. The intercompany chart of accounts can be, for example, a simplified version of the parent company's chart of accounts. Each company maps their full chart of accounts to the shared intercompany chart of accounts, and each company maps their dimensions to the intercompany dimensions.  

## IC Partner Codes  
 You also need to set up an IC partner code for each partner company. The partner codes must also be agreed upon by all of the companies.  

 If you have set up your intercompany partners as customers or vendors, fill in the **IC Partner Code** field on the relevant customer and vendor cards.  

## Items and Resources  
 If you will create or receive intercompany lines with items, you can either use your own item numbers, or you can set up your partner's item numbers for each relevant item, either in the **Vendor Item No.** field or the **Common Item No.** field on the item card, or by using the **Item Cross Reference Entries** window linked to the item card.  

 If you will make intercompany sales transactions that include resources, you must fill in the **IC Partner Purch. G/L Acc. No.** field on the resource card for each relevant resource. This is the number of the intercompany general ledger account that the amount for this resource will be posted to in your partner's company.  

 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  

## To set up the Intercompany feature  
 The Intercompany feature lets you save time and errors on data entry, by electronically transferring transactions between your company and your partner companies.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.  
2. In the **Company Information** window, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Open the **IC Partner List** to create and fill in a card for each of your partners.  
4. If you have set up your intercompany partners as customers and vendors, fill in the **IC Partner Code** field on the relevant customer and vendor cards.  
5. Set up the intercompany chart of accounts.  
6. If you want to use dimensions on intercompany transactions, set up intercompany dimensions.  
7. If you create or receive intercompany lines with items, you can either use your own item numbers, or set up your partner's item numbers for each relevant item.

    You can do this either in the **Vendor Item No.** field or the **Common Item No.** field on the item card, or use the **Item Cross Reference Entries** window that is linked to the item card.  

8. If you will make intercompany transactions that include resources, you must fill in the **IC Partner Purch. G/L Acc. No.** field on the resource card for each relevant resource.  

  Now you can create intercompany transactions using the intercompany general journal or sales or purchase documents.  

## To set up IC vendors and IC customers as IC partners
**IC Vendor** window
**IC Customer** window
You can use intercompany postings to transfer transactions electronically from one partner company to another. This allows you to save time on data entry and reduce the number of errors.   

# To set up the intercompany chart of accounts
In order for a group of companies to make intercompany transactions, they must agree on a chart of accounts to use as a common reference. To define the intercompany chart of accounts that your partner companies will use to make intercompany transactions, follow this procedure.

Before you and your intercompany partners can begin to transfer intercompany transactions electronically, each of you must set up the intercompany chart of accounts in your company.  

You must agree with your partner companies on the account numbers that all of you will use when you create intercompany transactions. For example, the parent company of the group creates a simplified version of their own chart of accounts, exports this intercompany chart of accounts from their database into an XML file and distributes it to each of the companies in the group.  

Each of the subsidiaries then imports the XML file into the IC Chart of Accounts table and maps the accounts to the accounts in their own chart of accounts.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IC Chart of Accounts**, and then choose the related link.  
2. In the **IC Chart of Accounts** window, enter each account on a line in the window.  
3. If your IC chart of accounts will be identical or similar to your regular chart of accounts, you can fill in the window automatically. On the **Actions** tab, in the **Functions** group, choose **Copy from Chart of Accounts** to copy chart of accounts, and then you can edit the resulting lines.  
4. To export the intercompany chart of accounts to an XML file for distribution to your partner companies, choose the **Export** action.  
5. Specify the file name and the location where you want to save the XML file, and then choose the **Save** button.  

Before you can use the intercompany chart of accounts, you may want to map the intercompany chart of accounts to your company's chart of accounts.  

### Parent Company  
If your company is defining the intercompany chart of accounts that your group will use as a common reference, follow the "To set up the intercompany chart of accounts" procedure.  

### Subsidiary Company  
If your company has received an XML file containing the intercompany chart of accounts that your group will use as a common reference, follow the procedure: [How to: Import the Intercompany Chart of Accounts]().  

### All Companies  
Once you have defined or imported the intercompany chart of accounts, you need to associate each of the IC G/L accounts with one of your company's G/L accounts. In the IC Chart of Accounts window, you specify how IC G/L accounts on incoming transactions will be translated into G/L accounts from your company's chart of accounts. Follow the "To map the intercompany chart of accounts to your company’s chart of accounts" procedure.  

## To import the intercompany chart of accounts  
Before you can complete this procedure, you need to have an XML file containing the intercompany chart of accounts that you and your partner companies have agreed to use.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IC Chart of Accounts**, and then choose the related link.  
2. In the **IC Chart of Accounts** window, choose the **Import** action.  
3. Specify the file name and location of the XML file and choose the **Open** button.  

The lines in the **IC Chart of Accounts** window will be filled in.  

## To map the intercompany chart of accounts to your company's chart of accounts  
After you fill in the **IC Chart of Accounts** window with the chart of accounts that you and your intercompany partners have agreed to use, you need to associate each of the intercompany general ledger accounts with one of your company's general ledger accounts. In the **IC Chart of Accounts** window, you specify how intercompany general ledger accounts on incoming transactions will be translated into accounts from your company's chart of accounts.  

When you create an intercompany sales or purchase line to send as an outgoing transaction, you will enter an account from the intercompany chart of accounts as a default for which account in your partner's company the amount should be posted to.  

If the accounts in the intercompany chart of accounts have the same account numbers as the corresponding accounts in chart of accounts, you can map the accounts.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IC Chart of Accounts**, and then choose the related link.  
2. Select the lines that you want to map automatically, and then choose the **Map to Acc. with Same No** action.  

    For each intercompany general ledger account that was not mapped automatically.  
3. Fill in the **Map-to G/L Acc. No.** field.  

Now you can set up default IC partner general ledger accounts.  

## To set up of the intercompany dimensions
In order for a group of companies to use dimensions on intercompany transactions, they must agree on a set of dimensions to use as a common reference. Follow the steps in the procedure to define the IC dimensions that you and your partner companies will use to make intercompany transactions.

If you and your intercompany partners want to be able to exchange transactions with dimensions linked to them, you need to use intercompany dimensions.  

You must agree with your partner companies on the dimensions that all of you will use when you create intercompany transactions. For example, the parent company of the group creates a simplified version of their own set of dimensions, exports these intercompany dimensions into an XML file and distributes it to each of the companies in the group.  

Each of the subsidiaries then imports the XML file into the IC Dimension table and maps the intercompany dimensions to the dimensions in their own Dimension table.  

### Parent Company  
If your company is defining the set of intercompany dimensions that your group will use as a common reference, follow the procedure: [How to: Define Intercompany Dimensions]().  

### Subsidiary Company  
If your company has received an XML file containing the IC dimensions that your group will use as a common reference, follow the procedure: [How to: Import Intercompany Dimensions]().

### All Companies  
Once you have defined or imported the intercompany dimensions, you need to associate each of the IC dimensions with one of your company's dimensions, and vice versa. In the IC Dimensions window, you specify how IC dimensions on incoming transactions will be translated into dimensions from your company's Dimension table. In the Dimension window, you specify how your dimensions will be translated into intercompany dimensions on outgoing transactions. Follow the procedure: [How to: Map Intercompany Dimensions to Your Company’s Dimensions]().  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IC Dimensions**, and then choose the related link.  
2. In the **IC Dimensions** window, enter each dimension on a line in the window.

    If your IC dimensions will be similar or identical to your company dimensions, you can fill in the window automatically by using the **Copy from Dimensions** function, and then you can edit the resulting lines.  
3. To export the IC dimensions to an XML file for distribution to your partner companies, choose the **Export** action.  
4. Specify the file name and the location where you want to save the XML file, and then choose the **Save** button.  

Before you can use the intercompany dimensions, you may want to map intercompany dimensions to your company's dimensions.  

## To import the IC dimensions  
Before you can complete this procedure, you need to have an XML file containing the intercompany dimensions that you and your partner companies have agreed to use.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IC Dimensions**, and then choose the related link.  
2. In the **IC Dimensions** window, choose the **Import** action.  
3. Specify the file name and location of the XML file, and then choose the **Open** button.  

The lines in the **IC Dimensions** window and the **IC Dimension Values** window are imported.  

Now you must specify how the intercompany dimensions correspond to your company's dimensions.

## To map the intercompany chart of accounts to your company's chart of accounts  
After you fill in the **IC Chart of Accounts** window with the chart of accounts that you and your intercompany partners have agreed to use, you need to associate each of the intercompany general ledger accounts with one of your company's general ledger accounts. In the **IC Chart of Accounts** window, you specify how intercompany general ledger accounts on incoming transactions will be translated into accounts from your company's chart of accounts.  

When you create an intercompany sales or purchase line to send as an outgoing transaction, you will enter an account from the intercompany chart of accounts as a default for which account in your partner's company the amount should be posted to.  

If the accounts in the intercompany chart of accounts have the same account numbers as the corresponding accounts in chart of accounts, you can map the accounts.

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **IC Chart of Accounts**, and then choose the related link.  
2. Select the lines that you want to map automatically, and then choose the **Map to Acc. with Same No** action.
3. For each intercompany general ledger account that was not mapped automatically, fill in the **Map-to G/L Acc. No.** field.  

Now you can set up default IC partner general ledger accounts.  

## To set up default intercompany partner general ledger accounts  
When you create an intercompany sales or purchase line to send as an outgoing transaction, you will enter an account from the IC chart of accounts as a default for which account in your partner's company the amount should be posted to. In the **Chart of Accounts** window, for accounts that you often use on outgoing IC sales or purchase lines, you can specify a default IC partner general ledger account. For example, for your receivables accounts, you can enter the corresponding payables accounts from the IC chart of accounts.  

> [!NOTE]  
>  Repeat the following procedure for each account that you often enter in the **Bal. Account No.** field on a line in an intercompany journal or document.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2. In the **Default IC Partner G/L Account** field, enter the IC general ledger account that your partner will post to when you post to the general ledger account on the line.  

> [!NOTE]  
>  When you enter a general ledger account in the **Bal. Account No.** field on an intercompany line with **IC Partner** in the **Account Type** field, the **IC Partner G/L Account** field is automatically filled in.  

## See Also
[Managing Intercompany Transactions](intercompany-manage.md)  
[Finance](finance.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
