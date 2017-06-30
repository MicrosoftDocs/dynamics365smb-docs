---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Deletion of G-L Accounts
Before a G\/L account can be deleted, the following criteria must be met:  
  
 The balance on the account must be zero.  
  
 If there is a date in the **Allow G\/L Acc. Deletion Before** field in the **General Ledger Setup** window, the account must not have ledger entries on or after that date.  
  
 If there is a check mark in the **Check G\/L Account Usage** field in the **General Ledger Setup** window, then the account must not be used in any of the following setup tables:  
  
 Currency  
  
 Customer Posting Group  
  
 Vendor Posting Group  
  
 Job Posting Group  
  
 General Posting Setup  
  
 Bank Account Posting Group  
  
 VAT Posting Setup  
  
 FA Posting Group  
  
 Inventory Posting Setup  
  
 Service Contract Account Group  
  
 Gen. Journal Template  
  
 Gen. Journal Batch  
  
 Gen. Jnl. Allocation  
  
 FA Allocation  
  
## See Also  
 [How to: View Where General Ledger Accounts Are Used](../how-to-view-where-general-ledger-accounts-are-used.md)   
 General Ledger Setup   
 Allow G\/L Acc. Deletion Before   
 Check G\/L Account Usage