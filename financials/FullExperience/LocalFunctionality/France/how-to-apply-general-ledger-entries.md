---
title: "How to: Apply General Ledger Entries"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "general ledger, applying entries"
ms.assetid: cae52be8-0946-4364-a816-1992d2ffd7b8
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# How to: Apply General Ledger Entries
You apply general ledger entries to justify ledger balances on asset and liability accounts. For example, you can apply transactions on the bill of exchange accounts to get a clear picture of which bills make up the balance of the account.  
  
### To apply general ledger entries  
  
1.  In the **Search** box, enter **\($ N\_16 Chart of Accounts $\)**, and then choose the related link.  
  
2.  In the **\($ N\_16 Chart of Accounts $\)** window, select the account that you want to apply entries for, and then on the **Navigate** tab, in the **Account** group, choose **Apply Entries**.  
  
3.  In the **\($ N\_10842 Apply G\/L Entries $\)** window, select the ledger entries that you want to apply.  
  
4.  On the **Navigate** tab, in the **Process** group, choose **Set Applies\-to ID** to populate the [\($ T\_17\_10811 Applies\-to ID $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_17_10811-applies-to-id-$-.md) field with the user ID of the current user.  
  
5.  On the **Navigate** tab, in the **Process** group, choose **Post Application**.  
  
     This effectuates the application by setting the [\($ T\_17\_10812 Letter $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_17_10812-letter-$-.md) and [\($ T\_17\_10813 Letter Date $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_17_10813-letter-date-$-.md) fields.  
  
> [!NOTE]  
>  Applied entries will be identified by the same three\-letter combination and the same date. Balanced entries will be assigned only uppercase letters, and unbalanced entries will be assigned only lowercase letters.  
  
## See Also  
 [How to: Unapply General Ledger Entries](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-unapply-general-ledger-entries.md)