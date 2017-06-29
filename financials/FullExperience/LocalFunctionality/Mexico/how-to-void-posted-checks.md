---
title: "How to: Void Posted Checks"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "posted checks, voiding"
  - "posted checks, printing"
ms.assetid: 35093d4c-c89b-4967-a530-6cb428b55cd8
caps.latest.revision: 28
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Void Posted Checks
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you must void the **Payment Journal** from which the export was initiated to void a check. You cannot void the journal after the file has been transmitted. You must post printed checks before you can void printed checks.  
  
### To post printed checks  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Edit \- Payment Journal** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Batch Name**|The required batch name.|  
    |**Posting Date**|The posting date for the entry.|  
    |**Document Type**|The document type for the entry in the journal line.|  
    |**Document No.**|The document number for the journal line.|  
    |**Account Type**|The account type.|  
    |**Account No.**|The account number.|  
    |**Check Printed**|Indicates if a check has been printed.|  
  
3.  You can only post entries for which checks have already been printed. On the **Home** tab, in the **Process** group, choose **Print Check**.  
  
4.  On the **Options** FastTab, fill in appropriate fields.  
  
5.  On the **Gen. Journal Line**  FastTab, select the appropriate filters.  
  
6.  Choose the **Print** button.  
  
7.  In the **Payment Journa**l window, on the **Actions** tab, in the **Posting** group, choose **Post**. Choose the **Yes** button to confirm.  
  
### To void posted checks  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the required bank account. On the **Actions** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Navigate** tab, in the **Bank Acc.** group, choose **Check Ledger Entries**.  
  
4.  In the **Check Ledger Entries** window, on the **Navigate** tab, in the **Check** group, choose **Void Check**.  
  
5.  Select the **Void Check Only** check box.  
  
6.  To void the check, choose the **OK** button.  
  
## See Also  
 [How to: Issue Checks](../../Finance/how-to-issue-checks.md)   
 [How to: Void Checks](../../Finance/how-to-void-checks.md)   
 Check Ledger Entries   
 Void\-Transmit Elec. Payments   
 [How to: Set Up Electronic Payments for Bank Accounts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-set-up-electronic-payments-for-bank-accounts.md)   
 [How to: Generate Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-generate-electronic-payments.md)