---
title: "How to: Create Deposits"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "deposits, creating"
ms.assetid: d7fa7c0f-3f44-4d37-abbe-a525c29ffc55
caps.latest.revision: 23
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Create Deposits
You can make deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.  
  
### To create a deposit  
  
1.  In the **Search** box, enter **Deposits**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10140\_1 No. $\)**|The unique identification number for the deposit.|  
    |**\($ T\_10140\_2 Bank Account No. $\)**|The bank account number for the deposit.|  
    |**\($ T\_10140\_6 Total Deposit Amount $\)**|The total deposit amount posted to the bank ledger.<br /><br /> You can post this deposit only if the sum of the deposit lines is equal to the value in this field.|  
    |**\($ T\_10140\_5 Posting Date $\)**|The posting date for the deposit.|  
    |**\($ T\_10140\_7 Document Date $\)**|The deposit document date.|  
  
4.  On the **Lines** FastTab, fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_81\_3 Account Type $\)**|The account type.|  
    |**\($ T\_81\_4 Account No. $\)**|The unique identification account number that is associated with the selected account type, to which the entry will be posted.|  
    |**\($ T\_81\_8 Description $\)**|The journal line entry description.|  
    |**\($ T\_81\_76 Document Date $\)**|The journal line entry document date.|  
    |**\($ T\_81\_6 Document Type $\)**|The journal line entry document type.|  
    |**\($ T\_81\_7 Document No. $\)**|The journal line entry document number.|  
    |**\($ T\_81\_15 Credit Amount $\)**|The total credit amount on the journal line.|  
  
5.  Optionally, on the **Navigate** tab, choose **Comments**, and then add relevant comments in the **\($ N\_10130 Bank Comment Sheet $\)** window.  
  
6.  Optionally, on the **Navigate** tab, choose **Dimensions**, and then add relevant dimensions in the **\($ N\_479 Dimension Set Entries $\)** window.  
  
 After you have created a deposit, you must post it.  
  
### To post a deposit  
  
-   On the **Home** tab, choose **Post**.  
  
    > [!NOTE]  
    >  You can post a deposit only if the amount displayed in the **\($ T\_10140\_22 Total Deposit Lines $\)** field is equal to the amount in the **\($ T\_10140\_6 Total Deposit Amount $\)** field.  
  
 Next, you can use the [\($ R\_10402 Deposit Test Report $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10402-deposit-test-report-$-.md) and [\($ R\_10403 Deposit $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10403-deposit-$-.md) reports to reconcile your posted deposits with outstanding invoices and credit memos.  
  
## See Also  
 [\($ T\_270 Bank Account $\)](assetId:///859a3a4a-835d-4443-9715-a8d79d986654)   
 [\($ T\_10140 Deposit Header $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-t_10140-deposit-header-$-.md)   
 [\($ N\_10130 Bank Comment Sheet $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-n_10130-bank-comment-sheet-$-.md)   
 [\($ N\_479 Dimension Set Entries $\)](assetId:///4f5b8d23-f084-4f21-8694-976fef34854c)   
 [\($ R\_10402 Deposit Test Report $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10402-deposit-test-report-$-.md)   
 [\($ R\_10403 Deposit $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10403-deposit-$-.md)