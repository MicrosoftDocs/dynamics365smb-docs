---
title: About Setting Up Value Added Tax | Microsoft Docs
description: Understand how to calculate, assess, and report on VAT in Financials.
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize
ms.date: 04/11/2017
ms.author: bholtorf

---

# About Setting Up Value Added Tax for Sales Documents
Consumers and businesses pay value added tax (VAT) when they purchase goods or services. The amount of VAT to pay can vary, depending on several factors. In Financials, you set up VAT to specify the rates to use to calculate tax amounts based on the following: 

* Who you sell to  
* Who you buy from  
* What you sell  
* What you buy  
  
There are a few things to do to start using VAT:  
  
* Set up VAT business posting groups  
* Enter VAT posting setup combinations  
* Set up VAT product posting groups  
* Assign VAT posting groups  
* Use reverse charge VAT for trade between EU countries/regions  
* Understand VAT rounding for documents  

VAT and sales tax differ, in that sales tax is charged one time when a product or service is sold. VAT is charged at each stage of the manufacturing process, and then charged in full when the finished product or service is sold.  

**Note**: The principles for setting up both business and product posting groups for VAT are like the principles for setting up general posting groups. For more information, see [Set Up Posting Groups]().
  
## Set up VAT business posting groups
VAT business posting group codes should represent the markets in which you do business with customers and vendors. For example, 
VAT business posting group codes define how VAT is calculated and posted according to the type of customer or vendor that is involved in the transaction. For example, the VAT business posting group can describe where the customer or vendor is located.
Use codes that are easy to remember and that describe the business group, such as EU, Non-EU, or Domestic. The code must be unique. You cannot have the same code more than once in a table. You can set up as many codes as you need.

To set up a VAT business posting group, follow these steps:

1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Business Posting Group**, and then choose the related link.  
2. Fill in the fields as necessary.

You set up default VAT business posting groups by linking them to general business posting groups. Microsoft Dynamics NAV automatically inserts the relevant code as the VAT business posting group when you assign the relevant business posting group to a customer, vendor, or general ledger account. Before you can do this, you must set up VAT business posting groups.

## Setting up VAT product posting groups
VAT product posting groups represent the items and resources you buy or sell. 
VAT product posting group codes determine how to calculate and post VAT according to the type of item that is being purchased or the type of item or resource that is being sold.
Use codes that are easy to remember and describe the product posting group, such as No-VAT for miscellaneous without VAT, VAT10 for miscellaneous with 10 percent VAT, and VAT25 for miscellaneous with 25 percent VAT.
The need for VAT product posting groups is determined by the way items are taxed. One example could be differentiated VAT, for example, 10% for food and 15% for non-food items.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Product Posting Group**, and then choose the related link.  
2. Fill in the fields as necessary.

## Entering VAT posting setup combinations
You set up the combinations of VAT business posting groups and VAT product posting groups in the VAT Posting Setup window.
For each combination, you can specify the VAT percent, VAT calculation type, and general ledger account numbers for posting VAT that is related to sales and purchases and reverse charge VAT. You can also specify whether VAT is recalculated when a payment discount is applied or received.
You can enter as many combinations as you need. If you want to group VAT posting setup combinations with similar attributes, then you can define a VAT Identifier value for each group and then assign the identifier to the group members.
For more information, see How to: Set Up Combinations of VAT Business Posting Groups and VAT Product Posting Groups, How to: Create a VAT Combination Setup, and VAT calculation type.

## Assigning VAT posting groups
Once you have set up VAT posting groups, you assign them to general ledger accounts, customers and vendors, and items and resources.
Instead of manually assigning these groups to accounts, you can set up default VAT business posting groups on general business posting groups and default VAT product posting groups on general product posting groups. The relevant code is then automatically inserted as the VAT business or product posting group when you assign the relevant business or product posting group to a customer, vendor, item, or resource.
For more information, see the following topics:

How to: Assign VAT Posting Groups to General Ledger Accounts 
How to: Assign VAT Business Posting Groups to Customer Accounts and Vendor Accounts 
How to: Assign VAT Product Posting Groups to Item Accounts and Resource Accounts 
How to: Set Up Default VAT Business Posting Groups 
How to: Set Up Default VAT Product Posting Groups 

## Using reverse charge VAT for trade between EU countries or regions
Companies in the EU must use reverse charge VAT when trading with other companies in the EU. The rule applies to purchases from EU countries/regions and sales to EU countries/regions.

**Note**: This rule applies when trading with companies that are registered as VAT liable in another EU country/region. If you do business directly with consumers in other EU countries/regions, then you should contact your tax authority for applicable VAT rules.

### Sales to EU counrties or regions
VAT is not calculated on sales to VAT-liable companies in other EU countries/regions. You must report the value of these sales to EU countries/regions separately on your VAT statement.
To correctly calculate VAT on sales to EU countries/regions, you should:  
  
* Set up a line for sales with the same information for purchases. If you have already set up lines in the VAT Posting Setup window for purchases from EU countries/regions, then you can also use these lines for sales.  
* Assign the VAT business posting groups in the **VAT Bus. Posting Group** field on the **Invoicing** FastTab of the customer card of each EU customer. You should also enter the customer's VAT registration number in the **VAT Registration No.** field on the **Foreign Trade** FastTab.  

When you post a sale to a customer in another EU country/region, the VAT amount is calculated, and a VAT entry is created by using the information about the reverse charge VAT and the VAT base, which is the amount that is used to calculate the VAT amount. No entries are posted to the VAT accounts in the general ledger.

## Understanding VAT rounding for documents
Amounts in documents that are not yet posted are rounded and displayed to correspond with the final rounding of amounts that are actually posted. VAT is calculated for a complete document, which means that VAT that is calculated in the document is based on the sum of all lines with the same VAT identifier in the document.