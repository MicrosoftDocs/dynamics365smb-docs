---
title: About Setting Up Value Added Tax | Microsoft Docs
description: Make sure that you correctly calculate, assess, and report on VAT on sales and purchases.
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
  
You can set up VAT calculations manually, but that can be tricky and time consuming. To make it easy, we've provided an assisted setup guide named VAT Setup that will help you with the steps. We recommend that you use the assisted setup guide to set up VAT.

If you want to set up VAT calculations yourself, or just want to learn about each step in the process, this topic contains descriptions of each step. These include how to:  
  
* Set up VAT business posting groups  
* Enter VAT posting setup combinations  
* Set up VAT product posting groups  
* Assign VAT posting groups to general ledger accounts for sales and purchases, and items, and resources  

    **Note**: To set up VAT for resources, you must enable the **Suite** user experience for your company. For more information, see [Customizing Your Dynamics 365 for Financials Experience](ui-experiences.md).
* Use reverse charge VAT for trade between EU countries/regions  
* Understand VAT rounding for documents  
* Set up clauses to explain the use of non-standard VAT rates

**Note**: The principles for setting up business and product posting groups for VAT are like the principles for setting up general posting groups. For more information, see [Posting Group Setups](finance-posting-groups.md).

## Use the VAT Setup assisted setup guide to set up VAT (recommended)
We recommend that you use the VAT Setup assisted setup guide to set up VAT in Financials. 

To start the assisted setup guide, follow these steps:
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Assisted Setup**, and then choose the related link.  
2. Choose **VAT Setup**.

## Set up VAT business posting groups
VAT business posting groups should represent the markets in which you do business with customers and vendors. Examples of VAT business posting groups are **Domestic**, or **European Union (EU)**.  
VAT business posting groups define how to calculate and post VAT according to the type of customer or vendor that is involved in the transaction. For example, the VAT business posting group can describe where the customer or vendor is located.  

Use codes that are easy to remember and describe the business posting group, such as **EU**, **Non-EU**, or **Domestic**. The code must be unique. You can set up as many codes as you need, but you cannot have the same code more than once in a table.
  
To set up a VAT business posting group, follow these steps:

1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Business Posting Group**, and then choose the related link.  
2. Fill in the fields as necessary.

You set up default VAT business posting groups by linking them to general business posting groups. Financials automatically assigns the VAT business posting group when you assign the business posting group to a customer, vendor, or general ledger account. Before you can do this, you must set up VAT business posting groups.

## Setting up VAT product posting groups
VAT product posting groups represent the items and resources you buy or sell, and determine how to calculate and post VAT according to the type of item or resource that is being bought or sold.
Use codes that are easy to remember and describe the product posting group, such as **No-VAT** for miscellaneous without VAT, **VAT10** for miscellaneous with 10 percent VAT, and **VAT25** for miscellaneous with 25 percent VAT.
The need for VAT product posting groups is determined by the way items are taxed. For example, differentiated VAT where the rates are 10% for food and 15% for non-food items.

To set up a VAT business posting group, follow these steps:

1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Product Posting Group**, and then choose the related link.  
2. Fill in the fields as necessary.

## Combining VAT posting setups
<!-- Why do you do this? and what's the difference between this and a VAT combinations setup? -->
You set up the combinations of VAT business posting groups and VAT product posting groups in the VAT Posting Setup window.
For each combination, you can specify the VAT percent, VAT calculation type, and general ledger account numbers for posting VAT that is related to sales and purchases and reverse charge VAT. You can also specify whether VAT is recalculated when a payment discount is applied or received.
You can enter as many combinations as you need. If you want to group VAT posting setup combinations with similar attributes, then you can define a VAT Identifier value for each group and then assign the identifier to the group members.

To combine VAT business posting group with a VAT product posting group, follow these steps:

1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Posting Setup**, and then choose the related link.
2. Fill in the fields as necessary.

## Assigning VAT posting groups
<!-- Why do you do this? -->
After you set up VAT posting groups, you assign them to general ledger accounts, customers and vendors, and items and resources.
Instead of manually assigning these groups to accounts, you can set up default VAT business posting groups on general business posting groups and default VAT product posting groups on general product posting groups. The relevant code is then automatically inserted as the VAT business or product posting group when you assign the relevant business or product posting group to a customer, vendor, item, or resource.  

For more information, see the following topics:

### To assign VAT posting Groups to accounts in the general ledger  
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Chart of Accounts**, and then choose the related link.  
2. Open the **Account** card for the account.
3. On the **Posting** FastTab, in the **Gen. Posting Type** field, choose either **Sale** or **Purchase**.  
5. Choose the VAT posting groups.  

### To assign VAT posting groups to customer and vendor accounts  
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Customer** or **Vendor**, and then choose the related link.  
2. On the **Customer** or **Vendor** card, expand the **Invoicing** FastTab.  
3. Choose the posting groups you want to assign.  

### To assign VAT product posting groups to item accounts and resource accounts  
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Item** or **Resource**, and then choose the related link.  
2. On the **Item** or **Resource** card, expand the **Invoicing** FastTab.  
3. Choose the posting groups you want to assign.

* How to: Set Up Default VAT Business Posting Groups  
* How to: Set Up Default VAT Product Posting Groups  

## Using reverse charge VAT for trade between EU countries or regions
<!-- This is specific to the EU. Do we need to rework this to cover regions that use VAT but are not in the EU?-->
Some companies must use reverse charge VAT when trading with other companies. For example this rule applies to purchases from EU countries/regions and sales to EU countries/regions.

**Note**: This rule applies when trading with companies that are registered as VAT liable in another EU country/region. If you do business directly with consumers in other EU countries/regions, then you should contact your tax authority for applicable VAT rules.

### Sales to EU countries or regions
VAT is not calculated on sales to VAT-liable companies in other EU countries/regions. You must report the value of these sales to EU countries/regions separately on your VAT statement.
To correctly calculate VAT on sales to EU countries/regions, you should:  
  
* Set up a line for sales with the same information for purchases. If you have already set up lines in the VAT Posting Setup window for purchases from EU countries/regions, then you can also use these lines for sales.  
* Assign the VAT business posting groups in the **VAT Bus. Posting Group** field on the **Invoicing** FastTab of the customer card of each EU customer. You should also enter the customer's VAT registration number in the **VAT Registration No.** field on the **Foreign Trade** FastTab.  

When you post a sale to a customer in another EU country/region, the VAT amount is calculated, and a VAT entry is created by using the information about the reverse charge VAT and the VAT base, which is the amount that is used to calculate the VAT amount. No entries are posted to the VAT accounts in the general ledger.

## Understanding VAT rounding for documents
Amounts in documents that are not yet posted are rounded and displayed to correspond with the final rounding of amounts that are actually posted. VAT is calculated for a complete document, which means that VAT that is calculated in the document is based on the sum of all lines with the same VAT identifier in the document.

## Set up clauses to explain the use of non-standard VAT rates
You set up a VAT clause to describe information about the type of VAT that is being applied. The information may be required by government regulation. After you set up a VAT clause, and associate it with a VAT posting setup, the VAT clause is displayed on all printed sales documents which have that VAT posting setup group, such as a sales invoice. 

If needed, you can also specify how to translate VAT clauses to other languages. Then, when you create and print a sales document that contains a VAT identifier, the document will include the translated VAT clause. The language code specified on the Customer card determines the language.
  
To set up VAT clauses, follow these steps:
1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Clauses**, and then choose the related link.  
2. On the **VAT Clauses** page, create a new line.  
3. In the **Code** field, enter an identifier for the clause. You use this code to assign the clause to VAT posting groups.  
4. In the **Description** field, enter the text that you want to display on documents that can include VAT. In the **Description 2** field, enter additional text, if needed. The text displays on new lines.  
5. Optional: To assign the VAT clause to a VAT posting setup right away, choose **Setup**, and then choosing the clause. If you want to wait, you can assign the clause later on the VAT Posting Setup page.  
6. Optional: To specify how to translate the VAT clause, choose the **Translations** action.

To assign a VAT clause to a VAT posting setup, follow these steps:
1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Posting Setup**, and then choose the related link.  
2. In the **VAT Clause** column, choose the clause to use for each VAT posting setup it applies to.  

To specify translations for VAT clauses, follow these steps:
1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Clauses**, and then choose the related link.  
2. Choose the **Translations** action.  
3. In the **Language Code** field, choose the language you're translating to.  
4. In the **Description** and **Description 2** fields, enter the translations of the descriptions. This text displays in the translated VAT report documents.  
  
## Set up codes for import VAT
You use the import VAT feature when you need to post a document where the entire amount must be treated as VAT. This is necessary if you receive a VAT invoice from the tax authorities for imported goods.  
  
To set up codes for import VAT, follow these steps:  
1. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Product Posting Groups**, and then choose the related link.  
2. On the VAT Product Posting Groups page, set up a new VAT product posting group for import VAT.  
3. In the top right corner, choose the **Search for Page or Report** icon, enter **VAT Posting Setup**, and then choose the related link.  
4. On the VAT Posting Setup page, create a new line, or use an existing VAT business posting groups in combination with the new VAT product posting group for import VAT.  
5. In the **VAT Calculation Type** field, choose **Full VAT**.  
6. In the **Purchase VAT Account** field, enter the general ledger account to use for posting import VAT. All other accounts are optional.  
  
##See Also  
