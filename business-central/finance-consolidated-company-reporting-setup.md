---
title: Set up company consolidation
description: Learn how you can configure how data from different companies in Business Central is reported into a consolidation company.
author: bholtorf

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: consolidation, subsidiaries, consolidate
ms.date: 10/01/2020
ms.author: bholtorf

---

# Set Up Company Consolidation

Before you can consolidate the general ledger entries of two or more separate companies (subsidiaries) into a consolidated company, you must prepare the charts of accounts and the consolidation company.  

Depending on the complexity of your businesses, there are two ways to set up consolidation:

* If you do not need advanced settings, such as including a company that you only own part of, you can use the **Company Consolidation** assisted setup guide to quickly set up a consolidation. The guide helps you through the basic steps.
* If you do need more advanced settings, you can set up the consolidated company and business units yourself.
  * In each business unit, specify which general ledger accounts are to be included in the consolidation, and specify the consolidation translation method for each account.
  * In the consolidation company, set up a business unit card for each company to be included in the consolidation. The business unit card includes information, such as the dates of the business unit's fiscal year, and the percentage of each account that must be included in the consolidation.

## Simple consolidation setup

If your consolidation is straightforward, for example because you wholly-own the business units to consolidate, the **Company Consolidation** assisted setup guide will help you through the following steps:

* Choose whether to create a new consolidated company, or whether to consolidate the data in a company that you have already created for the consolidation. The company should not contain transactions.
* Preview the results. [!INCLUDE[prod_short](includes/prod_short.md)] verifies that the master data and transactions can be successfully transferred to the consolidated company.

To use the assisted setup guide, follow these steps:

1. On the **Accountant** Role Center, choose the **Assisted Setup** action.
2. Choose **Set up consolidation reporting**, and then complete each step in the assisted setup guide.

## Advanced consolidation setup

If you need more advanced settings for your consolidation, you can set up consolidation manually. For example, if you have companies that you own only partially, or you have companies that you do not want to include in the consolidation.  

### Set up the consolidated company

First, you must set up the consolidated company. You set up the consolidated company in the same way that you set up other companies. For more information, see [Getting Ready for Doing Business](ui-get-ready-business.md).  

The following list illustrates key aspects of the consolidated company.

1. Set up the chart of accounts

    For more information, see [Setting Up or Changing the Chart of Accounts](finance-setup-chart-accounts.md).  

    The charts of accounts can be identical across a business unit and the consolidated company, or the consolidated company can have a different chart of account. If a business unit's chart of accounts is different from that of the consolidated company, you must specify the mapping between accounts on the accounts in the business unit. For more information, see the [Prepare general ledger accounts for consolidation](#glacc) section.

2. Add business units

    To consolidate several companies' financial data in a consolidated company, you must enter information about the subsidiary as business units to be included and about how much their figures will be included.

    For more information, see the [Add business units](#busunit) section.
3. You can specify exchange rates when consolidating the financial statements of business units if the financial statements are in a foreign currency.

    The three exchange rates that are used are **Average Rate (Manual)**, **Closing Rate**, and **Last Closing Rate**. For more information, see the [Specify exchange rates for consolidations](#exchrates) section.
4. You can consolidate dimension information and general ledger accounts.

    For more information, see the [Include or exclude dimensions](#dim) section.

### <a name="busunit"></a>Add business units

[!INCLUDE[prod_short](includes/prod_short.md)] lets you set up a list of business units to consolidate, verify the accounting data before you consolidate it, import files, and generate consolidation reports.  

1. Sign in to the consolidated company.
2. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Units**, and then choose the related link.  
3. Choose **New**, and then fill in the required fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!IMPORTANT]
    > When you fill in the **Starting Date** and **Ending Date** fields, make sure you comply with GAAP rules concerning the fiscal periods of the business unit versus the parent company.
4. Repeat step 3 for each additional business unit

If your business unit uses a foreign currency, you must specify the exchange rate to use in the consolidation. You must also enter consolidation information about the business unit's general ledger accounts. These processes are described in the following sections.

### <a name="glacc"></a>Prepare general ledger accounts for consolidation

The chart of accounts for a company that will be consolidated must specify accounts for consolidation. For each posting general ledger account in each company, you must specify the general ledger account in the consolidated company to which the balance will be transferred on consolidation. This is a mapping that will allow companies with different chart of accounts to be consolidated together.

If the chart of accounts in the business unit differs from the consolidated company, you must prepare general ledger accounts for consolidation. You can specify the accounts to post debits and credits to, and the method to use to translate currencies in the consolidated company. For example, this is useful if you frequently run the report.

1. In each business unit's [!INCLUDE [prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. Open the card for the account, and then fill in the fields on the **Consolidation** FastTab. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### <a name="exchrates"></a>Specify exchange rates for consolidations

If a business unit uses a different currency than the consolidated company, you must specify exchange rate methods for each account before you consolidate. For each account, the content of the **Consol. Translation Method** field determines the exchange rate. In the consolidated company, on each business unit card, in the **Currency Exchange Rate Table** field, you specify whether consolidation will use exchange rates from the business unit or the consolidated company. If you use exchange rates from the consolidated company, you can change the exchange rates for a business unit. For business units, if the **Currency Exchange Rate Table** field on the business unit card contains **Local**, you can change the exchange rate from the business unit card. The exchange rates are copied from the **Currency Exchange Rate** table, but you can change them before consolidating.

The following table describes the exchange rate methods you can use for accounts.

|Exchange rate | Typical use |
|---|---|
|Average Rate (Manual) | You manually calculate the average rate for the period to consolidate. Calculate the average either as an arithmetic average or as a best estimate, and specify the result for each business unit. Used for income statement accounts.|
|Closing Rate | Used for balance sheet accounts.|
|Last Closing Rate | The rate that was valid in the foreign exchange market on the date for which the balance sheet or income statement is being prepared. You enter this rate for each business unit. Used for balance sheet accounts.|
|Historical Rate | The exchange rate that was valid when the transaction occurred.|
|Composite Rate | The current period amounts are translated at the average rate and added to the previously recorded balance in the consolidated company. This method is typically used for retained earnings accounts because they include amounts from different periods and are therefore a composite of amounts translated with different exchange rates.|
|Equity Rate | This is similar to **Composite**. Differences are posted to separate general ledger accounts.|

To specify exchange rates for business units, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Units**, and then choose the related link.  
2. On the **Business Unit List** page, choose the business unit, and then choose the **Average Rate (Manual)** action.  
3. On the **Change Exchange Rate** page, the contents of the **Relational Exch. Rate** field have been copied from the **Currency Exchange Rate** table, but you can modify them. Close the page.  
4. Choose the **Closing Rate** action.  
5. In the **Relational Exch. Rate Amount** field, enter the exchange rate.

### <a name="dim"></a>Include or exclude dimensions

You can consolidate dimension information and general ledger accounts.

* On the relevant dimensions, specify the **Consolidation Code** field, or leave it blank
  * To exclude a dimension in the consolidation, leave the **Consolidation Code** field blank on the dimension, and do not choose dimensions in the **Copy Dimensions** fields in any consolidation functions or reports.
  * To include dimension information in the consolidation, leave the **Consolidation Code** field blank. However, the consolidation will only work if the dimension values in the business unit are the same as the consolidated company.
  * To consolidate the dimension value code in the business unit with a different dimension value code in the consolidated company, fill in the **Consolidation Code** field on the relevant dimensions.  
* Add the relevant dimensions to the relevant general ledger accounts

### <a name="exclude"></a>Exclude a company from consolidation

If you do not want to include a business unit in the consolidation, you can exclude it. To do that, go to the business unit card, and clear the **Consolidate** check box.

### <a name="include"></a>Include a partially-owned company in consolidation

If you own only part of a company, you can include a percentage of each transaction that corresponds to the percentage of the company you own. For example, if you own 70% of the company, consolidation will include $70 of an invoice for $100. To specify the percentage of the company you own, go to the business unit card, and enter the percentage in the **Consolidation %** field.  

## See Also

[Consolidating Financial Data from Multiple Companies](finance-consolidated-company-reporting.md)  
[Managing Intercompany Transactions](intercompany-manage.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exporting Your Business Data to Excel](about-export-data.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]