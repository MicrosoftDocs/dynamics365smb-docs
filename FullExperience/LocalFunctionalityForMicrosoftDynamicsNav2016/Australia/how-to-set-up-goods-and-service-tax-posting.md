---
title: "How to: Set Up Goods and Service Tax Posting"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting, goods and service tax"
  - "goods and services tax (GST), setting up"
ms.assetid: 22ed8798-cefd-437d-94ae-76e32726c6e1
caps.latest.revision: 17
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-au"
---
# How to: Set Up Goods and Service Tax Posting
Goods and services tax \(GST\) is the tax that is applied on most goods and services. The GST that is paid and received during a period is reported in the Business Activity Statement \(BAS\) that has to be submitted to the Australian Taxation Office \(ATO\).  
  
 To set up posting details for GST, you must define the posting groups, rate of GST, and the accounts to which GST is to be posted. You can set up this information for a particular combination business posting groups and product posting groups.  
  
 You must set up GST posting before you generate the BAS report.  
  
### To set up goods and sales tax posting  
  
1.  In the **Search** box, enter **\($ N\_472 VAT Posting Setup $\)**, and then choose the appropriate link.  
  
2.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_325\_1 VAT Bus. Posting Group $\)**|Specifies the VAT business posting group code.|  
    |**\($ T\_325\_2 VAT Prod. Posting Group $\)**|Specifies the VAT product posting group code.|  
    |**\($ T\_325\_13 VAT Identifier $\)**|Specifies the code that is used to group similar VAT setups with similar attributes.<br /><br /> For example, you can group a number of VAT posting setups that have a common VAT percentage.|  
    |**\($ T\_325\_4 VAT % $\)**|Specifies the VAT rate.|  
    |**\($ T\_325\_3 VAT Calculation Type $\)**|Specifies the method that is used to calculate the purchase or sale of items.|  
    |**\($ T\_325\_7 Sales VAT Account $\)**|Specifies the number of the general ledger account to which you want to post the sales VAT.<br /><br /> If you have selected the **Reverse Charge VAT** option in the **\($ T\_325\_3 VAT Calculation Type $\)** field, then do not enter a value in this field.|  
    |**\($ T\_325\_9 Purchase VAT Account $\)**|Specifies the number of the general ledger account to which you want to post the purchase VAT.|  
    |**\($ T\_325\_11 Reverse Chrg. VAT Acc. $\)**|Specifies the number of the general ledger account to which you want to post the reverse charge VAT.<br /><br /> You can enter a value in this field only if you have selected the **Reverse Charge VAT** option in the **\($ T\_325\_3 VAT Calculation Type $\)** field.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [\($ R\_11604 BAS\-Update $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-r_11604-bas-update-$-.md)   
 [How to: Print Goods and Service Tax Settlement Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/how-to-print-goods-and-service-tax-settlement-reports.md)