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
    |**No.**|The unique identification number for the deposit.|  
    |**Bank Account No.**|The bank account number for the deposit.|  
    |**Total Deposit Amount**|The total deposit amount posted to the bank ledger.<br /><br /> You can post this deposit only if the sum of the deposit lines is equal to the value in this field.|  
    |**Posting Date**|The posting date for the deposit.|  
    |**Document Date**|The deposit document date.|  
  
4.  On the **Lines** FastTab, fill in the required fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|The account type.|  
    |**Account No.**|The unique identification account number that is associated with the selected account type, to which the entry will be posted.|  
    |**Description**|The journal line entry description.|  
    |**Document Date**|The journal line entry document date.|  
    |**Document Type**|The journal line entry document type.|  
    |**Document No.**|The journal line entry document number.|  
    |**Credit Amount**|The total credit amount on the journal line.|  
  
5.  Optionally, on the **Navigate** tab, choose **Comments**, and then add relevant comments in the **Bank Comment Sheet** window.  
  
6.  Optionally, on the **Navigate** tab, choose **Dimensions**, and then add relevant dimensions in the **Dimension Set Entries** window.  
  
 After you have created a deposit, you must post it.  
  
### To post a deposit  
  
-   On the **Home** tab, choose **Post**.  
  
    > [!NOTE]  
    >  You can post a deposit only if the amount displayed in the **Total Deposit Lines** field is equal to the amount in the **Total Deposit Amount** field.  
  
 Next, you can use the Deposit Test Report and Deposit reports to reconcile your posted deposits with outstanding invoices and credit memos.  
  
## See Also  
 Bank Account   
 Deposit Header   
 Bank Comment Sheet   
 Dimension Set Entries   
 Deposit Test Report   
 Deposit