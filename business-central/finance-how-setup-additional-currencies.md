---
title: Setting Up Additional Currencies| Microsoft Docs
description: Your general ledger is set up to use your local currency (LCY), and another currency is set up as an additional currency, with a current exchange rate assigned.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up an Additional Reporting Currency
As companies operate in increasingly more countries/regions, it becomes more important that they are able to review and report financial data in more than one currency.

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a current exchange rate assigned. By designating a second currency as a so-called additional reporting currency, [!INCLUDE[d365fin](includes/d365fin_md.md)] will automatically record amounts in both LCY and this additional reporting currency on each G/L entry and other entries, such as VAT entries.

> [!Warning]
> The Additional Reporting Currency functionality should not be used as a basis for financial statement translation. It is not a tool that can perform translation of foreign subsidiary financial statements as part of a company consolidation. The additional reporting currency can only be used to prepare reports in another currency, as if that currency was the company’s local currency.

## Displaying Reports and Amounts in the Additional Reporting Currency
Using an additional reporting currency can assist the reporting process for a company in the following cases:

- Companies in non-EU countries/regions that have a high proportion of transactions with EU country/region companies. In this case, the non-EU company may also wish to report in euro to make its financial reports more usable for EU trade partners.
- Companies that also wish to display reports in a more internationally traded currency than their own local currency.

Several financial reports are based on G/L entries. To display report data in the additional reporting currency, you simply place a check mark in the **Show Amounts in Add. Reporting Currency** field on the **Options** FastTab for the relevant G/L report.

## Adjusting Exchange Rates
Because exchange rates fluctuate constantly, additional currency equivalents in your system must be adjusted periodically. If these adjustments are not done, amounts that have been converted from foreign (or additional) currencies and posted to the general ledger in LCY may be misleading. In addition, daily entries posted before a daily exchange rate is entered into application must be updated after the daily exchange rate information is entered. The **Adjust Exchange Rates** batch job is used to adjust the exchange rates of posted customer, vendor and bank account entries. It can also update additional reporting currency amounts on G/L entries. For more information, see [Update Currency Exchange Rates](finance-how-update-currencies.md).

## Setting Up an Additional Reporting Currency
To set up an additional reporting currency, you must follow these steps:

-   Specify general ledger accounts for posting exchange rate adjustments.  
-   Specify the exchange rate adjustment method for all general ledger accounts.  
-   Specify the exchange rate adjustment method for VAT entries.  
-   Activate the additional reporting currency.  

### To specify general ledger accounts for posting exchange rate adjustments  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Currencies**, and then choose the related link.  
2. On the **Currencies** page, fill in the following fields for the additional reporting currency.  

|Field|Description|  
|---------------------------------|---------------------------------------|  
|**Realized GL Gains Account**|The general ledger account to which exchange rate gains for currency adjustments between LCY and the additional reporting currency will be posted.|  
|**Realized GL Losses Account**|The general ledger account to which exchange rate losses for currency adjustments between LCY and the additional reporting currency will be posted.|  
|**Residual Gains Account**|The general ledger account to which residual amounts that are gains are posted if you post in the general ledger application area in both LCY and an additional reporting currency.|  
|**Residual Losses Account**|The general ledger account to which residual amounts that are losses are posted if you post in the general ledger application area in both LCY and an additional reporting currency.|

> [!NOTE]  
>  Residual amounts can occur when [!INCLUDE[d365fin](includes/d365fin_md.md)] rounds debit and credit amounts that have been converted from LCY to an additional reporting currency.  

For each general ledger account, you must specify how general ledger amounts for that account will be adjusted for exchange rate fluctuations between LCY and the additional reporting currency.  

### To specify the exchange rate adjustment method for all general ledger accounts  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.  
2. On the **Chart of Accounts** page, select the relevant account, and then choose the **Edit** action.  
3. On the **GL Account Card** page, select the relevant method in the **Exchange Rate Adjustment** field.  

    If you post in an additional reporting currency, specify in the **Exchange Rate Adjustment** field how this general ledger account will be adjusted for exchange-rate fluctuations between LCY and the additional reporting currency. The following table shows the options to choose from.  

    |Field|Decription|  
    |----------------------------------|---------------------------------------|  
    |**No Adjustment**|No exchange rate adjustment is made to the general ledger account. This is the default option.<br /><br /> **NOTE:** This option should be selected if the exchange rate between the LCY and additional reporting currency is always fixed.|  
    |**Adjust Amount**|The LCY amount is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  
    |**Adjust Additional-Currency Amount**|The additional reporting currency is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  

    Exchange rate gains and losses are posted when you run the **Adjust Exchange Rates** batch job. In that batch job, the adjustment exchange rate is identified on the **Currency Exchange Rates** page, and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the general ledger entry are compared to determine whether there is an exchange rate gain or loss. The batch job uses the option that you select in the **Exchange Rate Adjustment** field to determine how to calculate and post exchange rate gains or losses for general ledger accounts.  

4.  Close the **G/L Account Card** page.  

### To specify exchange rate adjustment method for VAT entries  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, select the relevant method in the **VAT Exchange Rate Adjustment** field.  
3. If you post in an additional reporting currency, you can specify in the **VAT Exchange Rate Adjustment** field how the accounts set up for VAT posting on the **VAT Posting Setup** page will be adjusted for exchange-rate fluctuations between LCY and the additional reporting currency.  

    When you run the **Adjust Exchange Rates** batch job, the adjustment exchange rate is identified on the **Currency Exchange Rate** page and then the amounts in the **Amount** and **Additional-Currency Amount** fields on the VAT entry are compared to determine if there is an exchange rate gain or loss. The batch job uses the option that you select in this field to determine how to post exchange rate gains or losses for VAT accounts.  

    You have the same options as with general ledger entries but in this case the entries adjusted will be the VAT entries. The following table shows the options to choose from.

    |Field|Description|  
    |----------------------------------|---------------------------------------|  
    |**No Adjustment**|No exchange rate adjustment is made to the general ledger account. This is the default option.|  
    |**Adjust Amount**|The LCY amount is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  
    |**Adjust Additional-Currency Amount**|The additional reporting currency is adjusted for any exchange rate gains or losses. Exchange rate gains or losses are posted to the general ledger account in the **Additional-Currency Amount** field and to the accounts you specified for gains or losses in the **Realized G/L Gains Account** and **Realized G/L Losses Account** fields on the **Currencies** page.|  

### To activate the additional reporting currency  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, choose the **Additional Reporting Currency** field to select the additional currency that you want to report in.  
3. When you leave the field, [!INCLUDE[d365fin](includes/d365fin_md.md)] displays a confirmation message describing the effects of activating the additional reporting currency.  
4. Choose the **Yes** button to confirm that you want to activate the currency.  
5. The **Adjust Add. Reporting Currency** batch job opens.

    This batch job converts LCY amounts on existing entries to the additional reporting currency. The batch job uses a default exchange rate copied from the exchange rate that is valid on the work date on the **Currency Exchange Rates** page. Residual amounts that occur on conversion of LCY to additional reporting currency are posted to the residual gains and losses accounts specified on the **Currencies** page. The posting date and document number for these entries are the same as for the original general ledger entry. After all these residual entries are posted, the batch job posts a rounding entry on the closing date of each closed year to the retained earnings account. This is to make sure that the ending balance of the income accounts for each closed years is 0 in both LCY and the additional reporting currency.
6. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]      
7. Choose the **OK** button to run the batch job.  

After running the batch job, amounts on the following existing entries will be in both LCY and in the additional reporting currency:  

- General ledger entries  
- Item application entries  
- VAT entries  
- Job ledger entries  
- Value entries  
- Production order lines  
- Production order ledger entries  

In addition, all future entries of the same type will have amounts recorded in both LCY and the additional reporting currency.  

> [!NOTE]  
>  The **Add. Reporting Currency** field will only be activated after you choose the **OK** button in the **Adjust Add. Reporting Currency** batch job.  

## See Related Training at [Microsoft Learn](/learn/paths/use-multiple-currencies-dynamics-365-business-central/)

## See Also
[Update Currency Exchange Rates](finance-how-update-currencies.md)  
[Closing Years and Periods](year-close-years-periods.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
