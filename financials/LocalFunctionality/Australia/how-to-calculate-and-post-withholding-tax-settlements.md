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
# How to: Calculate and Post Withholding Tax Settlements
You can use the **Calc. and Post WHT Settlement** window to calculate and post the withholding tax \(WHT\).  
  
 You can close WHT entries that are open or not settled and transfer the corresponding amount to the WHT settlement account.  
  
 The sum of all withheld amounts is reported as a truncated whole number to the Australian tax authorities.  
  
> [!NOTE]  
>  The truncated cents are accounted for in a rounding account.  
  
### To calculate and post withholding tax settlements  
  
1.  In the **Search** box, enter **Calc. and Post WHT Settlement**, and then choose the related link.  
  
2.  On the **ADD INCLUDE<!--[!INCLUDE[bp_optionsheading](../../includes/bp_optionsheading_md.md)]-->** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
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
 [Withholding Tax](withholding-tax.md)   
 [How to: Set Up Withholding Tax](how-to-set-up-withholding-tax.md)   
 [How to: Set Up Revenue Types for Withholding Tax](how-to-set-up-revenue-types-for-withholding-tax.md)   
 [How to: View Withholding Tax Entries](how-to-view-withholding-tax-entries.md)