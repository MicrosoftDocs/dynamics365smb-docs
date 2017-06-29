---
title: "How to: Print Checks for APACS"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "APACS (Association for Payment Clearing Services)"
  - "Association for Payment Clearing Services (APACS)"
  - "checks, printing in APACS format"
ms.assetid: c49f0617-8e1b-4684-833e-7cff46cfb9c0
caps.latest.revision: 35
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-gb"
---
# How to: Print Checks for APACS
The Association for Payment Clearing Services \(APACS\) specification defines a standard layout for fields on checks. The **Check** report uses this specification.  
  
### To print checks for APACS  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  To preview the check, on the **Navigate** tab, in the **Payments** group, choose **Preview Check**.  
  
3.  To print the check, on the **Navigate** tab, in the **Payments** group, choose **Print Check**.  
  
4.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_1401\_N\_2\_1 Bank Account $\)**|Specifies bank account code.|  
    |**\($ R\_1401\_N\_2\_3 Last Check No. $\)**|Specifies the last check number that was specified in the **Bank Account Card** window.|  
    |**\($ R\_1401\_N\_2\_11 One Check per Vendor per Document No. $\)**|Select to print only one check per vendor for each document number.|  
    |**\($ R\_1401\_N\_2\_5 Reprint Checks $\)**|Select to reprint canceled checks.|  
    |**\($ R\_1401\_N\_2\_9 Test Print $\)**|Select to print checks on blank paper before printing them on check forms.|  
    |**\($ R\_1401\_N\_2\_13 Preprinted Stub $\)**|Select to use check forms with preprinted stubs.|  
  
5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
## See Also  
 [Check\-duplicate](../Topic/\($%20R_1401%20Check%20$\)-duplicate.md)   
 Payment Journal   
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)