---
title: Set up additional currencies
description: Your general ledger is set up to use your local currency (LCY), and another currency is set up as an additional currency, with a current exchange rate assigned.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: multiple currencies, foreign exchange rates
ms.search.form: 5, 16, 118, 483, 495
ms.date: 06/13/2024
ms.service: dynamics-365-business-central

---
# Set up an additional reporting currency

As companies operate in increasingly more countries/regions, it becomes more important that they're able to review and report financial data in more than one currency.

> [!NOTE]  
> In [!INCLUDE[prod_short](includes/prod_short.md)], if you're looking for real time information about foreign exchange (FX) rates or historical rates, it's referred to as currency. In addition to this article, see also [Update Currency Exchange Rates](finance-how-update-currencies.md).

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a current exchange rate assigned. If you designate a second currency as an additional reporting currency (ACY), [!INCLUDE[prod_short](includes/prod_short.md)] automatically records amounts in both LCY and ACY on each G/L entry and other entries, such as VAT entries.

> [!Warning]
> You shouldn't use the ACY feature as a basis for financial statement translation unless you understand its limitations. It can't translate foreign subsidiary financial statements as part of a company consolidation. The ACY can only be used to prepare reports in another currency, as if that currency was the company's LCY.
>
> For example, you have a large amount of accounts receivable in British pounds (GBP), and you have set up your ACY to be GBP. In this scenario, amounts in the accounts receivable that use GBP aren't adjusted for currency exchange gains/losses in the ACY, only amounts in the accounts receivable that are in other currencies. That means that if you use ACY to report your financial statements, it might result in understated or overstated outstanding balances of accounts receivable.

## Displaying reports and amounts in ACY

Using an ACY can assist the reporting process for a company in the following cases:

- Companies in non-EU countries/regions that have a high proportion of transactions with EU country/region companies. In this case, the non-EU company might also want to report in euro to make its financial reports more usable for EU trade partners.
- Companies that also wish to display reports in a more internationally traded currency than their own local currency.

Several financial reports are based on G/L entries. To display report data in the ACY, select the **Show Amounts in Add. Reporting Currency** checkbox on the **Options** FastTab for the relevant G/L report.

## Adjusting exchange rates

Because exchange rates fluctuate constantly, ACY equivalents in your system must be adjusted periodically. If these adjustments aren't done, amounts that converted from foreign (or additional) currencies and posted to the general ledger in LCY can be misleading. In addition, daily entries posted before a daily exchange rate is entered into application must be updated after the daily exchange rate information is entered. The **Adjust Exchange Rates** batch job is used to adjust the exchange rates of posted customer, vendor, and bank account entries. It can also update ACY amounts on G/L entries. For more information, see [Update Currency Exchange Rates](finance-how-update-currencies.md).

## Setting up an ACY

To set up an ACY, follow these steps:

- Specify general ledger accounts for posting exchange rate adjustments.  
- Specify the exchange rate adjustment method for all general ledger accounts.  
- Specify the exchange rate adjustment method for VAT entries.  
- Activate the ACY.  

### To specify general ledger accounts for posting exchange rate adjustments  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Currencies**, and then choose the related link.  
2. On the **Currencies** page, fill in the following fields for the ACY.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Realized GL Gains Account**|The general ledger account to which exchange rate gains for currency adjustments between LCY and the ACY are posted.|  
|**Realized GL Losses Account**|The general ledger account to which exchange rate losses for currency adjustments between LCY and the ACY are posted.|  
|**Residual Gains Account**|The general ledger account to which residual amounts that are gains are posted if you post in the general ledger application area in both LCY and an ACY.|  
|**Residual Losses Account**|The general ledger account to which residual amounts that are losses are posted if you post in the general ledger application area in both LCY and an ACY.|

> [!NOTE]  
> Residual amounts can occur when [!INCLUDE[prod_short](includes/prod_short.md)] rounds debit and credit amounts that have been converted from LCY to an ACY.  

For each general ledger account, you must specify how general ledger amounts for that account are adjusted for exchange rate fluctuations between LCY and the ACY.  

### To specify the exchange rate adjustment method for all general ledger accounts

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Chart of Accounts**, and then choose the related link.  
2. On the **Chart of Accounts** page, select the relevant account, and then choose the **Edit** action.  
3. On the **GL Account Card** page, select the relevant method in the **Exchange Rate Adjustment** field.  

    If you post in an ACY, in the **Exchange Rate Adjustment** field, specify how this general ledger account is adjusted for exchange-rate fluctuations between LCY and the ACY. The following table describes the options.  

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**No Adjustment**|No exchange rate adjustment is made to the general ledger account. This setting is the default option.<br /><br /> **NOTE:** Select this option if the exchange rate between the LCY and ACY is always fixed.|  
    |**Adjust Amount**|The LCY amount is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  
    |**Adjust Additional-Currency Amount**|The ACY is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  

    Exchange rate gains and losses are posted when you run the **Adjust Exchange Rates** batch job. In that batch job, the adjustment exchange rate is identified on the **Currency Exchange Rates** page, and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the general ledger entry are compared to determine whether there's an exchange rate gain or loss. The batch job uses the option that you select in the **Exchange Rate Adjustment** field to determine how to calculate and post exchange rate gains or losses for general ledger accounts.  

4.  Close the **G/L Account Card** page.  

### To specify exchange rate adjustment method for VAT entries

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, select the relevant method in the **VAT Exchange Rate Adjustment** field.  
3. If you post in an ACY, in the **VAT Exchange Rate Adjustment** field you can specify how the accounts set up for VAT posting on the **VAT Posting Setup** page are adjusted for exchange-rate fluctuations between LCY and the ACY.  

    When you run the **Adjust Exchange Rates** batch job, the adjustment exchange rate is identified on the **Currency Exchange Rate** page and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the VAT entry are compared to determine if there's an exchange rate gain or loss. The batch job uses the option that you select in this field to determine how to post exchange rate gains or losses for VAT accounts.  

    You have the same options as with general ledger entries but in this case the entries adjusted are the VAT entries. The following table describes the options.

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**No Adjustment**|No exchange rate adjustment is made to the general ledger account. This setting is the default option.|  
    |**Adjust Amount**|The LCY amount is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  
    |**Adjust Additional-Currency Amount**|The ACY is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  

### To activate the ACY  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, in the **Additional Reporting Currency** field, choose the additional currency that you want to report in.  
3. When you leave the field, [!INCLUDE[prod_short](includes/prod_short.md)] displays a confirmation message describing the effects of activating the ACY.  
4. Choose the **Yes** button to confirm that you want to activate the currency.  
5. The **Adjust Add. Reporting Currency** batch job opens.

    This batch job converts LCY amounts on existing entries to the ACY. The batch job uses a default exchange rate copied from the exchange rate that is valid on the work date on the **Currency Exchange Rates** page. Residual amounts that occur on conversion of LCY to ACY are posted to the residual gains and losses accounts specified on the **Currencies** page. The posting date and document number for these entries are the same as for the original general ledger entry. After you post all residual entries, the batch job posts a rounding entry on the closing date of each closed year to the retained earnings account. This posting makes sure that the ending balance of the income accounts for each closed year is 0 in both LCY and the ACY.
6. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]      
7. Choose the **OK** button to run the batch job.  

After you run the batch job, amounts on the following existing entries are in both the LCY and ACY:  

- General ledger entries  
- Item application entries  
- VAT entries  
- Project ledger entries  
- Value entries  
- Production order lines  
- Production order ledger entries  

In addition, all future entries of the same type have amounts recorded in both LCY and the ACY.  

> [!NOTE]  
> The **Add. Reporting Currency** field will only be activated after you choose the **OK** button in the **Adjust Add. Reporting Currency** batch job.  

## Related information

[Update Currency Exchange Rates](finance-how-update-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
