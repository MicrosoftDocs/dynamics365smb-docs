---
title: Set Up Value-Added Tax
description: Make sure that you correctly calculate, post, and report on VAT for sales and purchases. We recommend that you use the assisted setup guide to set up VAT.
author: brentholtorf

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.search.form: 10, 1877, 470, 471, 472
ms.date: 04/12/2022
ms.author: bholtorf

---

# Set Up Calculations and Posting Methods for Value-Added Tax

Consumers and businesses pay value-added tax (VAT) when they purchase goods or services. The amount of VAT to pay can vary, depending on several factors. In [!INCLUDE[prod_short](includes/prod_short.md)], you set up VAT to specify the rates to use to calculate tax amounts based on the following parameters:

* Who you sell to  
* Who you buy from  
* What you sell  
* What you buy  

You can set up VAT calculations manually, but that can be tricky and time consuming. To make it easy, we provide an assisted setup guide named **VAT Setup** that will help you with the steps. We recommend that you use the assisted setup guide to set up VAT.

> [!NOTE]  
> You can use the guide only if you have created a My Company, and have not posted transactions that include VAT. Otherwise, it would be very easy to use different VAT rates by mistake, and make VAT-related reports inaccurate.  

If you want to set up VAT calculations yourself, or just want to learn about each step, this article contains descriptions of each step.  

[!INCLUDE [finance-vat](includes/finance-vat.md)]

## Use the VAT Setup assisted setup guide to set up VAT (recommended)

We recommend that you use the VAT Setup assisted setup guide to set up VAT in [!INCLUDE[prod_short](includes/prod_short.md)].

To start the assisted setup guide, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**.  
2. Choose **Set up VAT** and complete the steps.
3. When you have completed the assisted setup, visit the **VAT Posting Setup** page and check if you have to fill in more fields according to the local requirements in your version of [!INCLUDE [prod_short](includes/prod_short.md)]. For more information, see [Local functionality in Business Central](about-localization.md)  

### Check the VAT posting setup

To support you in getting started fast, [!INCLUDE [prod_short](includes/prod_short.md)] will show you notifications if you are missing general ledger (G/L) accounts in posting groups or posting setups, such as the **VAT Posting Setup** page. You can switch this type of notification on or off using the *G/L accounts missing in posting group or setup* notification in the **My Notifications** page. Just go to the **My settings** page, and then choose the *Change when I receive notifications.* link.  

If you choose such a notification, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates those posting setups based on the posting groups in the document or journal you're currently working on.  

At this point, you might just fill in the missing G/L accounts. Then, later, when you further refine the setup, you might realize this setup was wrong. [!INCLUDE [prod_short](includes/prod_short.md)] does not allow the deletion of VAT posting setup and general posting setup when there are entries created based on such configurations. Starting in 2022 release wave 1, you can use the **Blocked** field in the **VAT Posting Setup** page to prevent users from mistakenly using a setup that is no longer relevant for new postings.

## Set up VAT registration numbers for your country or region

To help ensure that people enter valid VAT registration numbers, you can define formats for the VAT registration numbers that are used in the countries or regions in which you do business. [!INCLUDE[prod_short](includes/prod_short.md)] will display an error message when someone makes a mistake or uses a format that is incorrect for the country or region.

To setup VAT registration numbers, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Countries/Regions**.
2. Choose the country or region, and then choose the **VAT Reg. No. Formats** action.
3. In the **Formats** field, define the format by entering one or more of the following characters:  

* **#** Requires a single-digit number.  
* **@** Requires a letter. This format is not case-sensitive.  
* **?** Allows any character.  

    > [!Tip]
    > You can use other characters as long as they are always present in the country or region format. For example, if you need to include a period or a hyphen between sets of numbers, you can define the format as ##.####.### or @@-###-###.  

## Set up VAT business posting groups

VAT business posting groups should represent the markets in which you do business with customers and vendors, and define how to calculate and post VAT in each market. Examples of VAT business posting groups are **Domestic** and **European Union (EU)**.  

Use codes that are easy to remember and describe the business posting group, such as **EU**, **Non-EU**, or **Domestic**. The code must be unique. You can set up as many codes as you need, but you cannot have the same code more than once in a table.

To set up a VAT business posting group, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Business Posting Group**, and then choose the related link.  
2. Fill in the fields as necessary.

You set up default VAT business posting groups by linking them to general business posting groups. [!INCLUDE[prod_short](includes/prod_short.md)] automatically assigns the VAT business posting group when you assign the business posting group to a customer, vendor, or general ledger account.

## Set up VAT product posting groups

VAT product posting groups represent the items and resources you buy or sell, and determine how to calculate and post VAT according to the type of item or resource that is being bought or sold.  
It is a good idea to use codes that are easy to remember and describe the rate, such as **NO-VAT** or **Zero**, **VAT10** or **Reduced** for 10% VAT, and **VAT25** or **Standard** for 25%.

To set up a VAT business posting group, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Product Posting Groups**, and then choose the related link.  
2. Fill in the fields as necessary.

## Combine VAT posting groups in VAT posting setups

[!INCLUDE[prod_short](includes/prod_short.md)] calculates VAT amounts on sales and purchases based on VAT posting setups, which are combinations of VAT business and product posting groups. For each combination, you can specify the VAT percent, VAT calculation type, and general ledger accounts for posting VAT for sales, purchases, and reverse charges. You can also specify whether to recalculate VAT when a payment discount is applied or received.  

Set up as many combinations as you need. If you want to group VAT posting setup combinations with similar attributes, you can define a **VAT Identifier** for each group, and assign the identifier to the group members.

To combine VAT posting setups, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 5.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Assign VAT posting groups by default to multiple entities

If you want to apply the same VAT posting groups to multiple entities, you can set up [!INCLUDE[prod_short](includes/prod_short.md)] to do so by default. There are a couple of ways to do this:

* You can assign VAT business posting groups to general business posting groups, or customer or vendor templates
* You can assign VAT product posting groups on general product posting groups  

The VAT business or product posting group is assigned when you choose a business or product posting group for a customer, vendor, item, or resource.

## Assign VAT posting groups to accounts, customers, vendors, items, and resources

The following sections describe how to assign VAT posting groups to individual entities.

### To assign VAT posting groups to individual general ledger accounts

1. Choose the ![Lightbulb that opens the Tell Me feature 6.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. Open the **G/L Account** card for the account.  
3. On the **Posting** FastTab, in the **Gen. Posting Type** field, choose either **Sale** or **Purchase**.  
4. Choose the VAT posting groups to use for the sales or purchase account.  

### To assign VAT business posting groups to customers and vendors

1. Choose the ![Lightbulb that opens the Tell Me feature 7.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer** or **Vendor**, and then choose the related link.  
2. On the **Customer** or **Vendor** card, expand the **Invoicing** FastTab.  
3. Choose the VAT business posting group.  

### To assign VAT product posting groups to individual items and resources

1. Choose the ![Lightbulb that opens the Tell Me feature 8.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item** or **Resource**, and then choose the related link.  
2. Do one of the following:  

    * On the **Item** card, expand the **Price & Posting** FastTab, and then choose **Show more** to display the **VAT Product Posting Group** field.  
    * On the **Resource** card, expand the **Invoicing** FastTab.  
3. Choose the VAT product posting group.  

## Set up clauses to explain VAT exemption or non-standard VAT rates

You set up a VAT clause to describe information about the type of VAT that is being applied. The information may be required by government regulation. After you set up a VAT clause, and associate it with a VAT posting setup, the VAT clause is displayed on printed sales documents that use the VAT posting setup group.

If needed, you can also specify how to translate VAT clauses to other languages. Then, when you create and print a sales document that contains a VAT identifier, the document will include the translated VAT clause. The language code specified on the customer card determines the language.

When non-standard VAT rates are used in different types of documents, such as invoices or credit memos, companies are usually required to include an exemption text (VAT clause) stating why a reduced VAT or zero VAT rate has been calculated. You can define different VAT clauses to be included on business documents per the type of document, such as invoice or credit memo. You do this on the **VAT Clauses by Doc. Type** page.

You can modify or delete a VAT clause, and your modifications will be reflected in a generated report. However, [!INCLUDE[prod_short](includes/prod_short.md)] does not keep a history of the change. On the report, the VAT clause descriptions are printed and displayed for all lines in the report alongside the VAT amount and the VAT base amount. If a VAT clause has not been defined for any lines on the sales document, then the whole section is omitted when the report is printed.

### To set up VAT clauses

1. Choose the ![Lightbulb that opens the Tell Me feature 9.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Clauses**, and then choose the related link.  
2. On the **VAT Clauses** page, create a new line.  
3. In the **Code** field, enter an identifier for the clause. You use this code to assign the clause to VAT posting groups.  
4. In the **Description** field, enter the VAT exemption text that you want to display on documents that can include VAT. In the **Description 2** field, enter more text, if needed. The text will be displayed on new document lines.
5. Choose the **Description by Document Type** action.
6. On the **VAT Clauses by Doc. Type** page, fill in the fields to set up which VAT exemption text to display for which document type.  
7. Optional: To assign the VAT clause to a VAT posting setup right away, choose **Setup**, and then choose the clause. If you want to wait, you can assign the clause later on the **VAT Posting Setup** page.  
8. Optional: To specify how to translate the VAT clause, choose the **Translations** action.

### To assign a VAT clause to a VAT posting setup

1. Choose the ![Lightbulb that opens the Tell Me feature 10.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
2. In the **VAT Clause** column, choose the clause to use for each VAT posting setup it applies to.  

### To specify translations for VAT clauses

1. Choose the ![Lightbulb that opens the Tell Me feature 11.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Clauses**, and then choose the related link.  
2. Choose the **Translations** action.  
3. In the **Language Code** field, choose the language you are translating to.  
4. In the **Description** and **Description 2** fields, enter the translations of the descriptions. This text displays in the translated VAT report documents.  

## Create a VAT posting setup to handle Import VAT

You use the *Import VAT* feature when you need to post a document where the entire amount is VAT. You will use this if you receive an invoice from the tax authorities for VAT for imported goods.  

To set up codes for import VAT, follow these steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature 12.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Product Posting Groups**, and then choose the related link.  
2. On the VAT Product Posting Groups page, set up a new VAT product posting group for import VAT.  
3. Choose the ![Lightbulb that opens the Tell Me feature 13.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
4. On the VAT Posting Setup page, create a new line, or use an existing VAT business posting groups in combination with the new VAT product posting group for import VAT.  
5. In the **VAT Calculation Type** field, choose **Full VAT**.  
6. In the **Purchase VAT Account** field, enter the general ledger account to use for posting import VAT. All other accounts are optional.  

## Use reverse charge VAT for trade between EU countries or regions

Some companies must use reverse charge VAT when trading with other companies. For example this rule applies to purchases from EU countries/regions and sales to EU countries/regions.  

> [!NOTE]  
> This rule applies when trading with companies that are registered as VAT liable in another EU country/region. If you do business directly with consumers in other EU countries/regions, then you should contact your tax authority for applicable VAT rules.  

> [!TIP]  
> You can verify that a company is registered as VAT liable in another EU country by using the EU VAT Registration Number Validation service. The service is available for free in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Verify VAT registration numbers](finance-how-validate-vat-registration-number.md).

### Sales to EU countries or regions

VAT is not calculated on sales to VAT-liable companies in other EU countries/regions. You must report the value of these sales to EU countries/regions separately on your VAT statement.  

To correctly calculate VAT on sales to EU countries/regions, you should:  

* Set up a line for sales with the same information for purchases. If you have already set up lines on the VAT Posting Setup page for purchases from EU countries/regions, then you can also use these lines for sales.  
* Assign the VAT business posting groups in the **VAT Bus. Posting Group** field on the **Invoicing** FastTab of the customer card of each EU customer. You should also enter the customer's VAT registration number in the **VAT Registration No.** field on the **Foreign Trade** FastTab.  

When you post a sale to a customer in another EU country/region, the VAT amount is calculated, and a VAT entry is created by using the information about the reverse charge VAT and the VAT base, which is the amount that is used to calculate the VAT amount. No entries are posted to the VAT accounts in the general ledger.

## VAT rounding for documents

Amounts in documents that are not yet posted are rounded and displayed to correspond with the final rounding of amounts that are actually posted. VAT is calculated for a complete document, which means that VAT is calculated based on the sum of all lines with the same VAT identifier in the document.  

## Set up VAT reporting

You must set up information about how the tax authorities in your country or region require you to submit VAT reports. The following steps illustrate the most commonly used information. However, your country or region may require additional steps. For more information, see the relevant article in the *Local functionality* section in the panel to the left.

[!INCLUDE [vat-report-setup](includes/vat-report-setup.md)]

## See Also

[Set Up VAT Statement Templates and VAT Statement Names](finance-how-setup-vat-statement.md)  
[Set Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Work with the VAT Rate Change Tool](finance-how-use-vat-rate-change-tool.md)  
[Verify VAT registration numbers](finance-how-validate-vat-registration-number.md)  
[Local functionality in Business Central](about-localization.md)  
[VAT Reporting in the German version](LocalFunctionality/Germany/vat-reporting.md)  
[Belgian VAT](LocalFunctionality/Belgium/belgian-vat.md)  
[Italian VAT](LocalFunctionality/Italy/italian-vat.md)  
[Set Up Electronic VAT and ICP Declarations in the Dutch Version](LocalFunctionality/Netherlands/how-to-set-up-electronic-vat-and-icp-declarations.md)  
[VAT Reports in the Spanish Version](LocalFunctionality/Spain/vat-reports.md)  
[Set Up Goods and Services Tax Posting in the Australian Version](LocalFunctionality/Australia/how-to-set-up-goods-and-service-tax-posting.md)  
[VAT in the Czech Version](LocalFunctionality/Czech/finance-vat.md)  
[VAT Reporting in the Norwegian Version](LocalFunctionality/Norway/norwegian-vat-reporting.md)  
[Reporting Goods/Services Tax and Harmonized Sales Tax in Canada](LocalFunctionality/Canada/sales-tax-goods-services.md)  

## See Related Training at [Microsoft Learn](/learn/paths/process-vat-dynamics-365-business-central/)


[!INCLUDE[footer-include](includes/footer-banner.md)]
