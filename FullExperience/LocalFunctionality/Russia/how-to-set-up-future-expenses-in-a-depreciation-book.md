---
title: "How to: Set Up Future Expenses in a Depreciation Book"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "future expenses, setting up"
ms.assetid: fa366d60-5e4d-403f-9b3c-dddc39c114f1
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Set Up Future Expenses in a Depreciation Book
To depreciate a future expense, you have to set up future period expenses in a depreciation book.  
  
### To set up future expenses in a depreciation book  
  
1.  In the **Search** box, enter **Depreciation Books**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_5611\_1 Code $\)**|Specifies the code for the depreciation book.|  
    |**\($ T\_5611\_2 Description $\)**|Specifies the description of the depreciation book.|  
    |**\($ T\_5611\_28 Default Final Rounding Amount $\)**|Specifies the final rounding amount that will be used as the default for the depreciation book.|  
    |**\($ T\_5611\_29 Default Ending Book Value $\)**|Specifies the ending book value that will be used as the default for the depreciation book.|  
    |**\($ T\_5611\_11 Disposal Calculation Method $\)**|Specifies the disposal calculation method that is associated with the depreciation book. Disposal calculation methods include **Net** or **Gross**.|  
    |**\($ T\_5611\_43 Subtract Disc. in Purch. Inv. $\)**|Specifies if discounts will be subtracted from the purchase invoice.|  
    |**\($ T\_5611\_44 Allow Correction of Disposal $\)**|Specifies if disposals can be corrected.|  
    |**\($ T\_5611\_27 Allow Changes in Depr. Fields $\)**|Specifies if changes can be made in the depreciation fields.|  
    |**\($ T\_5611\_46 VAT on Net Disposal Entries $\)**|Specifies if VAT will be calculated on net disposal entries.|  
    |**\($ T\_5611\_12401 Posting Book Type $\)**|Specifies the posting book type of the depreciation book. Book types include **Accounting**, **Tax Accounting**, and **Analytical**.|  
    |**\($ T\_5611\_12400 Currency Code $\)**|Specifies the currency code that is associated with the depreciation book.|  
    |**\($ T\_5611\_48 Allow Identical Document No. $\)**|Specifies if an identical document number can be used.|  
    |**\($ T\_5611\_12402 Allow Depreciation $\)**|Specifies if depreciations are allowed.|  
    |**\($ T\_5611\_18 Allow Indexation $\)**|Specifies if indexation is allowed.|  
    |**\($ T\_5611\_13 Allow Depr. Below Zero $\)**|Specifies if depreciation below zero is allowed.|  
    |**\($ T\_5611\_45 Allow more than 360\/365 Days $\)**|Specifies if depreciation is allowed for more than 360\/365 days.|  
    |**\($ T\_5611\_23 Use FA Ledger Check $\)**|Specifies if fixed asset ledger checks are used.|  
    |**\($ T\_5611\_24 Use Rounding in Periodic Depr. $\)**|Specifies if rounding is used in periodic depreciation calculations.|  
    |**\($ T\_5611\_19 Use Same FA\+G\/L Posting Date $\)**|Specifies if the same fixed asset general ledger posting date is used.|  
    |**\($ T\_5611\_49 Fiscal Year 365 Days $\)**|Specifies if the fiscal year equals 365 days.|  
    |**\($ T\_5611\_33 Mark Errors as Corrections $\)**|Specifies if errors are marked as corrections.|  
    |**\($ T\_5611\_12403 Control FA Acquis.Cost $\)**|Specifies if fixed asset acquisition costs are controlled.|  
  
3.  On the **Integration** FastTab, select all options.  
  
4.  On the **Navigate** tab, in the **Depr. Book** group, choose **FA Journal Setup**.  
  
5.  In the **\($ N\_5609 FA Journal Setup window $\)**, fill in the **\($ T\_5605\_5 Gen. Jnl. Template Name $\)** and **\($ T\_5605\_6 Gen. Jnl. Batch Name $\)** fields.  
  
6.  Choose the **OK** button.  
  
7.  In the **Search** box, enter **FA Setup**, and then choose the related link.  
  
8.  In the **\($ N\_5607 Fixed Asset Setup $\)** window, on the **General** FastTab, fill in the **\($ T\_5603\_12417 Future Depr. Book $\)** field and then choose the **OK** button.  
  
9. In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
10. Open the relevant account, and in the **\($ N\_17 G\/L Account Card $\)** window, on the **Posting** FastTab, fill in the **\($ T\_15\_45 Gen. Prod. Posting Group $\)** and the **\($ T\_15\_58 VAT Prod. Posting Group $\)** fields, and then choose the **OK** button.  
  
11. In the **Search** box, enter **FA Posting Groups**, and then choose the related link.  
  
12. In the **\($ N\_5613 FA Posting Groups $\)** window, enter information in the required fields.  
  
13. Choose the **OK** button.  
  
## See Also  
 [\($ N\_5607 Fixed Asset Setup $\)](../Topic/\($%20N_5607%20Fixed%20Asset%20Setup%20$\).md)   
 [Fixed Assets Accounting Setup](../../Finance/fixed-assets-accounting-setup.md)   
 [\($ N\_5600 Fixed Asset Card $\)](../Topic/\($%20N_5600%20Fixed%20Asset%20Card%20$\).md)   
 [Future Expenses \(Deferrals\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/future-expenses-deferrals-.md)   
 [How to: Create Future Expense Journals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-future-expense-journals.md)