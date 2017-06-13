---
title: "Belgian VAT"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, in Belgium"
  - "VAT, non-deductible"
ms.assetid: 547af500-b537-4ca9-ab63-0aaaeebc83ae
caps.latest.revision: 3
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# Belgian VAT
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes Belgium enhancements to VAT reporting feature that enables you to print VAT transaction details. You must send the following reports to the Belgian tax authorities:  
  
-   Monthly\/Quarterly declaration \- This report is used to create monthly or quarterly VAT declarations, depending on your company revenue.  
  
-   VAT annual listing \(on paper\/disk\) \- This report is used to annually report all amounts invoiced for both goods and services to all Belgian companies with a registered VAT number.  
  
-   VAT\-VIES listing \(on paper\/disk\) \- This report is used to report the sales of goods to other countries.  
  
 You are also required to provide a printed statement detailing the VAT transactions to the Belgian tax authorities. For more information, see [VAT Statement](../Topic/\($%20R_12%20VAT%20Statement%20$\).md).  
  
## Non\-Deductible VAT  
 In Belgium, VAT can be fully or partially deductible. Expenses such as representation cost or purchases of cars are only partially deductible, and the transaction must specify how much of the VAT is non\-deductible. For example, you create a general ledger account for fixed assets such as cars, and another account for representation cost. For each account, you specify how much of the reported VAT is non\-deductible by setting the [Percentage Non deductible VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_15_11300-percentage-non-deductible-vat-$-.md) field. Then, when you post a transaction, the deductible VAT will post to the corresponding VAT account, and the non\-deductible VAT will be added to the base amount and posted to the same account as the tangible or intangible asset.  
  
 For fixed assets, the non\-deductible VAT depreciates just like the base acquisition cost of the fixed asset. You must set up separate fixed asset posting groups for each percentage of non\-deductible VAT since each fixed asset posting group posts to a general ledger account where the [Percentage Non deductible VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_15_11300-percentage-non-deductible-vat-$-.md) field specifies how much VAT must post to the same account as the fixed asset.  
  
 If you select the [Incl. Non Deductible VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/-$-t_256_11310-incl.-non-deductible-vat-$-.md) field in a VAT statement line, non\-deductible VAT is included in the VAT amount. The **Calc. and Post VAT Settlement** report adds the non\-deductible part of that amount to the **Non Ded. VAT Amount** and **Non Ded. Source Curr. VAT Amt.** fields in the resulting VAT entries.  
  
## See Also  
 [Belgium Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgium-local-functionality.md)   
 [How to: Print Periodic VAT Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-print-periodic-vat-reports.md)   
 [How to: Set Up Non\-Deductible VAT](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-non-deductible-vat.md)