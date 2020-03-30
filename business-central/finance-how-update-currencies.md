---
title: Update Currency Exchange Rates| Microsoft Docs
description: Track amounts in different currencies using currency codes, and let Business Central help you adjust exchange rates of posted entries with an external service.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: multiple currencies, adjust exchange rates
ms.date: 04/01/2020
ms.author: sgroespe

---
# Update Currency Exchange Rates
As companies operate in increasingly more countries/regions, it becomes more important that they be able to trade and report financials in more than one currency. You must set up a code for each currency you use if you buy or sell in currencies other than your local currency, have receivables or payables in other currencies, or record G/L transactions in different currencies.

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a current exchange rate assigned. By designating a second currency as a so-called additional reporting currency, [!INCLUDE[d365fin](includes/d365fin_md.md)] will automatically record amounts in both LCY and this additional reporting currency on each G/L entry and other entries, such as VAT entries. For more information, see [Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md).

## Adjusting Exchange Rates
Because exchange rates fluctuate constantly, additional currency equivalents in your system must be adjusted periodically. If these adjustments are not done, amounts that have been converted from foreign (or additional) currencies and posted to the general ledger in LCY may be misleading. In addition, daily entries posted before a daily exchange rate is entered into application must be updated after the daily exchange rate information is entered.

The **Adjust Exchange Rates** batch job is used to manually adjust the exchange rates of posted customer, vendor and bank account entries. It can also update additional reporting currency amounts on G/L entries. You can also have the exchange rates adjusted automatically by using a service. For more information, see [To set up a currency exchange rate service](finance-how-update-currencies.md#to-set-up-a-currency-exchange-rate-service).

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

## To update currency exchange rates through a service
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.
2. Choose the **Update Exchange Rates** action.

The value in the **Exchange Rate** field on the **Currencies** page is updated with the latest currency exchange rate.

## See Related Training at [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## See Also
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
