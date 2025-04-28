---
title: Set up company consolidation
description: Learn how you can configure how data from different companies in Business Central is reported into a consolidation company.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 04/25/2025
ms.custom: bap-template
ms.search.keywords: consolidation, subsidiaries, consolidate
ms.search.form: 240, 1826, 1827
ms.service: dynamics-365-business-central
---

# Set up company consolidation

Before you can consolidate the general ledger entries of two or more companies (subsidiaries) into a consolidated company, you must prepare the charts of accounts and the consolidation company.  

Depending on the complexity of your businesses, there are two ways to set up consolidation:

* If you don't need advanced settings, such as including a company that you only own part of, you can use the **Company Consolidation** setup guide to quickly set-up a consolidation. The guide helps you through the basic steps.
* If you need more advanced settings, you can set up the consolidated company and business units yourself.
  * In each business unit, specify the general ledger accounts to include in the consolidation and the translation method for each account.
  * In the consolidated company, set up a business unit card for each company to include in the consolidation. The business unit card includes information such as the dates of the business unit's fiscal year, and the percentage of each account to include in the consolidation.

## Simple consolidation setup

If your consolidation is straightforward, for example because you wholly own the business units to consolidate, the **Company Consolidation** guide helps you through the following steps:

* Create a new consolidated company, or consolidate a company you already created. The company shouldn't contain transactions.
* Preview the results. [!INCLUDE[prod_short](includes/prod_short.md)] verifies that you can successfully transfer the master data and transactions to the consolidated company.

To use the assisted setup guide, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assisted Setup**, and then choose the related link.
2. Choose **Process Consolidations**, and then complete each step in the Company Consolidation assisted setup guide.

## Advanced consolidation setup

If you need more advanced settings for your consolidation, you can set up consolidation manually. For example, if you have companies that you partially own, or you have companies that you don't want to include.  

### Set up the consolidated company

First, you must set up the consolidated company. You set up the consolidated company in the same way that you set up other companies. To learn more about setting up a company, go to [Getting Ready for Doing Business](ui-get-ready-business.md).  

The following list illustrates key aspects of the consolidated company.

1. Set up the chart of accounts.

    To learn more about setting up a chart of accounts, go to [Setting Up or Changing the Chart of Accounts](finance-setup-chart-accounts.md).  

    The charts of accounts can be identical across a business unit and the consolidated company, or the consolidated company can have a different chart of account. If a business unit's chart of accounts differs from the consolidated company's, you must map the accounts to the accounts in the business unit. To learn more, go to the [Prepare general ledger accounts for consolidation](#glacc) section.

2. Add business units.

    To consolidate several companies' data, you must set up the subsidiaries as business units and specify how much of their balances to include. To learn more about business units, to go the [Add business units](#busunit) section.

3. Specify exchange rates, if needed.

    Specify exchange rates if you consolidate data for business units that use different currencies. The exchange rates you can use are **Average Rate (Manual)** and **Closing Rate**. To learn more about exchange rates, go to [Specify exchange rates for consolidations](#exchrates).

4. Consolidate dimension information and general ledger accounts.

    To learn more, go to the [Include or exclude dimensions](#dim) section.

### <a name="busunit"></a>Add business units

In the consolidated company, set up each company that you want to consolidate data from as a business unit. Before you run a consolidation and generate your consolidation report, it's a good idea to verify the financial data in each business unit.

A significant part of setting up the business unit is to specify how the unit shares it's financial data with the consolidated company. There are manual and automated options:

* To use a manual process, for [!INCLUDE [prod_short](includes/prod_short.md)] online and on-premises, you can export an .xml file that contains the unit's general ledger entries. Then import the file in the consolidated company.
* To automate the data exchange, for [!INCLUDE [prod_short](includes/prod_short.md)] online you can use an API that [!INCLUDE [prod_short](includes/prod_short.md)] provides to share data across environments. If your companies are in the same environment, you can use the **Database** option.

> [!NOTE]
> The API option also lets you share general ledger entries from other [!INCLUDE [prod_short](includes/prod_short.md)] environments. To use the API option, the user who configures the consolidation must have permission to access G/L entries. For example, the D365 Basic and D365 Read permission sets provide access.

#### Set up business unit currencies

When you run consolidation for business units in a foreign currency, pay attention to the exchange rates that various parts of the process use. This is especially true when you rerun consolidation. Use the **Set Up Business Unit Currencies** page to easily keep track of the rates.

The **Set Up Business Unit Currencies** page gives you the last rates for average and closing. You can look up the exchange rates in the currency exchange rate table, which makes it easier to validate rates. You can change the rates for the current run by entering the values or copying them from previous runs. To copy rates, choose **Select from previous consolidation**. This page is valuable when you want to rerun a previous consolidation and use a previous closing rate. This step helps to correctly revaluate your balance sheet items. The **Select from previous consolidation** page is also useful if you just want to view the rates that were used, for example, when you're troubleshooting. The page is filtered to runs that included the selected business unit.

You start the **Run Consolidation** batch job from the **Business Units** list page. You can also find the **Set Up Business Unit Currencies** page by choosing the **Exchange Rates** action.

> [!NOTE]
> The exchange rate setup pages for average and closing that are currently available on the **Business Unit** card will be deprecated in a future version. However, you can still maintain these rates if you have business units that you import through files.

#### Create a business unit

1. Sign in to the consolidated company.
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Units**, and then choose the related link.  
3. Choose **New**, and then fill in the required fields on the **General** and **G/L Accounts** FastTabs. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!IMPORTANT]
    > When you fill in the **Starting Date** and **Ending Date** fields, make sure you comply with GAAP rules concerning the fiscal periods of the business unit versus the parent company.
4. On the **Data Import** FastTab, in the **Default Data Import** field, specify how you share general ledger entries with the consolidated company:

   * To share data between companies in the same environment, choose **Database**.
   * To share data between companies in different environments, choose **API**, and then fill in the **API's Endpoint** field.
        
        To get the endpoint URL, in the business unit company's [!INCLUDE [prod_short](includes/prod_short.md)], open the **Consolidation Setup Page** and check the Current environment's API Endpoint field value. 
   * To export an .xml file and manually share it, choose **File Format**.

### <a name="glacc"></a>Prepare general ledger accounts for consolidation

The chart of accounts for a company that you will consolidate must specify accounts for consolidation. For each posting general ledger account in each company, you must specify the general ledger account in the consolidated company to transfer the balance to. This mapping lets you consolidate companies that have different charts of accounts.

If the chart of accounts in the business unit differs from the consolidated company, you must prepare general ledger accounts for consolidation. You can specify the accounts to post debits and credits to, and the method to use to translate currencies in the consolidated company.

1. In each business unit's [!INCLUDE [prod_short](includes/prod_short.md)], choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. Open the card for the account, and then fill in the fields on the **Consolidation** FastTab. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> If you don't fill in the **Consol. Debit Acc.** and **Consol. Credit Acc.** fields, [!INCLUDE [prod_short](includes/prod_short.md)] assumes they're mapped to the same accounts in the consolidated company.

> [!TIP]
> There might be scenarios where you don't want to include an account in a consolidation. For example, if you want your consolidation company to reflect only the balance sheets from the subsidiary companies. To exclude an account from consolidation, turn on the **Exclude from Consolidation** toggle for the account.

### <a name="exchrates"></a>Specify exchange rates for consolidations

If a business unit uses a different currency than the consolidated company, you must specify exchange rate methods for each account before you consolidate. For each account, the content of the **Consol. Translation Method** field determines the exchange rate. In the consolidated company, on each business unit card, in the **Currency Exchange Rate Table** field you specify whether consolidation uses exchange rates from the business unit or the consolidated company. If you use exchange rates from the consolidated company, you can change the exchange rates for a business unit. For business units, if the **Currency Exchange Rate Table** field on the business unit card contains **Local**, you can change the exchange rate from the business unit card. The exchange rates are copied from the **Currency Exchange Rate** table, but you can change them before consolidating.

The following table describes the exchange rate methods you can use for accounts.

|Exchange rate | Typical use |
|---|---|
|Average Rate (Manual) | You manually calculate the average rate for the period to consolidate. Calculate the average either as an arithmetic average or as a best estimate, and specify the result for each business unit. Use for income statement accounts.|
|Closing Rate | Used for balance sheet accounts.|
|Historical Rate | The exchange rate that was valid when the transaction occurred.|
|Composite Rate | The current period amounts are translated at the average rate and added to the previously recorded balance in the consolidated company. You typically use this method for retained earnings accounts. Those accounts include amounts from different periods, so they contain amounts translated with different exchange rates.|
|Equity Rate | This option is similar to **Composite**. Differences post to separate general ledger accounts.|

To specify exchange rates for a business unit, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Business Units**, and then choose the related link.  
2. On the **Business Unit List** page, choose the business unit, and then choose the **Exchange Rates** action.  
3. On the **Setup Business Unit Currencies** page, fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### <a name="dim"></a>Include or exclude dimensions

You can consolidate dimension information and general ledger accounts.

* On the dimensions, specify the **Consolidation Code** field, or leave it blank.
  * To exclude a dimension in the consolidation, leave the **Consolidation Code** field blank on the dimension, and don't choose dimensions in the **Copy Dimensions** fields in any consolidation functions or reports.
  * To include dimension information in the consolidation, leave the **Consolidation Code** field blank. However, the consolidation works only if the dimension values in the business unit are the same as the consolidated company.
  * To consolidate the dimension value code in the business unit with a different dimension value code in the consolidated company, fill in the **Consolidation Code** field on the dimensions.  
* Add the dimensions to the general ledger accounts.

### <a name="exclude"></a>Exclude a company from consolidation

If you don't want to include a business unit in the consolidation, you can exclude it. To do that, go to the business unit card, and clear the **Consolidate** checkbox.

### <a name="include"></a>Include a partially owned company in consolidation

If you own only part of a company, you can include a percentage of each transaction that reflects the percentage you own. For example, if you own 70% of the company, consolidation includes $70 of an invoice for $100. To specify the percentage of the company you own, go to the business unit card and enter the percentage in the **Consolidation %** field.  

## Related information

[Consolidating Financial Data from Multiple Companies](finance-consolidated-company-reporting.md)  
[Managing Intercompany Transactions](intercompany-manage.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exporting Your Business Data to Excel](about-export-data.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
