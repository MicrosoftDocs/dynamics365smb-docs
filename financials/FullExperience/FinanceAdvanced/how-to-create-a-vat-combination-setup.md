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
# How to: Create a VAT Combination Setup
This topic describes how to create a VAT combination setup.  
  
#### To create a VAT combination setup  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  In the **VAT Posting Setup** window, insert a new line, and then enter values in the **VAT Bus. Posting Group**, **VAT Prod. Posting Group**, and **VAT Identifier** fields.  
  
3.  On the **Actions** tab, in the **General** group, choose **Copy**.  
  
4.  In the **Copy - VAT Posting Setup** batch job, specify the **VAT Bus. Posting Group** and **VAT Prod. Posting Group** values of the line that you want to copy from.  
  
5.  In the **Copy** field, select one of the following values.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_optionsheading](../../includes/bp_tabledescription_md.md)]-->|  
    |-------------------------------------|---------------------------------------|  
    |**All Fields**|Copies all fields|  
    |**Selected Fields**|Selects one or more of the following fields:<br /><br /> -   **VAT% etc.**<br />-   **Sales Accounts**<br />-   **Purchase Accounts**|  
  
6.  Choose the **OK** button to copy the information.  
  
 For more information, see Copy - VAT Posting Setup.  
  
## See Also  
 [About Setting Up VAT](../FullExperience/about-setting-up-vat.md)   
 [How to: Enter Basic Information on Reverse Charge VAT for Purchases](../FullExperience/how-to-enter-basic-information-on-reverse-charge-vat-for-purchases.md)   
 [How to: Record VAT](../FullExperience/how-to-record-vat.md)   
 [How to: Revert VAT on Payment Discounts](../FullExperience/how-to-revert-vat-on-payment-discounts.md)   
 [How to: Set Up Codes for Import VAT](../FullExperience/how-to-set-up-codes-for-import-vat.md)   
 [How to: Set Up General Ledger Accounts for Invoice Rounding Differences](../FullExperience/how-to-set-up-general-ledger-accounts-for-invoice-rounding-differences.md)   
 [How to: Use Accounts for Unrealized VAT](../FullExperience/how-to-use-accounts-for-unrealized-vat.md)   
 VAT Posting Setup   
 Copy - VAT Posting Setup