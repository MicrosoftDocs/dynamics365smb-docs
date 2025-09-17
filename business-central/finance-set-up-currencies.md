---
title: Set up currencies
description: You must set up each currency if you buy or sell in currencies other than your local currency (LCY), or if you record G/L transactions in different currencies.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: multiple currencies
ms.search.form: 5, 118
ms.date: 06/10/2024
ms.service: dynamics-365-business-central

---
# Set up currencies

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

Use an external service to get the latest currency exchange rates into the **Currencies** list. For more information, see [To set up a currency exchange rate service](finance-how-update-currencies.md#set-up-a-currency-exchange-rate-service).  

[!INCLUDE [finance-currencies-lcy](includes/finance-currencies-lcy-note.md)]

## <a name="curr"></a>Currencies

The following table describes the fields in the **Currencies** list.

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Code**|The identifier for the currency.|
|**Description**|A free text description of the currency.|
|**ISO Code**|The international three letter code to the currency defined in ISO 4217.|
|**ISO Numeric code**|The international numeric reference to the currency defined in ISO 4217.|
|**Exchange Rate Date**|The latest actual exchange rate date.|
|**EMU Currency**|Specifies if the currency is an EMU (Economic and Monetary Union) currency, such as EUR.|
|**Realized Gains Account**|The account where the actual gain is posted when you receive payments for receivables or register the actual currency rate on payments to payables. For an example of a receivable currency transaction, see the example below this table. |
|**Realized Losses Account**|The account where the actual loss is posted when you receive payments for receivables or register the actual currency rate on payments to payables. For an example of a receivable currency transaction, see the example below this table. |
|**Unrealized Gains Account**|The account where the theoretical gain is posted when you perform a currency adjustment.|
|**Unrealized Losses Account**|The account where the theoretical loss is posted when you perform a currency adjustment.|
|**Amount Rounding Precision**|Some currencies have other formats for invoice amounts than are defined in the **General Ledger Setup** page. If you change the amount rounding precision for a currency, all invoice amounts in that currency are rounded with the updated precision.|
|**Amount Decimal Places**|Some currencies have other formats for invoice amounts than are defined in the **General Ledger Setup** page. If you change the amount decimal places for a currency, all invoice amounts in the currency are rounded with the updated decimals|
|**Invoice Rounding Type**|Specifies the method to use if the amounts must be rounded. The options are **Nearest**, **Up**, and **Down**.|
|**Unit-Amount Rounding Precision**|Some currencies have other formats for unit amounts than are defined in the **General Ledger Setup** page. if you change the unit amount rounding precision for a currency, all unit amounts in the currency are rounded with the updated precision.|
|**Unit-Amount Decimal Places**|Some currencies have other formats for unit amounts than are defined in the **General Ledger Setup** page. If you change the unit amount decimal places for a currency, all unit amounts in the currency are rounded with the updated decimals.|
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
|**Max. VAT Difference Allowed**|The maximum amount allowed for VAT differences in this currency. For more information, see [Correcting VAT amounts manually on sales and purchase documents](finance-work-with-vat.md#correcting-vat-amounts-manually-on-sales-and-purchase-documents). This field might not be visible by default. It can be retrieved by personalizing the page.|
|**VAT Rounding Type**|Specifies the rounding method for correcting VAT amounts manually in sales and purchase documents. This field might not be visible by default. It can be retrieved by personalizing the page.|

### Available currency functions

The following table outlines key actions on the **Currencies** page.  

|Menu|Action|Description|
|-------------|--------------|------------------------------|
|**Process**|**Suggest Accounts**|Use accounts from the other currencies. The most frequently used accounts are inserted.|
||**Change Payment Tolerance**|Change either or both the maximum payment tolerance and the payment tolerance percentage, and filter by currency. For more information, see [Payment Tolerance and Payment Discount Tolerance](finance-payment-tolerance-and-payment-discount-tolerance.md)|
||**Exchange Rates**|View updated exchange rates for the currencies that you use.|
||**Adjust Exchange Rates**|Update balances for general ledger, customer, vendor, and bank account entries. The update is useful if the exchange rate changed after the entries were posted.|
||**Exchange Rate Adjustment Register**|View the results of running the **Adjust Exchange Rates** batch job. One line is created for each currency or each combination of currency and posting group that is included in the adjustment.|
|**Exchange Rate Service**|**Exchange Rate Services**|View or edit the setup of the services that are set up to fetch updated currency exchange rates when you choose the **Update Exchange Rates** action.|
||**Update Exchange Rates**|Get the latest currency exchange rates from a service provider.|
|**Reports**|**Foreign Currency Balance**|View the balances for all customers and vendors in both foreign currencies and in local currency (LCY). The report displays two LCY balances. One is the foreign currency balance converted to LCY by using the exchange rate at the time of the transaction. The other is the foreign currency balance converted to LCY by using the exchange rate of the work date.|

## LCY and other currencies

[!INCLUDE [finance-currencies-lcy-def](includes/finance-currencies-lcy-def.md)]

## Rounding currencies

To manage currencies that don't use decimals and to avoid unnecessary decimals in foreign currency, you can use two different rounding features:

- Unit-amount rounding  

- Amount rounding  

These features can operate independently or in combination. In addition, the features can operate with invoice rounding.

As opposed to the invoice rounding features, the amount rounding and unit-amount rounding features affect only amounts in foreign currency-not the corresponding amounts in LCY. These two features don't post anything to general ledger accounts. So, no general ledger account needs to be specified on posting groups or elsewhere.

### Unit-amount rounding

The unit-amount rounding feature controls how sales prices for items and resources in foreign currencies are rounded on sales and purchase lines. You must specify the rules for each currency separately, in the **Unit-Amount Rounding Precision** field in the **Currencies** list.

The unit-amount rounding feature is used automatically every time you enter an item or resource number on a sales line. If the invoice is for a customer with a currency code, the item or resource price is converted into the customer's currency. The price is rounded according to the unit-amount rounding precision for the currency.

### Amount rounding

The amount rounding feature controls how amounts in foreign currencies are rounded on general journal lines, sales lines, and purchase lines. You must specify the rules for each currency separately, in the **Amount Rounding Precision** field in the **Currencies** list.

Amounts in foreign currencies are rounded when you fill in and post general journal lines, sales lines, and purchase lines.

## Exchange rates

You can register exchange rates for each foreign currency and specify from which dates the exchange rates are valid. For example, you can enter daily exchange rates, monthly exchange rates, or quarterly exchange rates for each foreign currency.

You can retain historical exchange rates in the **Currency Exchange Rates** page for reference purposes. When you need to update exchange rates, you can use the **Update Exchange Rates** button to get the latest exchange rates from an external service provider.

## General ledger accounts

You can't link currency codes to general ledger accounts because amounts on general ledger accounts are in LCY. If you have a bank loan in USD and place deposits in a bank account in SEK, you can keep track of these accounts by setting up bank accounts in USD and SEK. With posting groups, you can link the accounts to the relevant general ledger accounts. In the general ledger, the value of the amounts is shown in LCY.

You can enter a currency code on a general journal line and post the line to a general ledger account. The relevant exchange rate is used to convert the amount to LCY before it posts to the general ledger account.  

## Example of a receivable currency transaction

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Related information

[Update Currency Exchange Rates](finance-how-update-currencies.md)  
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
