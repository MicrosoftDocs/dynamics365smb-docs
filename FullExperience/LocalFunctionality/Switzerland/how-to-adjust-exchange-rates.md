---
title: "How to: Adjust Exchange Rates"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "exchange rates"
  - "VAT, exchange rates"
ms.assetid: b9737eaf-a6d3-475a-bf77-f65391555842
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# How to: Adjust Exchange Rates
If you have taxable sales in a foreign currency, you must use the official rate for VAT currency conversion as set by the Federal Tax Administration.  
  
 If these rates do not match the currency rates used in the purchase or sales invoices, you will have to adjust the VAT rates with a batch job later. These adjustments can only be run using an authorized VAT rate.  
  
 You can run this batch job as often as you like, however make sure that you always run it before creating a VAT statement.  
  
> [!NOTE]  
>  When using a report currency, make sure that the **\($ T\_98\_72 VAT Exchange Rate Adjustment $\)** field in the **\($ N\_118 General Ledger Setup $\)** window is set to **No Adjustment**.  
  
 For more information about VAT and foreign currencies, see the [ESTV](http://go.microsoft.com/fwlink/?LinkId=285999) website.  
  
### To adjust an exchange rate  
  
1.  In the **Search** box, enter **Currencies**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Exchange Rate** group, choose **Exch. Rates**.  
  
3.  In the **\($ N\_483 Currency Exchange Rates $\)** window, enter the official VAT rate per period for each currency in the **\($ T\_330\_11500 VAT Exch. Rate Amount $\)** and the **\($ T\_330\_11501 Relational VAT Exch. Rate Amt $\)** fields.  
  
4.  Choose the **OK** button.  
  
5.  In the **Search** box, enter **Adjust Exchange Rates**, and then choose the related link.  
  
6.  On the **Options** FastTab, fill in the fields as described in the following table. [!INCLUDE[bp_fieldhelp]()]  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_595\_F\_1\_1 Starting Date $\)**|Enter a date to specify the beginning of the period for which entries will be adjusted.|  
    |**\($ B\_595\_F\_1\_2 Ending Date $\)**|Enter the last date for which entries will be adjusted. This date is typically the same as the posting date in the **\($ B\_595\_F\_1\_4 Posting Date $\)** field.|  
    |**\($ B\_595\_F\_1\_1150001 Adjust VAT exch. rate $\)**|Specify if you want to adjust the VAT exchange rate.|  
  
7.  Choose the **Print** button to start the batch job. This batch job controls whether VAT entries have to be adjusted and prepares an adjusting entry for each of these entries for the Unrealized\/Realized Exchange Rate Adjustment accounts. The existing VAT entries are also corrected.  
  
## See Also  
 [Swiss Value Added Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-value-added-tax.md)   
 [VAT Rates for Switzerland](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/vat-rates-for-switzerland.md)   
 [\($ T\_325 VAT Posting Setup $\)](assetId:///5510a4f9-3ad3-461f-a53a-f3578c78a87f)   
 [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)   
 [\($ T\_254 VAT Entry $\)](assetId:///e4113f5c-adc8-4bfd-8c4b-e7b5f11f4d32)   
 [\($ B\_595 Adjust Exchange Rates $\)\-duplicate](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/-$-b_595-adjust-exchange-rates-$-duplicate.md)   
 [\($ N\_483 Currency Exchange Rates $\)](assetId:///ecc75eeb-2b22-4316-8204-fd0940c11c68)