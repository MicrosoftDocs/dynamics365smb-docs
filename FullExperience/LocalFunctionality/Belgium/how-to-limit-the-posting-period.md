---
title: "How to: Limit the Posting Period"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posting periods, limiting"
ms.assetid: 552d62a3-216b-467f-bab7-feb740e74994
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Limit the Posting Period
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can limit the period by which posting is permitted on three different levels: **by company**, **by user**, and **by template**.  
  
 Limiting posting periods can be useful when a company closes its sales journal at the end of each month. This keeps salespeople from registering sales documents from the previous month. At the same time, the purchase journal may stay open to register incoming purchase invoices from the previous month.  
  
 When you post in the **\($ N\_101 General Journal Templates $\)** window, the contents of the **\($ T\_80\_11300 Allow Posting From $\)** field and **\($ T\_80\_11301 Allow Posting To $\)** field are checked for a date interval. The date interval indicates when you can post to a journal template. If the field is blank, the **\($ N\_119 User Setup $\)** window is checked for a date interval for the current user. If the **\($ N\_119 User Setup $\)** window does not contain an interval, the **\($ T\_98\_2 Allow Posting From $\)** field and the **\($ T\_98\_3 Allow Posting To $\)** field in the **\($ N\_118 General Ledger Setup $\)** window is checked for a date interval at the company level.  
  
### To limit the posting periods by company  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  Select the **General** tab.  
  
3.  To specify the start of the period, choose the **\($ T\_98\_2 Allow Posting From $\)** field, and then enter the earliest date on which posting to the company is enabled.  
  
4.  To specify the end of the period, choose the **\($ T\_98\_3 Allow Posting To $\)** field, and then enter the last date on which posting to the company is enabled.  
  
### To limit the posting periods by user  
  
1.  In the **Search** box, enter **User Setup**, and then choose the related link.  
  
2.  To specify the start of the period, choose the **\($ T\_91\_2 Allow Posting From $\)** field, and then enter the earliest date on which the user can post to the company.  
  
3.  To specify the end of the period, choose the **\($ T\_91\_3 Allow Posting To $\)** field, and then enter the last date the user will be able to post to the company.  
  
### To limit the posting periods by template  
  
1.  In the **Search** box, enter **General Journal Templates**, and then choose the related link.  
  
2.  To specify the start of the period, choose the **\($ T\_80\_11300 Allow Posting From $\)** field, and then enter the earliest date on which the user can post to the company.  
  
3.  To specify the end of the period, choose the **\($ T\_80\_11301 Allow Posting To $\)** field, and then enter the last date the user will be able to post to the company.  
  
## See Also  
 [Belgium Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/belgium-local-functionality.md)   
 [\($ T\_98 General Ledger Setup $\)](assetId:///199e09dc-fe90-4792-be3e-ad395447dfd6)   
 [\($ T\_80 Gen. Journal Template $\)](assetId:///eb60bf94-fc5b-442c-acb8-91df074d20d2)   
 [How to: Specify Posting Periods\-duplicate](../../Finance/how-to-specify-posting-periods-duplicate.md)