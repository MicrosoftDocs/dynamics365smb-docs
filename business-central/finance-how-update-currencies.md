---
title: Update Currency Exchange Rates
description: Track amounts in different currencies using currency codes, and let Business Central help you adjust exchange rates of posted entries with an external service.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: multiple currencies, adjust exchange rates
ms.date: 05/26/2021
ms.author: edupont

---
# Update Currency Exchange Rates

As companies operate in more countries/regions, it becomes essential that they are able to trade and report financial information in more than one currency. The local currency (LCY) is defined in the **General Ledger Setup** page as described in the article [Setting Up Finance](finance-setup-finance.md). Once the local currency (LCY) has been defined, it will be represented as a blank currency, so when the **Currency** field is blank, it means that the currency is LCY.  

Next, you must set up currency codes for each currency that you use if you buy or sell in currencies other than your local currency (LCY). Also bank accounts can be created using currencies. It is possible to record G/L transactions in different currencies, however, the G/L transaction will always be posted in the local currency (LCY).

> [!Important]
> Do not create the local currency code both in the **General Ledger Setup** and in the **Currencies** page. This will create confusion between the blank currency and the LCY code in the currency table, and bank accounts, customers or vendors might accidentally be created, some with the blank currency and some with the LCY code.

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a current exchange rate assigned. By designating a second currency as a so-called additional reporting currency, [!INCLUDE[prod_short](includes/prod_short.md)] will automatically record amounts in both LCY and this additional reporting currency on each G/L entry and other entries, such as VAT entries. For more information, see [Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md). The additional reporting currency is most often used to facilitate financial reporting to owners that reside in countries/regions using different currencies than the local currency (LCY).

## Exchange Rates

The exchange rates are the tool to calculate the local currency value (LCY) of each currency transaction. The **Exchange Rates** page includes the following fields:

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Starting Data**|The date when the currency rate was effectuated|  
|**Currency Code**|The currency code related to this exchange rate|  
|**Relational Currency Code**|If this currency is part of a triangular currency calculation, then the related currency code can be set up here|  
|**Exchange Rate Amount**|The exchange rate amount is the rate to use for the currency code selected on the line. Normally 1 or 100|  
|**Relational Exch. Rate Amount**|The relational exchange rate amount relates to the rate to use for the relational currency code|  
|**Adjustment Exch. Rate Amount**|The adjustment exchange rate amount is the rate to use for the currency code selected on the line for use of the **Adjust Exchange Rates** batch job|  
|**Relational Adjmt Exch. Rate Amt**|The relational adjustment exchange rate amount is the rate to use for the currency code selected on the line for use of the **Adjust Exchange Rates** batch job|  
|**Fix Exchange Rate Amount**|Specifies if the currency's exchange rate can be changed on invoices and journal lines.|  

In general, the values of the **Exchange Rate Amount** and **Relational Exchange Rate Amount** fields are used as the default currency rate on all new receivables and payables documents that are created going forward. The document is assigned the currency rate according to the current working date.  

> [!Note]
> The actual currency rate will be calculated using this formula:
> 
> `Currency Amount = Amount / Exchange Rate Amount * Relational Exch. Rate Amount`

The adjustment exchange rate amount or relational adjustment exchange rate amount will be used to update all open bank, receivable or payable transactions.  

> [!Note]
> The actual currency rate will be calculated using this formula:
> 
> `Currency Amount = Amount / Adjustment Exch. Rate Amount * Relational Adjmt Exch. Rate Amt`

## Adjusting Exchange Rates

Because exchange rates fluctuate constantly, additional currency equivalents in your system must be adjusted periodically. If these adjustments are not done, amounts that have been converted from foreign (or additional) currencies and posted to the general ledger in LCY may be misleading. In addition, daily entries posted before a daily exchange rate is entered into application must be updated after the daily exchange rate information is entered.

The **Adjust Exchange Rates** batch job is used to manually adjust the exchange rates of posted customer, vendor and bank account entries. It can also update additional reporting currency amounts on G/L entries.  

> [!TIP]
> You can use a service to update exchange rates in the system automatically. For more information, see [To set up a currency exchange rate service](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service). However, this does not adjust exchange rates on already posted transactions. To update exchange rates on posted entries, use the **Adjust Exchange Rates** batch job.

### Effect on Customers and Vendors

For customer and vendor accounts, the batch job adjusts the currency by using the exchange rate that is valid on the posting date that is specified in the batch job. The batch job calculates the differences for the individual currency balances and posts the amounts to the general ledger account that is specified in the **Unrealized Gains Acc.** field or the **Unrealized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the receivables/payables account in the general ledger.

The batch job processes all open customer ledger entries and vendor ledger entries. If there is an exchange rate difference for an entry, the batch job creates a new detailed customer or vendor ledger entry which reflects the adjusted amount on the customer or vendor ledger entry.

#### Dimensions on Customer and Vendor Ledger Entries
The adjustment entries are assigned the dimensions from the customer/vendor ledger entries, and the adjustments are posted per combination of dimension values.

### Effect on Bank Accounts
For bank accounts, the batch job adjusts the currency by using the exchange rate that is valid on the posting date specified in the batch job. The batch job calculates the differences for each bank account that has a currency code and posts the amounts to the general ledger account that is specified in the **Realized Gains Acc.** field or the **Realized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the general ledger bank accounts that are specified in the bank account posting groups. The batch job calculates one entry per currency per posting group.

#### Dimensions on Bank Account Entries
The adjustment entries for the bank account's general ledger account and for the gain/loss account are assigned the bank account's default dimensions.

### Effect on G/L Accounts
If you post in an additional reporting currency, you can have the batch job create new general ledger entries for currency adjustments between LCY and the additional reporting currency. The batch job calculates the differences for each general ledger entry and adjusts the general ledger entry depending on the contents of the **Exchange Rate Adjustment** field for each general ledger account.

##### Dimensions on G/L Account Entries
The adjustment entries are assigned the default dimensions from the accounts they are posted to.

> [!Important]
> Before you can use the batch job, you must enter the adjustment exchange rates that are used to adjust the foreign currency balances. You do so on the **Currency Exchange Rates** page.<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Q24s?rel=0]

## To set up a currency exchange rate service
You can use an external service to keep your currency exchange rates up to date, such as FloatRates.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currency Exchange Rate Services**, and then choose the related link.
2. Choose the **New** action.
3. On the **Currency Exchange Rate Service** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **Enabled** check box to enable the service.
<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4A1jy?rel=0]

## To update currency exchange rates through a service
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.
2. Choose the **Update Exchange Rates** action.

The value in the **Exchange Rate** field on the **Currencies** page is updated with the latest currency exchange rate.

## See Related Training at [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## See Also
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
