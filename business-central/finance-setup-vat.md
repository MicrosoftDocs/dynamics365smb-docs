---
title: Set Up Value-Added Tax
description: Make sure that you correctly calculate, post, and report on VAT for sales and purchases. We recommend that you use the assisted setup guide to set up VAT.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, posting, tax, value-added tax
ms.search.form: 10, 118, 391, 470, 471, 472, 575, 734, 747, 748, 1877, 
ms.date: 01/31/2023
ms.author: bholtorf
---

# Set Up Calculations and Posting Methods for Value-Added Tax

Consumers and businesses pay value-added tax (VAT) when they purchase goods or services. The amount of VAT to pay can vary, depending on several factors. In [!INCLUDE[prod_short](includes/prod_short.md)], you set up VAT to specify the rates used to calculate tax amounts based on the following parameters:

* Who you sell to  
* Who you buy from  
* What you sell  
* What you buy  

You can set up VAT calculations manually, but that can be tricky and time-consuming. It's easy to use different VAT rates by mistake and create inaccurate VAT-related reports. To make VAT set up easier, we recommend you use the assisted **VAT Setup** guide provided in the product. 

However, if you want to set up the VAT calculations yourself, or just want to learn about each step, this article contains descriptions of each step:  

[!INCLUDE [finance-vat](includes/finance-vat.md)]

## Set up VAT using the assisted setup guide (recommended)

> [!NOTE]
> You can use the **VAT Setup** guide only if you have created a *My Company* and have not yet posted transactions that include VAT.

To start the assisted setup guide, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon and enter **Assisted Setup**. 
2. Choose **Set up Value-Added Tax (VAT)** and complete the steps.
3. When you have completed the assisted setup, visit the **VAT Posting Setup** page to check if you need to fill in more fields according to the local requirements in your version of [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more at [Local functionality in Business Central](about-localization.md).  

### Check the VAT posting setup

To support your fast start, [!INCLUDE [prod_short](includes/prod_short.md)] notifies you of missing general ledger (G/L) accounts in posting groups or posting setups, such as on the **VAT Posting Setup** page. You can turn this type of notification on or off using the *G/L Account is missing in posting group or setup* notification in the **My Notifications** page. Just go to the **My settings** page, and then choose the *Change when I receive notifications.* link.  

If you choose such a notification, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates those posting setups based on the posting groups in the document or journal you're currently working on.  

At this point, you can just fill in the missing G/L accounts. But, later, when you further refine the setup, you might realize this initial setup is wrong. And [!INCLUDE [prod_short](includes/prod_short.md)] doesn't allow the deletion of a VAT posting setup and general posting setup when entries have been created based on such configurations. So starting in 2022 release wave 1, you can use the **Blocked** field on the **VAT Posting Setup** page to prevent users from mistakenly using a setup that is no longer relevant for new postings.

## Set up a default VAT date for documents and journals

VAT reporting in [!INCLUDE [prod_short](includes/prod_short.md)] is based on the **VAT Date** to include VAT entries on VAT reports in a VAT period. The VAT date can be changed on all documents and journals, but you must specify a default value for VAT date.

> [!NOTE]
> After posting the document or journal, the **VAT Date** will appear on **VAT Entries** and **G/L Entries** as well as on the posted document if exists.

To set up a default value for a VAT date, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon and enter **General Ledger Setup**, and then choose the related link.  
2. On the **General** FastTab, in the **Default VAT Date** field, choose either **Posting Date** or **Document Date**.
3. Close the page.  

> [!NOTE]
> By default, the **Default VAT Date** is the **Posting Date**.

### Enabling or disabling the VAT Date feature

Some countries/regions require that businesses use a specific VAT date, but other countries/regions don't. Some countries/regions also require businesses to change the VAT date in specific situations after they have posted documents, but other countries don't allow changes to VAT dates. To allow for different contexts, you can choose whether you want to use this functionality and, if so, to what degree.

To set up the level of VAT date usage, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon and enter **General Ledger Setup**, and then choose the related link.  
2. On the **General** FastTab, in the **VAT Date Usage** field, specify the degree to which you want to use the VAT date feature. You can choose one of the following options:

| Type | Description |
|--------------------|-----------------------------------------|
| **Use full VAT Date functionality** | Everything related to **VAT Date** works by default, giving you the maximum **VAT Date** functionality. You can set up the date, change it in documents, report based on it, and modify the date after posting as long as the period isn't closed or protected with allowed dates for posting. |
| **Use but do not allow modifications** | Everything related to **VAT Date** works by default with one exception. You can't modify the **VAT Date** in **VAT Entries**. |
| **Not using VAT Date functionality** | [!INCLUDE [prod_short](includes/prod_short.md)] will hide and make the **VAT Date** fields not available on documents, journals, and entries. The **Default VAT Date** is configured as the **Posting Date**. |

3. Close the page.

> [!IMPORTANT]
> Even if you choose the **Not using VAT Date functionality** option, [!INCLUDE [prod_short](includes/prod_short.md)] will use the **VAT Date** in the background. Because the **Default VAT Date** is configured as the **Posting Date**, and you can't change it in this case, you'll get the same experience as without this feature. **VAT Date** fields will be removed from all pages, but this field will still exist in tables and reports will work based on it.

### Limiting periods for posting and changing the VAT date

You can prevent people from posting or changing VAT entries in specific date ranges. You set the restriction using two settings:

* Based on closed **VAT Return Period**
* Based on the **Allow Posting From** and **Allow Posting To** fields.

#### To limit posting based on VAT return period

1. Choose the ![Lightbulb that opens the TellF Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General** FastTab, in the **Control VAT Period** field, specify the degree of VAT Return Period control. The following table describes the options.

| Type | Description |
|--------------------|-----------------------------------------|
| **Block posting within closed and warn for released period** | Prevent people from posting a document or journal, or changing VAT entries that have a VAT date within a closed **VAT Return Period**. [!INCLUDE [prod_short](includes/prod_short.md)] also shows a warning if your **VAT Return Period** is open, but the status of **VAT Return** is **Released** or **Submitted**. |
| **Block posting within closed period** | Prevent people from posting a document or journal, or changing vat entries that have a VAT date within the closed **VAT Return Period**. |
| **Warn when posting in closed period** | Show a warning, but don't block posting, if you want to post a document or journal that has a VAT date within a closed **VAT Return Period**. |
| **Disabled** | Take no action based on a closed **VAT Return Period**. |

#### Limit posting based on Allow from/to period

> [!NOTE]
> As of Business Central version 23.1, this control is changed. In earlier versions, there was only one control on the **General Ledger Setup** page for both Posting Date and VAT Date. Now, these controls are split, so control in the **General Ledger Setup** page is for the **Posting Date** only and control in the **VAT Setup** page is for the **VAT Date** only. There are also new date controls in the **User Setup** page.  

##### Version 23.1 or newer

> [!IMPORTANT]
> When you upgrade to a newversion, be aware that values are upgraded in the new **Allow VAT Date From/To** in the **VAT Setup** page based on the values in **Allow Posting From/To** in the **General Ledger Setup**. If you want to use different date controls, open the **VAT Setup** page and make changes.  

You can set up limitations on the company or at specific user levels.

To limit all postings for the whole company:

1. Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Setup**, and then select the related link.  
2. On the **VAT Date** FastTab, in the **Allow VAT Date From** field, specify the VAT date from which you allow posting. Posting a document or journal with a VAT date before this date isn't allowed.  
3. On the **VAT Date** FastTab, in the **Allow VAT Date To** field, specify the VAT date until which you allow posting. Posting a document or journal with a VAT date after this date isn't allowed. 

To limit postings for the specific user:  

1. Select the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then select the related link.  
2. In the **User ID** field, specify the user allowed to post in a specific period.  
3. In the **Allow VAT Date From** field, specify the VAT date from which you allow posting. Posting a document or journal with a VAT date before this date isn't allowed. 
4. In the **Allow VAT Date To** field, specify the VAT date until which you allow posting. Posting a document or journal with a VAT date after this date isn't allowed.  

##### Versions before 23.1 

You can set up limitation on the company or specific user levels.

To limit all postings for the whole company:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General** FastTab, in the **Allow Posting From** field, specify the VAT date from which you allow posting. Posting a document or journal with a VAT date before this date isn't allowed.  
3. On the **General** FastTab, in the **Allow Posting To** field, specify the VAT date until which you allow posting. Posting a document or journal with a VAT date after this date isn't allowed.

To limit postings for the specific user:

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.  
2. In the **User ID** field, specify the user allowed to post in specific period.  
3. In the **Allow Posting From** field, specify the VAT date from which you allow posting. Posting a document or journal with a VAT date before this date isn't allowed.
4. In the **Allow Posting To** field, specify the VAT date until which you allow posting. Posting a document or journal with a VAT date after this date isn't allowed.

## Set up VAT registration numbers for your country or region

To help ensure people enter valid VAT registration numbers, you can define formats for the VAT registration numbers that are used in the countries or regions in which you do business. [!INCLUDE[prod_short](includes/prod_short.md)] displays an error message if someone makes a mistake or uses a format that is incorrect for the country or region.

To set up VAT registration numbers, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 2.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Countries/Regions**.
2. Choose the country or region, and then choose the **VAT Reg. No. Formats** action.
3. In the **Formats** field, define the format by entering one or more of the following characters:  

* **#** Requires a single-digit number.  
* **@** Requires a letter. This format isn't case-sensitive.  
* **?** Allows any character.  

    > [!TIP]
    > You can use other characters as long as they are always present in the country or region format. So, if you need to include a period or a hyphen between sets of numbers, you can define the format as ##.####.### or @@-###-###.  

## Set up VAT business posting groups

VAT business posting groups should represent the markets in which you do business with customers and vendors, and define how to calculate and post VAT in each market. Examples of VAT business posting groups are **Domestic** and **European Union (EU)**.  

Use codes that are easy to remember and describe the business posting group, such as **EU**, **Non-EU**, or **Domestic**. Each code must be unique, meaning you can set up as many codes as you need, but you can't have the same code more than once in a table.

To set up a VAT business posting group, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 3.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Business Posting Groups**, and then choose the related link.  
2. Fill in the fields as necessary.

You can set up default VAT business posting groups by linking them to general business posting groups. [!INCLUDE[prod_short](includes/prod_short.md)] automatically assigns the VAT business posting group when you assign the business posting group to a customer, vendor, or general ledger account.

## Set up VAT product posting groups

VAT product posting groups represent the items and resources you buy or sell, and determine how to calculate and post VAT according to the type of item or resource.

It's a good idea to use codes that are easy to remember and describe the rate, such as **NO-VAT** or **Zero**, **VAT10** or **Reduced** for 10 percent VAT, and **VAT25** or **Standard** for 25 percent.

To set up a VAT business posting group, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature 4.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Product Posting Groups**, and then choose the related link.  
2. Fill in the fields as necessary.

## Combine VAT posting groups in VAT posting setups

[!INCLUDE[prod_short](includes/prod_short.md)] calculates VAT amounts on sales and purchases based on VAT posting setups, which are combinations of VAT business and product posting groups. For each combination, you can specify the VAT percent, VAT calculation type, and general ledger accounts for posting VAT for sales, purchases, and reverse charges. You can also specify whether to recalculate VAT when a payment discount is applied or received.  

Set up as many combinations as you need. To group VAT posting setup combinations with similar attributes, define a **VAT Identifier** for each group, and assign the identifier to the group members.  

> [!NOTE]
> A **VAT Identifier** is a code you can use to group similar attributes. We recommend you use different VAT identifiers for different VAT percentages.  

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

You set up a VAT clause to describe information about the type of VAT that is being applied. The information may be required by government regulations. After you set up a VAT clause, and associate it with a VAT posting setup, the VAT clause is displayed on printed sales documents that use the VAT posting setup group.

If needed, you can also specify how to translate VAT clauses to other languages. Then, when you create and print a sales document that contains a VAT identifier, the document will include the translated VAT clause. The language code specified on the customer card determines the language.

When non-standard VAT rates are used in different types of documents, such as invoices or credit memos, companies are usually required to include an exemption text (VAT clause) stating why a reduced VAT or zero VAT rate has been calculated. You can define different VAT clauses to be included on business documents per the type of document, such as invoice or credit memo. You do this on the **VAT Clauses by Document Type** page.

You can modify or delete a VAT clause, and your modifications will be reflected in a generated report. However, [!INCLUDE[prod_short](includes/prod_short.md)] doesn't keep a history of the change. On the report, the VAT clause descriptions are printed and displayed for all lines in the report alongside the VAT amount and the VAT base amount. If a VAT clause has not been defined for any lines on the sales document, then the whole section is omitted when the report is printed.

### To set up VAT clauses

1. Choose the ![Lightbulb that opens the Tell Me feature 9.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Clauses**, and then choose the related link.  
2. On the **VAT Clauses** page, create a new line.  
3. In the **Code** field, enter an identifier for the clause. You use this code to assign the clause to VAT posting groups.  
4. In the **Description** field, enter the VAT exemption text that you want to display on documents that can include VAT. In the **Description 2** field, enter more text, if needed. The text will be displayed on new document lines.
5. Choose the **Description by document type** action.
6. On the **VAT Clauses by Document Type** page, fill in the fields to set up which VAT exemption text to display for which document type.  
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

### To specify extended text for VAT clauses

> [!NOTE]  
> If your country or region requires longer text for the VAT clauses than the default version supports, you can specify the longer text for the VAT clauses as *extended text* so that it prints on the sales and purchase reports.  

1. Choose the ![Lightbulb that opens the Tell Me feature 11.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Clauses**, and then choose the related link.  
2. Choose the **Extended Texts** action.  
3. Choose the **New** action.  
4. Fill in the **Language Code** and **Description** fields.  
5. Optionally, select the **All Language Codes** field, or specify the relevant language in the **Language Code** field if you use language codes.  
6. Fill in the **Starting Date** and **Ending Date** fields if you want to limit the dates on which the extended text is used.  
7. In the **Text** lines, write the extended text for your VAT clauses.  
8. Select the relevant fields for the document types where you want the extended text printed.  
9. Close the page.  

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

Some companies must use reverse charge VAT when trading with other companies. For example, this rule applies to purchases from EU countries/regions and sales to EU countries/regions.  

> [!NOTE]  
> This rule applies when trading with companies that are registered as VAT liable in another EU country/region. If you do business directly with consumers in other EU countries/regions, then you should contact your tax authority for applicable VAT rules.  

> [!TIP]  
> You can verify that a company is registered as VAT liable in another EU country/region by using the EU VAT Registration Number Validation service. The service is available for free in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Verify VAT registration numbers](finance-how-validate-vat-registration-number.md).

### Sales to EU countries or regions

VAT isn't calculated on sales to VAT-liable companies in other EU countries/regions. You must report the value of these sales to EU countries/regions separately on your VAT statement.  

To correctly calculate VAT on sales to EU countries/regions, you should:  

* Set up a line for sales with the same information for purchases. If you have already set up lines on the **VAT Posting Setup** page for purchases from EU countries/regions, then you can also use these lines for sales.  
* Assign the VAT business posting groups in the **VAT Bus. Posting Group** field on the **Invoicing** FastTab of the customer card of each EU customer. You should also enter the customer's VAT registration number in the **VAT Registration No.** field on the **Foreign Trade** FastTab.  

When you post a sale to a customer in another EU country/region, the VAT amount is calculated, and a VAT entry is created by using the information about the reverse charge VAT and the VAT base, which is the amount that is used to calculate the VAT amount. No entries are posted to the VAT accounts in the general ledger.

If you want to use combination of VAT business posting group and VAT product posting group for reporting as services in the periodic VAT reports, mark the **EU Service** field.

> [!NOTE]  
> The **EU Service** field is only applicable for VAT reports. The field isn't related to the **Service Declaration** or **Intrastat for Services** features.

## VAT rounding for documents

Amounts in documents that are not yet posted are rounded and displayed to correspond with the final rounding of amounts that are actually posted. VAT is calculated for a complete document, which means that VAT is calculated based on the sum of all lines with the same VAT identifier in the document.  

## Set up VAT reporting

You must set up information about how the tax authorities in your country or region require you to submit VAT reports. The following steps illustrate the most commonly used information. However, your country or region may require other steps. For more information, see the relevant article in the *Local functionality* section in the panel to the left.

[!INCLUDE [vat-report-setup](includes/vat-report-setup.md)]

## See also

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

[!INCLUDE[footer-include](includes/footer-banner.md)]
