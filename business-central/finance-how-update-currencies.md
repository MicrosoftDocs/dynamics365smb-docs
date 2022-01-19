---
title: Update Currency Exchange Rates (contains video)
description: Track amounts in different currencies using currency codes, let Business Central help you adjust FX exchange rates of posted entries with an external service.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: multiple currencies, adjust exchange rates, FX rates
ms.search.form: 5, 118
ms.date: 07/23/2021
ms.author: edupont

---
# Update Currency Exchange Rates

As companies operate in more countries/regions, it becomes essential that they are able to trade and report financial information in more than one currency. The local currency (LCY) is defined in the **General Ledger Setup** page as described in the article [Setting Up Finance](finance-setup-finance.md). Once the local currency (LCY) has been defined, it will be represented as a blank currency, so when the **Currency** field is blank, it means that the currency is LCY.  

Next, you must set up currency codes for each currency that you use if you buy or sell in currencies other than your local currency (LCY). Also bank accounts can be created using currencies. It is possible to record G/L transactions in different currencies, however, the G/L transaction will always be posted in the local currency (LCY).

> [!Important]
> Do not create the local currency code both in the **General Ledger Setup** and in the **Currencies** page. This will create confusion between the blank currency and the LCY code in the currency table, and bank accounts, customers or vendors might accidentally be created, some with the blank currency and some with the LCY code.

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a currency exchange rate assigned. By designating a second currency as a so-called additional reporting currency, [!INCLUDE[prod_short](includes/prod_short.md)] will automatically record amounts in both LCY and this additional reporting currency on each G/L entry and other entries, such as VAT entries. For more information, see [Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md). The additional reporting currency is most often used to facilitate financial reporting to owners that reside in countries/regions using different currencies than the local currency (LCY).  

> [!IMPORTANT]
> If you want to use an additional reporting currency for financial reporting, make sure that you understand the limitations. For more information, see [Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md).

## Currencies

> [!NOTE]  
> In [!INCLUDE[prod_short](includes/prod_short.md)] if you are looking for real time information about foreign exchange (FX) rates or historical rates, you will find it referred to as currency. In addition to this article, see also [Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md).

You specify the currency codes in the **Currencies**, including extra information and settings that are necessary for each currency code.

> [!TIP]
> Create the currencies with the international ISO code as the code to simplify working with the currency in the future.

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Code**|The identifier for the currency.|
|**Description**|A free text description of the currency.|
|**ISO Code**|The international three letter code to the currency defined in ISO 4217.|
|**ISO Numeric code**|The international numeric reference to the currency defined in ISO 4217.|
|**Exchange Rate Date**|The latest actual exchange rate date.|
|**EMU Currency**|Specifies if the currency is an EMU (Economic and Monetary Union) currency, such as EUR.|
|**Realized Gains Account**|The account where the actual gain will be posted when you receive payments for receivables or register the actual currency rate on payments to payables. For an example of a receivable currency transaction, see the example below this table. |
|**Realized Losses Account**|The account where the actual loss will be posted when you receive payments for receivables or register the actual currency rate on payments to payables. For an example of a receivable currency transaction, see the example below this table. |
|**Unrealized Gains Account**|The account where the theoretical gain will be posted when you perform a currency adjustment.|
|**Unrealized Losses Account**|The account where the theoretical loss will be posted when you perform a currency adjustment.|
|**Amount Rounding Precision**|Some currencies have other formats for invoice amounts than are defined in the **General Ledger Setup** page. If you change the amount rounding precision for a currency, all invoice amounts in that currency will be rounded with the updated precision.|
|**Amount Decimal Places**|Some currencies have other formats for invoice amounts than are defined in the **General Ledger Setup** page. If you change the amount decimal places for a currency, all invoice amounts in the currency will be rounded with the updated decimals|
|**Invoice Rounding Type**|Specifies the method to use if the amounts must be rounded. The options are **Nearest**, **Up**, and **Down**.|
|**Unit-Amount Rounding Precision**|Some currencies have other formats for unit amounts than are defined in the **General Ledger Setup** page. if you change the unit amount rounding precision for a currency, all unit amounts in the currency will be rounded with the updated precision.|
|**Unit-Amount Decimal Places**|Some currencies have other formats for unit amounts than are defined in the **General Ledger Setup** page. If you change the unit amount decimal places for a currency, all unit amounts in the currency will be rounded with the updated decimals.|
|**Application Rounding Precision**|Specifies the size of the interval that is allowed as a rounding difference when you apply entries in different currencies to one another.|
|**Conversion LCY Rounding. Debit Account**|Specifies conversion information that must also contain a debit account if you want to insert correction lines for rounding differences in the general journals using the **Insert Conv. LCY Rndg. Lines** action.|
|**Conversion LCY Rounding Credit Account**|Specifies conversion information that must also contain a credit account if you wish to insert correction lines for rounding differences in the general journals using the **Insert Conv. LCY Rndg. Lines** action.|
|**Last Date Adjusted**|The date of the last currency adjustment.|
|**Last Date Modified**|The date of the change to the setup of the currency.|
|**Payment Tolerance %**|The maximum payment tolerance % set for this currency. For more information, see [Payment Tolerance and Payment Discount Tolerance](finance-payment-tolerance-and-payment-discount-tolerance.md). |
|**Max. Payment Tolerance Amount**|The maximum payment tolerance amount set for this currency. For more information, see [Payment Tolerance and Payment Discount Tolerance](finance-payment-tolerance-and-payment-discount-tolerance.md). |
|**Currency Factor**|Specifies the relationship between the currency and the local currency using the actual currency rate.|
|**Realized G/L Gains Account**|Specifies the G/L account that is used to post exchange rate gains for currency adjustments between the local currency (LCY) and the additional reporting currency. The exchange rate gains are calculated when the Adjust Exchange Rates batch job is run to adjust general ledger accounts. This field might not be visible by default. It can be retrieved by personalizing the page.|
|**Realized G/L Losses Account**|Specifies the G/L account that is used to post exchange rate losses for currency adjustments between the local currency (LCY) and the additional reporting currency. The exchange rate gains are calculated when the Adjust Exchange Rates batch job is run to adjust general ledger accounts. This field might not be visible by default. It can be retrieved by personalizing the page.|
|**Residual Gains Account**|Specifies the G/L account that is used to post residual gain amounts (rounding differences) when an additional reporting currency is used in the general ledger application area. This field might not be visible by default. It can be retrieved by personalizing the page.|
|**Residual Losses Account**|Specifies the G/L account that is used to post residual loss amounts (rounding differences) when an additional reporting currency is used in the general ledger application area. This field might not be visible by default. It can be retrieved by personalizing the page.|
|**Max. VAT Difference Allowed**|The maximum amount allowed for VAT differences in this currency. For more information, see [Correcting VAT Amounts Manually in Sales and Purchase Documents](finance-work-with-vat.md#correcting-vat-amounts-manually-in-sales-and-purchase-documents). This field might not be visible by default. It can be retrieved by personalizing the page.|
|**VAT Rounding Type**|Specifies the rounding method for correcting VAT amounts manually in sales and purchase documents. This field might not be visible by default. It can be retrieved by personalizing the page.|

### Example of a receivable currency transaction

When you receive an invoice from a company in a foreign currency, it is fairly easy to calculate the local currency (LCY) value of the invoice based on today's currency rate. However, the invoice often comes with payment terms so you can delay the payment to a later date, which implies a potentially different currency rate. This issue in combination with the fact that bank currency rates always differ from the official currency rates makes it impossible to anticipate the exact local currency (LCY) amount that is required to cover the invoice. If the due date of the invoice extends to the next month, you might also have to revaluate the local currency (LCY) amount at the end of the month. The currency adjustment is necessary because the new LCY value that is required to cover the invoice amount might be different, and the company debt to the vendor has potentially changed. The new LCY amount might be higher or lower than the previous amount and will therefore represent a gain or a loss. However, since the invoice has not been paid yet, the gain or loss is considered *unrealized*. Later, the invoice is paid, and the bank has returned with the actual currency rate for the payment. It is not until now the *realized* gain or loss is calculated. This unrealized gain or loss is then reversed, and the realized gain or loss is posted instead.

In the following example, an invoice is received on January 1 with the currency amount of 1000. At the time, the currency rate is 1.123.

|Date|Action|Currency Amount|Document Rate|LCY Amount on document|Adjustment Rate|Unrealized Gains Amount|Payment Rate|Realized Losses Amount|  
|-----|----------|------------|-----------|---------|-----------|-------------|---------|---------|
|1/1|**Invoice**|1000|1.123|1123|||||
|1/31|**Adjustment**|1000||1125|1.125|2|||
|2/15|**Adjustment Reversal on payment**|1000||||-2|||
|2/15|**Payment**|1000||1120|||1.120|-3|

At the end of the month, a currency adjustment is performed where the adjustment currency rate has been set to 1.125, which triggers an unrealized gain of 2.

At the time of payment, the actual currency rate registered on the bank transaction shows a currency rate of 1.120.

Here there is an unrealized transaction, and therefore it will be reversed together with the payment.

Finally, the payment is registered and the actual loss is posted to the realized losses account.

## Available Currency Functions

The following table outlines key actions on the **Currencies** page. Some of the actions are explained in the next sections.  

|Menu|Action|Description|
|-------------|--------------|------------------------------|
|**Process**|**Suggest Accounts**|Use accounts from the other currencies. The most frequently used accounts will be inserted.|
||Change Payment Tolerance|Change either or both the maximum payment tolerance and the payment tolerance percentage, and filter by currency. For more information, see [Payment Tolerance and Payment Discount Tolerance](finance-payment-tolerance-and-payment-discount-tolerance.md)|
||**Exch. Rates**|View updated exchange rates for the currencies that you use.|
||**Adjust Exch. Rates**|Adjust general ledger, customer, vendor, and bank account entries to reflect a more updated balance if the exchange rate has changed since the entries were posted.|
||**Exchange Rate Adjust. Register**|View the results of running the **Adjust Exchange Rates** batch job. One line is created for each currency or each combination of currency and posting group that is included in the adjustment.|
|**Exchange Rate Service**|**Exchange Rate Services**|View or edit the setup of the services that are set up to fetch updated currency exchange rates when you choose the **Update Exchange Rates** action.|
||**Update Exchange Rates**|Get the latest currency exchange rates from a service provider.|
|**Reports**|**Foreign Currency Balance**|View the balances for all customers and vendors in both foreign currencies and in local currency (LCY). The report displays two LCY balances. One is the foreign currency balance converted to LCY by using the exchange rate at the time of the transaction. The other is the foreign currency balance converted to LCY by using the exchange rate of the work date.|

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

The adjustment exchange rate amount or relational adjustment exchange rate amount will be used to update all open bank, receivables, or payables transactions.  

> [!Note]
> The actual currency rate will be calculated using this formula:
>
> `Currency Amount = Amount / Adjustment Exch. Rate Amount * Relational Adjmt Exch. Rate Amt`

## Adjusting Exchange Rates

Because exchange rates fluctuate constantly, additional currency equivalents in your system must be adjusted periodically. If these adjustments are not done, amounts that have been converted from foreign (or additional) currencies and posted to the general ledger in LCY may be misleading. In addition, daily entries posted before a daily exchange rate is entered into application must be updated after the daily exchange rate information is entered.

The **Adjust Exchange Rates** batch job is used to manually adjust the exchange rates of posted customer, vendor, and bank account entries. It can also update additional reporting currency amounts on G/L entries.  

> [!TIP]
> You can use a service to update exchange rates in the system automatically. For more information, see [To set up a currency exchange rate service](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service). However, this does not adjust exchange rates on already posted transactions. To update exchange rates on posted entries, use the **Adjust Exchange Rates** batch job.

### Effect on Customers and Vendors

For customer and vendor accounts, the batch job adjusts the currency by using the exchange rate that is valid on the posting date that is specified in the batch job. The batch job calculates the differences for the individual currency balances and posts the amounts to the general ledger account that is specified in the **Unrealized Gains Acc.** field or the **Unrealized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the receivables/payables account in the general ledger.

The batch job processes all open customer ledger entries and vendor ledger entries. If there is an exchange rate difference for an entry, the batch job creates a new detailed customer or vendor ledger entry, which reflects the adjusted amount on the customer or vendor ledger entry.

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

> [!NOTE]
> Most exchange rate services provide data that is compatible with the import process in [!INCLUDE[prod_short](includes/prod_short.md)]. However, sometimes the data is formatted differently and you will need to customize your import process. You can use the data exchange framework to do that by adding your own codeunit. You'll probably need some help from a developer to do that. For more information, see [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currency Exchange Rate Services**, and then choose the related link.
2. Choose the **New** action.
3. On the **Currency Exchange Rate Service** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Turn on the **Enabled** toggle to enable the service.

> [!NOTE]
> The following video shows an example of how to connect to a currency exchange rate service, using the European Central Bank as an example. In the segment that describes how to set up field mappings, the setting in the **Source** column for the **Parent Node for Currency Code**  will only return the first currency found. The setting should be `/gesmes:Envelope/Code/Code/Code`.

<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4A1jy?rel=0]

## To update currency exchange rates through a service
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.
2. Choose the **Update Exchange Rates** action.

The value in the **Exchange Rate** field on the **Currencies** page is updated with the latest currency exchange rate.

## See Related Training at [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## See Also
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
