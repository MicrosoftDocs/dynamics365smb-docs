---
title: About Setting Up Value-Added Tax | Microsoft Docs
description: Make sure that you correctly calculate, post, and report on VAT for sales and purchases.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.date: 04/20/2017
ms.author: bholtorf

---

# Setting Up Calculations and Posting Methods for Value-Added Tax
Consumers and businesses pay value-added tax (VAT) when they purchase goods or services. The amount of VAT to pay can vary, depending on several factors. In [!INCLUDE[d365fin](includes/d365fin_md.md)], you set up VAT to specify the rates to use to calculate tax amounts based on the following:

* Who you sell to  
* Who you buy from  
* What you sell  
* What you buy  

You can set up VAT calculations manually, but that can be tricky and time consuming. To make it easy, we provide an assisted setup guide named **VAT Setup** that will help you with the steps. We recommend that you use the assisted setup guide to set up VAT.

> [!NOTE]  
>   You can use the guide only if you have created a My Company, and have not posted transactions that include VAT. Otherwise, it would be very easy to use different VAT rates by mistake, and make VAT-related reports inaccurate.  

If you want to set up VAT calculations yourself, or just want to learn about each step, this topic contains descriptions of each step.

## To use the VAT Setup assisted setup guide to set up VAT (recommended)
We recommend that you use the VAT Setup assisted setup guide to set up VAT in [!INCLUDE[d365fin](includes/d365fin_md.md)].

To start the assisted setup guide, follow these steps:
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Assisted Setup**.  
2. Choose **Set up VAT**.

## To set up VAT registration numbers for your country or region
To help ensure that people enter valid VAT registration numbers, you can define formats for the VAT registration numbers that are used in the countries or regions in which you do business. [!INCLUDE[d365fin](includes/d365fin_md.md)] will display an error message when someone makes a mistake or uses a format that is incorrect for the country or region.

To setup VAT registration numbers, follow these steps:
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Countries/Regions**.
2. Choose the country or region, and then choose the **VAT Reg. No. Formats** action.
3. In the **Formats** field, define the format by entering one or more of the following characters:  

* # - Requires a single-digit number.
* @ - Requires a letter. This is not case-sensitive.
* ? - Allows any character.

    > [!Tip]
    > You can use other characters as long as they are always present in the country or region format. For example, if you need to include a period or a hyphen between sets of numbers, you can define the format as ##.####.### or @@-###-###.  

## To set up VAT business posting groups
VAT business posting groups should represent the markets in which you do business with customers and vendors, and define how to calculate and post VAT in each market. Examples of VAT business posting groups are **Domestic** and **European Union (EU)**.  

Use codes that are easy to remember and describe the business posting group, such as **EU**, **Non-EU**, or **Domestic**. The code must be unique. You can set up as many codes as you need, but you cannot have the same code more than once in a table.

To set up a VAT business posting group, follow these steps:

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Business Posting Group**, and then choose the related link.  
2. Fill in the fields as necessary.

You set up default VAT business posting groups by linking them to general business posting groups. [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically assigns the VAT business posting group when you assign the business posting group to a customer, vendor, or general ledger account.

## To set up VAT product posting groups
VAT product posting groups represent the items and resources you buy or sell, and determine how to calculate and post VAT according to the type of item or resource that is being bought or sold.  
It is a good idea to use codes that are easy to remember and describe the rate, such as **NO-VAT** or **Zero**, **VAT10** or **Reduced** for 10% VAT, and **VAT25** or **Standard** for 25%.

To set up a VAT business posting group, follow these steps:

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Product Posting Groups**, and then choose the related link.  
2. Fill in the fields as necessary.

## To combine VAT posting groups in VAT posting setups
[!INCLUDE[d365fin](includes/d365fin_md.md)] calculates VAT amounts on sales and purchases based on VAT posting setups, which are combinations of VAT business and product posting groups. For each combination, you can specify the VAT percent, VAT calculation type, and general ledger accounts for posting VAT for sales, purchases, and reverse charges. You can also specify whether to recalculate VAT when a payment discount is applied or received.  

Set up as many combinations as you need. If you want to group VAT posting setup combinations with similar attributes, you can define a **VAT Identifier** for each group, and assign the identifier to the group members.

To combine VAT posting setups, follow these steps:

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.
2. Fill in the fields as necessary.

## To assign VAT posting groups by default to multiple entities
If you want to apply the same VAT posting groups to multiple entities, you can set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to do so by default. There are a couple of ways to do this:

* You can assign VAT business posting groups to general business posting groups, or customer or vendor templates
* You can assign VAT product posting groups on general product posting groups  

The VAT business or product posting group is assigned when you choose a business or product posting group for a customer, vendor, item, or resource.

## To assign VAT posting groups to individual accounts, customers, vendors, items, and resources
The following sections describe how to assign VAT posting groups to individual entities.

### To assign VAT posting groups to individual general ledger accounts
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
2. Open the **G/L Account** card for the account.  
3. On the **Posting** FastTab, in the **Gen. Posting Type** field, choose either **Sale** or **Purchase**.  
5. Choose the VAT posting groups to use for the sales or purchase account.  

### To assign VAT business posting groups to customers and vendors  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customer** or **Vendor**, and then choose the related link.  
2. On the **Customer** or **Vendor** card, expand the **Invoicing** FastTab.  
3. Choose the VAT business posting group.  

### To assign VAT product posting groups to individual items and resources  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item** or **Resource**, and then choose the related link.  
2. Do one of the following:  

* On the **Item** card, expand the **Price & Posting** FastTab, and then choose **Show more** to display the **VAT Product Posting Group** field.  
* On the **Resource** card, expand the **Invoicing** FastTab.  
3. Choose the VAT product posting group.  

## To set up clauses to explain the use of non-standard VAT rates
You set up a VAT clause to describe information about the type of VAT that is being applied. The information may be required by government regulation. After you set up a VAT clause, and associate it with a VAT posting setup, the VAT clause is displayed on printed sales documents that use the VAT posting setup group.

If needed, you can also specify how to translate VAT clauses to other languages. Then, when you create and print a sales document that contains a VAT identifier, the document will include the translated VAT clause. The language code specified on the Customer card determines the language.

You can modify or delete a VAT clause, and your modifications will be reflected in a generated report. However, [!INCLUDE[d365fin](includes/d365fin_md.md)] does not keep a history of the change. On the report, the VAT clause descriptions are printed and displayed for all lines in the report alongside the VAT amount and the VAT base amount. If a VAT clause has not been defined for any lines on the sales document, then the whole section is omitted when the report is printed.

### To set up VAT clauses
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Clauses**, and then choose the related link.  
2. On the **VAT Clauses** page, create a new line.  
3. In the **Code** field, enter an identifier for the clause. You use this code to assign the clause to VAT posting groups.  
4. In the **Description** field, enter the text that you want to display on documents that can include VAT. In the **Description 2** field, enter additional text, if needed. The text displays on new lines.  
5. Optional: To assign the VAT clause to a VAT posting setup right away, choose **Setup**, and then choosing the clause. If you want to wait, you can assign the clause later on the VAT Posting Setup page.  
6. Optional: To specify how to translate the VAT clause, choose the **Translations** action.

### To assign a VAT clause to a VAT posting setup
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.  
2. In the **VAT Clause** column, choose the clause to use for each VAT posting setup it applies to.  

### To specify translations for VAT clauses
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Clauses**, and then choose the related link.  
2. Choose the **Translations** action.  
3. In the **Language Code** field, choose the language you are translating to.  
4. In the **Description** and **Description 2** fields, enter the translations of the descriptions. This text displays in the translated VAT report documents.  

## To create a VAT posting setup to handle Import VAT
You use the Import VAT feature when you need to post a document where the entire amount is VAT. You will use this if you receive an invoice from the tax authorities for VAT for imported goods.  

To set up codes for import VAT, follow these steps:  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Product Posting Groups**, and then choose the related link.  
2. On the VAT Product Posting Groups page, set up a new VAT product posting group for import VAT.  
3. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Posting Setup**, and then choose the related link.  
4. On the VAT Posting Setup page, create a new line, or use an existing VAT business posting groups in combination with the new VAT product posting group for import VAT.  
5. In the **VAT Calculation Type** field, choose **Full VAT**.  
6. In the **Purchase VAT Account** field, enter the general ledger account to use for posting import VAT. All other accounts are optional.  

## To verify VAT registration numbers
It is important that the VAT registration numbers you have for customers, vendors, and contacts are valid. For example, companies sometimes change their tax liability status, and in some countries tax authorities might ask you to provide reports, such as the EC Sales List report, that list the VAT registration numbers you use when you do business.

The European Commission provides the VIES VAT Number Validation service on its website, which is public and free. [!INCLUDE[d365fin](includes/d365fin_md.md)] can save you a step and let you use the VIES service to validate and track VAT numbers for customers, vendors, and contacts straight from the customer, vendor, and contact cards. The service in [!INCLUDE[d365fin](includes/d365fin_md.md)] is named **EU VAT Reg. No. Validation Service**. The service is available on the **Service Connections** page, and you can start using it right away. The service connection is free, and signup is not required.

> [!Note]
> To enable the EU VAT Reg. No. Validation Service, you must have administrator permissions.

When you use our service connection, we record a history of VAT numbers and verifications for each customer, vendor, or contact, in the **VAT Registration Log**, so you can easily track them. The log is specific to each customer. For example, the log is useful for proving that you have verified that the current VAT number is correct. When you verify a VAT number, the **Request Identifier** column in the log will reflect that you have taken action.

You can view the VAT Registration log on the Customer, Vendor, or Contact cards, on the **Invoicing** FastTab, by choosing the lookup button in the **VAT Registration No.** field.  

Our service can also save you time when you create a customer or vendor. If you know the customer's VAT number, you can enter it in the **VAT Registration No.** field on the Customer or Vendor cards, and we will fill out the customer name for you. Some countries also provide company addresses in a structured format. In those countries, we fill in the address too.  

> [!NOTE]  
> There are a couple of things to note about the VIES VAT Number Validation service:

* The service uses the http protocol, which means that data transferred through the service is not encrypted.  
* You may experience downtime for this service for which Microsoft is not responsible. The service is part of a broad EU network of national VAT registers.

## Using Reverse Charge VAT for Trade between EU Countries or Regions
Some companies must use reverse charge VAT when trading with other companies. For example this rule applies to purchases from EU countries/regions and sales to EU countries/regions.  

> [!NOTE]  
> This rule applies when trading with companies that are registered as VAT liable in another EU country/region. If you do business directly with consumers in other EU countries/regions, then you should contact your tax authority for applicable VAT rules.  

> [!TIP]  
> You can verify that a company is registered as VAT liable in another EU country by using the EU VAT Registration Number Validation service. The service is available for free in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see the section titled _Verify VAT registration numbers_ in this topic.

### Sales to EU countries or regions
VAT is not calculated on sales to VAT-liable companies in other EU countries/regions. You must report the value of these sales to EU countries/regions separately on your VAT statement.  

To correctly calculate VAT on sales to EU countries/regions, you should:  

* Set up a line for sales with the same information for purchases. If you have already set up lines on the VAT Posting Setup page for purchases from EU countries/regions, then you can also use these lines for sales.  
* Assign the VAT business posting groups in the **VAT Bus. Posting Group** field on the **Invoicing** FastTab of the customer card of each EU customer. You should also enter the customer's VAT registration number in the **VAT Registration No.** field on the **Foreign Trade** FastTab.  

When you post a sale to a customer in another EU country/region, the VAT amount is calculated, and a VAT entry is created by using the information about the reverse charge VAT and the VAT base, which is the amount that is used to calculate the VAT amount. No entries are posted to the VAT accounts in the general ledger.

## Understanding VAT rounding for documents
Amounts in documents that are not yet posted are rounded and displayed to correspond with the final rounding of amounts that are actually posted. VAT is calculated for a complete document, which means that VAT is calculated based on the sum of all lines with the same VAT identifier in the document.

## Understanding the VAT Rate Conversion Process  
The VAT rate change tool performs VAT rate conversions for master data, journals, and orders in different ways. The selected master data and journals will be updated by the new general product posting group or VAT product post group. If an order has been fully or partially shipped, the shipped items will keep the current general product posting group or VAT product posting group. A new order line will be created for the unshipped items and updated to align current and new VAT or general product posting groups. In addition, item charge assignments, reservations, and item tracking information will be updated accordingly.  

There are, however, a few things that the tool does not convert:

* Sales or purchase orders and invoices where shipments have been posted. These documents are posted using the current VAT rate.  
* Documents that have posted prepayment invoices. For example, you have made or received prepayments on invoices that have not been completed before you use the VAT rate change tool. In this case, there will be a difference between the VAT that is due and the VAT that has been paid in the prepayments when the invoice is completed. The VAT rate change tool will skip these documents and you will have to manually update them.  
* Drop shipments or special orders.  
* Sales or purchase orders with warehouse integration if they are partially shipped or received.  
* Service contracts.  

### To prepare VAT rate change conversions  
Before you set up the VAT rate change tool, you must make the following preparations.

* If you have transactions that use different rates, then they must be separated into different groups either by creating new general ledger accounts for each rate or by using data filters to group transactions according to rate.  
* If you create new general ledger accounts, then you must create new general posting groups.  
* To reduce the number of documents that get converted, post as many documents as possible and reduce unposted documents to a minimum.  
* Back up data.

### To set up the VAT rate change tool  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Rate Change Setup**, and then choose the related link.  
2. On the **Master Data**, **Journals**, and **Documents** FastTabs, choose a posting group value from the option list for needed fields.  

### To set up product posting group conversion  
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Rate Change Setup**, and then choose the related link.  
2. On the **VAT Rate Change Setup** page, on the **Home** tab, in the **Process** group, choose either **VAT Prod. Posting Group Conv.** or **Gen Prod. Posting Group Conv.**.  
3. In the **From Code** field, enter the current posting group.  
4. In the **To Code** field, enter the new posting group.  

### To perform VAT rate change conversion  
You use the VAT rate change tool to manage changes in the standard rate of VAT. You perform VAT and general posting group conversions to change VAT rates and maintain accurate VAT reporting. Depending on your setup, the following changes are made:  

* VAT and general posting groups are converted.  
* Changes are implemented in general ledger accounts, customers, vendors, open documents, journal lines, and so on.  

> [!IMPORTANT]  
>  Before you perform VAT rate change conversion, you can test the conversion. To do so, follow the steps below, but make sure to clear the **Perform Conversion** and **VAT Rate Change Tool Completed** check boxes. During test conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is cleared and the **Converted Date** field in the **VAT Rate Change Log Entry** table is blank. After the conversion is complete, choose **VAT Rate Change Log Entries** to view the results of the test conversion. Verify each entry before you perform the conversion. In particular, verify transactions that use an old VAT rate.     

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.  
2. Verify that you have already set up the VAT product posting group conversion or general product posting group conversion.  
3. Choose the **Perform Conversion** check box.  

    > [!IMPORTANT]  
    >  Clear the **VAT Rate Change Tool Completed** check box. The check box is automatically selected when the VAT rate change conversion is completed.  

4. Choose the **Convert** action.  
5. After the conversion is complete, on the **Home** tab, in the **Process** group, choose **VAT Rate Change Log Entries** to view the results of the conversion.  

> [!IMPORTANT]  
>  After the conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is chosen and the **Converted Date** field in the **VAT Rate Change Log Entry** table displays the conversion date.  

## See Also  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[How To: Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
