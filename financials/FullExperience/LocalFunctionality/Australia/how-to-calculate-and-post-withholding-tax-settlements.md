---
title: "How to: Calculate and Post Withholding Tax Settlements"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "withholding tax, settlements"
  - "tax, withholding tax settlements"
ms.assetid: daed71cb-4cb6-496d-995b-0fc84c1ee5ad
caps.latest.revision: 17
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-au"
---
# How to: Calculate and Post Withholding Tax Settlements
You can use the **Calc. and Post WHT Settlement** window to calculate and post the withholding tax \(WHT\).  
  
 You can close WHT entries that are open or not settled and transfer the corresponding amount to the WHT settlement account.  
  
 The sum of all withheld amounts is reported as a truncated whole number to the Australian tax authorities.  
  
> [!NOTE]  
>  The truncated cents are accounted for in a rounding account.  
  
### To calculate and post withholding tax settlements  
  
1.  In the **Search** box, enter **Calc. and Post WHT Settlement**, and then choose the related link.  
  
2.  On the **[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_28041\_N\_2\_13 Starting Date $\)**|The start date of the period for which WHT has to be settled.|  
    |**\($ R\_28041\_N\_2\_11 Ending Date $\)**|The end date of the period for which WHT has to be settled.|  
    |**\($ R\_28041\_N\_2\_9 Posting Date $\)**|The posting date of the WHT settlement entries.|  
    |**\($ R\_28041\_N\_2\_4 Document No. $\)**|The document number of the WHT settlement entries.|  
    |**\($ R\_28041\_N\_2\_1500006 Description $\)**|The WHT settlement description.|  
    |**\($ R\_28041\_N\_2\_1500002 Settlement Account Type $\)**|The settlement account type.|  
    |**\($ R\_28041\_N\_2\_3 Settlement Account $\)**|The account number based on the account type selected in the **\($ R\_28041\_N\_2\_1500002 Settlement Account Type $\)** field.|  
    |**\($ R\_28041\_N\_2\_1500000 Rounding G\/L Account $\)**|The account to which the truncated amount is to be posted.|  
    |**\($ R\_28041\_N\_2\_2 Show WHT Entries $\)**|Select to view the withholding tax entries for the specified period.|  
    |**\($ R\_28041\_N\_2\_1 Post $\)**|Select to post the WHT settlement entries.|  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Withholding Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/withholding-tax.md)   
 [How to: Set Up Withholding Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-set-up-withholding-tax.md)   
 [How to: Set Up Revenue Types for Withholding Tax](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-set-up-revenue-types-for-withholding-tax.md)   
 [How to: View Withholding Tax Entries](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-view-withholding-tax-entries.md)