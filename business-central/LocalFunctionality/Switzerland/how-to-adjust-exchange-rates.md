---
    title: How to Adjust Exchange Rates
    description: If you have taxable sales in a foreign currency, you must use the official rate for VAT currency conversion as set by the Federal Tax Administration.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Adjust Exchange Rates
If you have taxable sales in a foreign currency, you must use the official rate for VAT currency conversion as set by the Federal Tax Administration.  

If these rates do not match the currency rates used in the purchase or sales invoices, you will have to adjust the VAT rates with a batch job later. These adjustments can only be run using an authorized VAT rate.  

You can run this batch job as often as you like, however make sure that you always run it before creating a VAT statement.  

> [!NOTE]  
>  When using a report currency, make sure that the **VAT Exchange Rate Adjustment** field on the **General Ledger Setup** page is set to **No Adjustment**.  

For more information about VAT and foreign currencies, see the [ESTV](https://go.microsoft.com/fwlink/?LinkId=285999) website.  

## To adjust an exchange rate  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Currencies**, and then choose the related link.  
2.  Choose the **Exch. Rates** action.  
3.  On the **Currency Exchange Rates** page, enter the official VAT rate per period for each currency in the **VAT Exch. Rate Amount** and the **Relational VAT Exch. Rate Amt** fields.  
4.  Choose the **OK** button.  
5.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Adjust Exchange Rates**, and then choose the related link.  
6.  On the **Options** FastTab, fill in the fields as described in the following table.   

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|Enter a date to specify the beginning of the period for which entries will be adjusted.|  
    |**Ending Date**|Enter the last date for which entries will be adjusted. This date is typically the same as the posting date in the **Posting Date** field.|  
    |**Adjust VAT exch. rate**|Specify if you want to adjust the VAT exchange rate.|  

7.  Choose the **Print** button to start the batch job. This batch job controls whether VAT entries have to be adjusted and prepares an adjusting entry for each of these entries for the Unrealized/Realized Exchange Rate Adjustment accounts. The existing VAT entries are also corrected.  

## See Also  
 [Swiss Value Added Tax](swiss-value-added-tax.md)   
 [VAT Rates for Switzerland](vat-rates-for-switzerland.md)   
[Update Currency Exchange Rates](../../finance-how-update-currencies.md)  
[Set Up an Additional Reporting Currency](../../finance-how-setup-additional-currencies.md)
