---
title: "Tax Registers"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax registers, creating"
  - "tax registers, setting up"
  - "tax registers, types"
ms.assetid: 0d271f4e-6807-4fb2-b1c6-bfa1a603d871
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Tax Registers
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can set up tax registers to track and manage taxable profits and losses in accordance with Russian tax accounting principles. Tax registers allow you to group taxable transactions into logical categories and apply tax accounting rules for the recognition of revenue and expenditures.  
  
## Types of Tax Registers  
 There are two types of tax registers that are used for tracking taxable profits and losses.  
  
|Tax Register Type|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> --> -->|  
|-----------------------|---------------------------------------|  
|Analytic Tax Register|An analytic register is based on ledger entries for taxable transactions. The information provides a continuous chronological reflection of business operations, which tracks taxable profits and losses based on tax codes.|  
|Synthetic Tax Register|A synthetic register is based on summarized and calculated information from an analytic register or another synthetic register.|  
  
## Tax Registers  
 Transactions are processed using specific tax accounting principles that are applied to the following types of tax registers.  
  
|Tax Register|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------------|---------------------------------------|  
|General Ledger Entry|An analytic register based on general ledger transaction entries.|  
|CV Entry|A group of analytic registers based on information associated with debtor or creditor liabilities.|  
|Fixed Asset Entry|A group of analytic registers based on tax data for fixed assets. This group is created by using a fixed asset ledger and a tax depreciation book that is not integrated with the financial accounting ledger.|  
|Item Entry|An analytic register based on posted item transactions.|  
|Future Expense Entry|A group of analytic registers based on tax data for future expenses. This group is created by using a fixed asset ledger and a tax depreciation book that is not integrated with the financial accounting ledger.|  
|Accumulation|A synthetic register based on calculated algorithms defined during tax register set up.|  
  
## Getting Started with Tax Registers  
 To get started with tax registers, see the following topics on key tables, windows, and batch jobs to create and set up tax registers.  
  
|Window|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
|------------|---------------------------------------|  
|Tax Register Setup|Specifies tax register details where you can set up and manage taxable profits and losses.|  
|Create Tax Registers|Creates the tax registers that you define using the **Tax Register Setup** window.|  
  
## See Also  
 [How to: Set Up Tax Accounting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-tax-accounting.md)   
 [How to: Create Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-tax-registers.md)   
 [How to: Set Up Tax Register Sections](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-set-up-tax-register-sections.md)   
 [Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-differences.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)