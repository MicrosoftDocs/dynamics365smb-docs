---
title: "How to: Specify Posting Periods"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting periods"
  - "posting, setting up periods"
ms.assetid: 150ff6ab-882d-4adc-bab3-ab6d271109d3
caps.latest.revision: 6
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# How to: Specify Posting Periods
When you specify posting periods, you limit the period in which posting is allowed.  
  
### To specify posting periods  
  
1.  In the **Search** box, enter **\($ N\_118 General Ledger Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_118 General Ledger Setup $\)** window, on the **General** tab, in the **\($ T\_98\_2 Allow Posting From $\)** field, specify the start date of the posting period.  
  
3.  In the **\($ T\_98\_3 Allow Posting To $\)** field, specify the end date of the posting period.  
  
     The dates are validated against the allowed posting ranges to make sure that they belong to open fiscal years. For more information, see [\($ N\_10819 Allowed Posting Range $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-n_10819-allowed-posting-range-$-.md).  
  
4.  To verify what the allowed posting range is, on the **Actions** tab, in the **Functions** group, choose **Get Allowed Posting Range**.  
  
 The dates that you define here apply to the whole company, that is, to all users.  
  
> [!NOTE]  
>  You can define different posting periods for different users and apply a posting period to a user in the **\($ N\_119 User Setup $\)** window. If you enter dates here, the dates entered on the **General** tab in the **\($ N\_118 General Ledger Setup $\)** window will not apply to these users.  
  
## See Also  
 [Fiscal Periods and Fiscal Years](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/fiscal-periods-and-fiscal-years.md)   
 [\($ N\_118 General Ledger Setup $\)](assetId:///40b9235c-b0d7-4a9f-9ecf-6dc97655309b)   
 [\($ N\_10819 Allowed Posting Range $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-n_10819-allowed-posting-range-$-.md)