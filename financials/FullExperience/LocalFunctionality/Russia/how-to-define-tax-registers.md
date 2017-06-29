---
title: "How to: Define Tax Registers"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax registers, defining"
  - "tax registers, creating"
  - "taxes"
  - "tax registers, setting up"
ms.assetid: abc6cccc-5373-45d3-bf4d-b522d10a3db2
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Define Tax Registers
Tax registers are used to track and manage taxable profits and losses in accordance with Russian tax accounting principles. You can use the **Tax Register Card** window to define how tax registers calculate taxable profits and losses and record the results.  
  
### To define tax registers  
  
1.  In the **Search** box, enter **Tax Register Card**, and then choose the related link.  
  
2.  On the **General** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specifies the entry number that is assigned to the tax register.|  
    |**Description**|Enter a description for the tax register.|  
    |**Level**|Specifies the parent\/child relationship between tax registers. Top\-level parent tax registers should be **0**.|  
    |**Costing Method**|Select the inventory valuation costing method that is used for the tax register.|  
    |**G\/L Corr. Analysis View Code**|Select the code of the general ledger correspondence analysis view that you want to use for the tax register.|  
  
3.  On the **Register Lines** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Line Code**|Enter a code to identify the tax register line.|  
    |**Account Type**|Select the account type of the tax register line. Options include **Correspondence** and **G\/L Account**.|  
    |**Amount Type**|Select the amount type of the tax register line. Options include **Debit**, **Credit**, and **Net Change**.|  
    |**Account No.**|Enter the general ledger account number for the tax register line.|  
    |**Bal. Account No.**|Enter the general ledger balance account number for the tax register line. The calculated tax register line balance amount will be stored in this account.|  
    |**Dimensions Filters**|Specifies if a dimension filter has been entered for the tax register line. If a dimension filter has been entered, the value will be **Present**.|  
    |**G\/L Corr. Dimensions Filters**|Specifies if a general ledger correspondence dimension filter has been entered for the tax register line. If a dimension filter has been entered, the value will be **Present**.|  
  
4.  On the **Template Line** FastTab, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Line Code**|Enter a code to identify the tax register template line.|  
    |**Expression**|Enter a formula for the tax register template line.|  
    |**Term Line Code**|Enter the tax register line code that is used for the template line.|  
    |**Dimensions Filters**|Specifies if a dimension filter has been entered for the tax register template line. If a dimension filter has been entered, the value will be **Present**.|  
    |**G\/L Corr. Dimensions Filters**|Specifies if a general ledger correspondence dimension filter has been entered for the tax register template line. If a dimension filter has been entered, the value will be **Present**.|  
  
5.  Choose the **Close** button to close the window and save your entries.  
  
## See Also  
 [Tax Accounting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-accounting.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)   
 [Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-registers.md)   
 [How to: Create Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-tax-registers.md)   
 [Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-differences.md)