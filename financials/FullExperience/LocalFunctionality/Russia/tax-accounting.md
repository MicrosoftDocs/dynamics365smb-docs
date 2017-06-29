---
title: "Tax Accounting"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax accounting, setting up"
  - "tax registers, defining"
ms.assetid: bff0b833-2996-4e03-8f07-ab23a9f2f9d6
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Tax Accounting
In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can set up and maintain tax registers to track taxable profits and losses. This is based on the following tax accounting principles:  
  
-   The financial database is used for tax accounting.  
  
-   The chart of accounts is used to track taxable profits and losses.  
  
-   Income and expenses are recorded using separate subaccounts and dimensions.  
  
-   Fixed asset transactions and expenses for future periods are tracked using the depreciation book for tax accounting.  
  
-   Tax registers are grouped and totaled monthly. Each register has 12 values for a 12 month tax period.  
  
 Because ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> keeps the history of all transactions, detailed information from a transaction that changes taxable profits is automatically tracked. The information collected in tax registers meets the principles of tax reliability and tax validity.  
  
## Tax Registers  
 There are two types of tax registers that are used for tracking taxable profits and losses.  
  
|Tax Register Type|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|-----------------------|---------------------------------------|  
|Analytic Tax Register|An analytic register is based on ledger entries for taxable transactions. The information provides a continuous chronological reflection of business operations, which tracks taxable profits and losses based on tax codes.|  
|Synthetic Tax Register|A synthetic register is based on summarized and calculated information from an analytic register or another synthetic register.|  
  
 Transactions are processed using specific tax accounting principles that are applied to the following types of tax registers.  
  
|Tax Register|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|------------------|---------------------------------------|  
|General Ledger Entry|An analytic register based on general ledger transaction entries.|  
|CV Entry|A group of analytic registers based on information associated with debtor or creditor liabilities.|  
|Fixed Asset Entry|A group of analytic registers based on tax data for fixed assets. This group is created by using a fixed asset ledger and a tax depreciation book that is not integrated with the financial accounting ledger.|  
|Item Entry|An analytic register based on posted item transactions.|  
|Future Expense Entry|A group of analytic registers based on tax data for future expenses. This group is created by using a fixed asset ledger and a tax depreciation book that is not integrated with the financial accounting ledger.|  
|Accumulation|A synthetic register based on calculated algorithms defined during tax register set up.|  
  
## See Also  
 [How to: Set Up Tax Accounting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-tax-accounting.md)   
 [Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-registers.md)   
 [How to: Create Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-tax-registers.md)   
 [How to: Set Up Tax Register Sections](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-tax-register-sections.md)   
 [Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-differences.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)