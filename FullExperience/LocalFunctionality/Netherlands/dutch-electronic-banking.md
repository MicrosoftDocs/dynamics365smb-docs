---
title: "Docket Reports"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "Docket (report)"
ms.assetid: 348aacf2-0fd7-4db3-b5d4-6fa81a0f54f6
caps.latest.revision: 5
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# Docket Reports
The Dutch telebanking application allows you to combine ledger entries for the same customer or vendor, having the same transaction mode, into one payment or collection order to the bank. As such one total amount will be paid to or collected from the vendor or customer involved. Possibly this combined payment could lack all detail information about the individual payments or collections. Telebanking offers you the possibility to inform your vendor or customer in detail by generating a docket report that describes the individual payments that constitute the total amount paid or collected.  
  
 When generating payment proposals using the [\($ B\_11000000 Get Proposal Entries $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-b_11000000-get-proposal-entries-batch-job-$-.md) batch job the system will place a check mark in the [\($ T\_11000000\_27 Docket $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000000_27-docket-field-$-.md) field on the proposal in case that:  
  
-   The resulting combined payment includes too many invoice numbers to list them in the available four description fields of the new proposal line: [\($ T\_11000000\_11 Description 1 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000000_11-description-1-field-$-.md) field, [\($ T\_11000000\_12 Description 2 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000000_12-description-2-field-$-.md) field, [\($ T\_11000000\_13 Description 3 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000000_13-description-3-field-$-.md) field, and [\($ T\_11000000\_14 Description 4 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11000000_14-description-4-field-$-.md) field.  
  
-   The payment is not based upon an invoice.  
  
## See Also  
 [Telebanking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/telebanking.md)