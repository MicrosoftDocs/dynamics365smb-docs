---
title: Update currency exchange rates
description: Learn how to use Business Central to adjust exchange rates for amounts in different currencies.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: multiple currencies, adjust exchange rates, FX rates
ms.search.form: 5, 118
ms.date: 06/16/2025
ms.custom: bap-template

---

# Update currency exchange rates

If you trade in different currencies, you need to keep track of the changes in currency exchange rates. [!INCLUDE [prod_short](includes/prod_short.md)] helps you manage and update the exchange rates manually or automatically and set up a currency exchange rate service.

## Currencies

> [!TIP]  
> In [!INCLUDE[prod_short](includes/prod_short.md)], you can find real-time information about foreign exchange (FX) rates or historical rates under the term currency. To learn more, go to [Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md).

[!INCLUDE [finance-currencies-def](includes/finance-currencies-def.md)]

You can specify the currency codes in the **Currencies** list, including extra information and settings that are necessary for each currency code. To learn more, go to [Currencies](finance-set-up-currencies.md#curr)

### Example of a receivable currency transaction

[!INCLUDE [finance-currencies-example](includes/finance-currencies-example.md)]

## Exchange rates

The exchange rates are the tool to calculate the local currency value (LCY) of each currency transaction. The **Currency Exchange Rates** page includes the following fields:

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Starting Date**|The date when the currency rate was effective.|  
|**Currency Code**|The currency code related to this exchange rate.|  
|**Relational Currency Code**|If this currency is part of a triangular currency calculation, then you can set up the related currency code here.|  
|**Exchange Rate Amount**|The exchange rate amount is the rate for the currency code selected on the line. Normally 1 or 100.|  
|**Relational Exch. Rate Amount**|The relational exchange rate amount relates to the rate to use for the relational currency code.|  
|**Adjustment Exch. Rate Amount**|The rate for the currency code selected on the line for the use of the **Adjust Exchange Rates** batch job.|  
|**Relational Adjmt Exch. Rate Amt**|The rate for the currency code selected on the line for the use of the **Adjust Exchange Rates** batch job.|  
|**Fix Exchange Rate Amount**|Specifies if the currency's exchange rate can be changed on invoices and journal lines.|  

In general, the values of the **Exchange Rate Amount** and **Relational Exchange Rate Amount** fields are used as the default currency rate on all new receivables and payables documents that are created going forward. The currency rate is assigned to the document according to the current working date.  

> [!Note]
> The actual currency rate is calculated using this formula:
>
> `Currency Amount = Amount / Exchange Rate Amount * Relational Exch. Rate Amount`

The adjustment exchange rate amount, or the relational adjustment exchange rate amount, updates all open bank, receivables, or payables transactions.  

> [!Note]
> The actual currency rate is calculated using this formula:
>
> `Currency Amount = Amount / Adjustment Exch. Rate Amount * Relational Adjmt Exch. Rate Amt`

## Adjust exchange rates

Because exchange rates fluctuate constantly, you need to adjust other currency equivalents periodically. If you don't, amounts you converted from foreign (or other) currencies and posted to the general ledger in local currency can be incorrect. Also, you need to update daily entries posted before you enter a daily exchange rate.

You can use the **Adjust Exchange Rates** batch job to manually adjust the exchange rates for posted customer, vendor, and bank account entries. The batch job can also update other reporting currency amounts on G/L entries.  

> [!TIP]
> You can use a service to update exchange rates automatically. To learn more, go to [To set up a currency exchange rate service](finance-how-update-currencies.md#set-up-a-currency-exchange-rate-service). However, this doesn't adjust exchange rates on already posted transactions. To update exchange rates on posted entries, use the **Exchange Rates Adjustment** batch job.

You can also specify how the adjustment handles dimensions for unrealized gains and losses postings by choosing one of the following options in the **Dimension Posting** field:  

* **Source Entry Dimensions**: Transfer dimension values for G/L entries for unrealized gains and losses from the entry you're adjusting.  
* **No Dimensions**: Don't transfer dimension values for unrealized gains and losses to G/L entries. [!INCLUDE [prod_short](includes/prod_short.md)] still uses default dimension settings, for example, **Code Mandatory**, **Same Code**, or **No Code**. If the source transaction entries have dimension values, the adjustment creates entries without dimension values.  
* **G/L Account Dimensions**: Transfer dimension values from the unrealized gains and losses G/L account's dimension settings source entry to G/L entries.

> [!NOTE]
> This capability isn't available in the Swiss version right now, but it's coming soon. We're working on it.

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] doesn't consider dimensions for individual entries when you adjust exchange rates for additional reporting currencies. Dimensions aren't copied to the G/L entries if you set up the **Exchange Rate Adjustment** batch job with:
>
> * The **Adjust G/L Accounts for Add.-Reporting Currency** toggle turned on.
> * **Source Entry Dimensions** selected in the **Dimension Posting** field.

## Preview the effect of an adjustment

You can preview the effect that an exchange rate adjustment has on posting before you actually post by choosing the **Preview Posting** action on the **Exch. Rates Adjustment** report (Report 596) request page. On the request page, you can specify what to include in the preview:

* Get a detailed posting to the general ledger by entry.
* Get a summarized posting by currency. Just pick the **Adjust per entry** field on the **Exch. Rates Adjustment** report.

### Effect on customers and vendors

For customer and vendor accounts, the batch job uses the exchange rate that was valid on the posting date specified for the batch job to adjust the currency. The batch job calculates the differences for the individual currency balances and posts the amounts to the general ledger account that is specified in the **Unrealized Gains Acc.** field or the **Unrealized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the receivables/payables account in the general ledger.

The batch job processes all open customer ledger entries and vendor ledger entries. If there's an exchange rate difference for an entry, the batch job creates a new detailed customer or vendor ledger entry. The new entry reflects the adjusted amount on the customer or vendor ledger entry.

#### Dimensions on customer and vendor ledger entries

[!INCLUDE [prod_short](includes/prod_short.md)] assigns the dimensions from the customer or vendor ledger entries to the adjustment entries, and posts adjustments for each combination of dimension values.

### Effect on bank accounts

For bank accounts, the batch job adjusts the currency by using the exchange rate that is valid on the posting date specified in the batch job. The batch job calculates the differences for each bank account that has a currency code and posts the amounts to the general ledger account that is specified in the **Realized Gains Acc.** field or the **Realized Losses Acc.** field on the **Currencies** page. Balancing entries are automatically posted to the general ledger bank accounts that are specified in the bank account posting groups. The batch job calculates one entry per currency per posting group.

#### Dimensions on bank account entries

The bank account's default dimensions are assigned to the adjustment entries for the bank account's general ledger account and the gain/loss account.

### Effect on G/L accounts

If you post in another reporting currency, the batch job can create new general ledger entries for currency adjustments between the local currency and the other reporting currency. The batch job calculates the differences for each general ledger entry. It adjusts the general ledger entry depending on the contents of the **Exchange Rate Adjustment** field for each general ledger account.

#### Dimensions on G/L account entries

Adjustment entries are assigned the default dimensions from the accounts they posted to.

> [!Important]
> Before you can use the batch job, enter the adjustment exchange rates that are used to adjust the foreign currency balances. You do so on the **Currency Exchange Rates** page.<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=e871f958-fe42-4cf3-bb8a-e97f4c7658de]

## Set up a currency exchange rate service

You can use an external service to keep your currency exchange rates up to date.

> [!NOTE]
> Most exchange rate services provide data that is compatible with the import process in [!INCLUDE[prod_short](includes/prod_short.md)]. However, sometimes the data is formatted differently and you need to customize your import process. You can use the data exchange framework to do that by adding your own codeunit. You might need some help from a developer to do that. To learn more, go to [Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currency Exchange Rate Services**, and then select the related link.
2. Select the **New** action.
3. On the **Currency Exchange Rate Service** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Map the fields from the XML file to the currency exchange rates table in the source field.
5. Apply any necessary transformation rules.
6. Turn on the **Enabled** toggle to enable the service.

> [!NOTE]
> The following video shows how you can connect to a currency exchange rate service, using the European Central Bank as an example. In the segment that describes how to set up field mappings, the setting in the **Source** column for the **Parent Node for Currency Code**  only returns the first currency found. The setting should be `/gesmes:Envelope/Code/Code/Code`.

<br><br>  
  
> [!Video https://learn-video.azurefd.net/vod/player?id=76914b80-c36a-4d74-95fa-0cdf5c5c0bfa]

## Update currency exchange rates through a service

Follow the steps given to update the currency exchange rates through a service:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then select the related link.
2. Select the **Update Exchange Rates** action.

## Correct mistakes

Every now and then, you might need to correct a mistake in a payment transaction for adjustments to foreign currency gains and losses. You can use the **Reverse transaction** action on the **Bank Account Ledger Entries**, **Customer Ledger Entries**, and **Vendor Ledger Entries** pages to unapply and reverse the payment transaction.

> [!NOTE]
> When you unapply and reverse a payment for an entry that had exchange rate adjustments, the reversal posts reversal entries for the adjustments. You might have to run the currency exchange rate adjustment again to get the correct current balance.

## Related information

[Currencies in Business Central](finance-currencies.md)  
[Set Up Currencies](finance-set-up-currencies.md)  
[Set Up an Additional Reporting Currency](finance-how-setup-additional-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
