---
title: "How to: Set Up VAT Ledgers"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT, ledgers"
  - "VAT, creating"
  - "VAT ledgers, setting up"
ms.assetid: 71373b20-cdcd-4aed-828e-450bf31c8185
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Set Up VAT Ledgers
VAT ledgers are used to store details about VAT in transactions that involve goods and services in Russia or goods imported into Russia. You can create and store different kinds of VAT ledgers. For example, you can create VAT ledgers for:  
  
-   Sales to different groups of customers.  
  
-   Sales amount differences and prepayments.  
  
-   Purchases from different vendor groups.  
  
 To use VAT ledgers, you must specify the relevant number series.  
  
### To set up VAT ledgers  
  
1.  In the **Search** box, enter **\($ N\_118 General Ledger Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_118 General Ledger Setup $\)** window, on the **Numbering** Fast Tab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_98\_12401 VAT Purch. Ledger No. Series $\)**|Specifies the number series that you want to use for VAT ledgers for purchase documents.|  
    |**\($ T\_98\_12402 VAT Sales Ledger No. Series $\)**|Specifies the number series that you want to use for VAT ledgers for sales documents.|  
  
     You must ensure that vendor purchase documents cannot be posted without stating the invoice date and number.  
  
3.  In the **Search** box, enter **\($ N\_111 Vendor Posting Groups $\)**, and then choose the related link.  
  
4.  In the **\($ N\_111 Vendor Posting Groups $\)** window, for the relevant posting groups, select the **\($ T\_93\_12410 VAT Invoice Mandatory $\)** field.  
  
     Next, you must set up VAT posting. For each VAT posting setup you must specify if entries that use the setup must be included in VAT ledgers.  
  
5.  In the **Search** box, enter **\($ N\_472 VAT Posting Setup $\)**, and then choose the related link.  
  
6.  In the **\($ N\_472 VAT Posting Setup $\)** window, for each VAT posting setup, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_325\_12402 Not Include into VAT Ledger $\)**|Specifies if entries that use the setup must be included in VAT ledgers. For more information, see [\($ T\_325\_12402 Not Include into VAT Ledger $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_325_12402-not-include-into-vat-ledger-$-.md).|  
    |**\($ T\_325\_12412 VAT Exempt $\)**|Specifies if entries that use this posting setup are VAT exempt. For more information, see [\($ T\_325\_12412 VAT Exempt $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_325_12412-vat-exempt-$-.md).|  
  
 Now, you can create VAT ledgers for purchases and sales.  
  
## See Also  
 [About Setting Up VAT](../../Finance/about-setting-up-vat.md)   
 [How to: Set Up VAT Business Posting Groups](../../Finance/how-to-set-up-vat-business-posting-groups.md)   
 [How to: Assign VAT Business Posting Groups to Customer Accounts and Vendor Accounts](../../Finance/how-to-assign-vat-business-posting-groups-to-customer-accounts-and-vendor-accounts.md)   
 [How to: Register VAT on Purchase Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-register-vat-on-purchase-orders.md)   
 [How to: Prepare VAT Entries for Posting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-prepare-vat-entries-for-posting.md)   
 [How to: Create VAT Ledgers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-vat-ledgers.md)   
 [How to: Create Additional Sheets](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-additional-sheets.md)