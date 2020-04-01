---
title: How to Calculate and Post Withholding Tax Settlements
description: You can use the Calc. and Post WHT Settlement page to calculate and post the withholding tax (WHT).
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.author: sgroespe

---
# Calculate and Post Withholding Tax Settlements
You can use the **Calc. and Post WHT Settlement** page to calculate and post the withholding tax (WHT).  

You can close WHT entries that are open or not settled and transfer the corresponding amount to the WHT settlement account.  

The sum of all withheld amounts is reported as a truncated whole number to the Australian tax authorities.  

> [!NOTE]  
>  The truncated cents are accounted for in a rounding account.  

## To calculate and post withholding tax settlements  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Calc. and Post WHT Settlement**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Starting Date**|The start date of the period for which WHT has to be settled.|  
    |**Ending Date**|The end date of the period for which WHT has to be settled.|  
    |**Posting Date**|The posting date of the WHT settlement entries.|  
    |**Document No.**|The document number of the WHT settlement entries.|  
    |**Description**|The WHT settlement description.|  
    |**Settlement Account Type**|The settlement account type.|  
    |**Settlement Account**|The account number based on the account type selected in the **Settlement Account Type** field.|  
    |**Rounding G/L Account**|The account to which the truncated amount is to be posted.|  
    |**Show WHT Entries**|Select to view the withholding tax entries for the specified period.|  
    |**Post**|Select to post the WHT settlement entries.|  

3.  Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen.  

## See Also  
 [Withholding Tax](withholding-tax.md)   
 [Set Up Withholding Tax](how-to-set-up-withholding-tax.md)   
 [Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)   
 [View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)
