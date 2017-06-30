---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Adjust Exchange Rates
If you have taxable sales in a foreign currency, you must use the official rate for VAT currency conversion as set by the Federal Tax Administration.  
  
 If these rates do not match the currency rates used in the purchase or sales invoices, you will have to adjust the VAT rates with a batch job later. These adjustments can only be run using an authorized VAT rate.  
  
 You can run this batch job as often as you like, however make sure that you always run it before creating a VAT statement.  
  
> [!NOTE]  
>  When using a report currency, make sure that the **VAT Exchange Rate Adjustment** field in the **General Ledger Setup** window is set to **No Adjustment**.  
  
 For more information about VAT and foreign currencies, see the [ESTV](http://go.microsoft.com/fwlink/?LinkId=285999) website.  
  
### To adjust an exchange rate  
  
1.  In the **Search** box, enter **Currencies**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Exchange Rate** group, choose **Exch. Rates**.  
  
3.  In the **Currency Exchange Rates** window, enter the official VAT rate per period for each currency in the **VAT Exch. Rate Amount** and the **Relational VAT Exch. Rate Amt** fields.  
  
4.  Choose the **OK** button.  
  
5.  In the **Search** box, enter **Adjust Exchange Rates**, and then choose the related link.  
  
6.  On the **Options** FastTab, fill in the fields as described in the following table. ADD INCLUDE<!--[!INCLUDE[bp_fieldhelp]()]-->  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_595\_F\_1\_1 Starting Date $\)**|Enter a date to specify the beginning of the period for which entries will be adjusted.|  
    |**\($ B\_595\_F\_1\_2 Ending Date $\)**|Enter the last date for which entries will be adjusted. This date is typically the same as the posting date in the **\($ B\_595\_F\_1\_4 Posting Date $\)** field.|  
    |**\($ B\_595\_F\_1\_1150001 Adjust VAT exch. rate $\)**|Specify if you want to adjust the VAT exchange rate.|  
  
7.  Choose the **Print** button to start the batch job. This batch job controls whether VAT entries have to be adjusted and prepares an adjusting entry for each of these entries for the Unrealized\/Realized Exchange Rate Adjustment accounts. The existing VAT entries are also corrected.  
  
## See Also  
 [Swiss Value Added Tax](../swiss-value-added-tax.md)   
 [VAT Rates for Switzerland](../vat-rates-for-switzerland.md)   
 VAT Posting Setup   
 General Ledger Setup   
 VAT Entry   
 [Adjust Exchange Rates-duplicate](../-$-b_595-adjust-exchange-rates-$-duplicate.md)   
 Currency Exchange Rates