---
title: "How to: Set Up Tax Accounting"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "tax accounting, setting up"
  - "taxes"
ms.assetid: 9e9f3d51-239f-44f2-92a2-7ac13e89632e
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Set Up Tax Accounting
Tax accounting lets you apply rules for recognizing income and expenses that follow your local tax laws. You can activate tax accounting features in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] by setting up tax registers.  
  
### To activate tax accounting  
  
1.  In the **Search** box, enter **Tax Register Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, select codes for the following dimensions.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_17236\_2 Condition Dimension Code $\)**|Select a dimension code that describes the condition of the tax register.|  
    |**\($ T\_17236\_3 Kind Dimension Code $\)**|Select a dimension code that describes the type of tax register.|  
  
3.  Select the following fields to activate entries in the tax register.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_17236\_4 Create Acquis. FA Tax Ledger $\)**|Select to create fixed asset acquisition entries.|  
    |**\($ T\_17236\_6 Create Reclass. FA Tax Ledger $\)**|Select to create fixed asset reclassification entries.|  
    |**\($ T\_17236\_8 Create Acquis. FE Tax Ledger $\)**|Select to create future expense acquisition entries.|  
  
4.  Select the appropriate depreciation books in the **\($ T\_17236\_5 Tax Depreciation Book $\)** and **\($ T\_17236\_17200 Future Exp. Depreciation Book $\)** fields. The depreciation books that you select should not be integrated with the [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] finance module.  
  
5.  Select the **\($ T\_17236\_17227 Create Data for Printing Forms $\)** check box to enable detailed tax register entry information to be printed on reports and forms.  
  
6.  Choose the **Close** button to close the window and save your entries.  
  
 For more information about how to set up and customize tax registers, see [How to: Create Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-tax-registers.md).  
  
## See Also  
 [Tax Accounting](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-accounting.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)   
 [Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-registers.md)   
 [How to: Create Tax Registers](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/how-to-create-tax-registers.md)   
 [Tax Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/tax-differences.md)