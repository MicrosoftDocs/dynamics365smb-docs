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
# How to: Set Up Norm Jurisdictions
Norm jurisdictions are based on Russian tax laws that define a variety of tax rates. Norm jurisdictions are used to calculate taxable profits and losses in tax accounting. You can use the **Norm Jurisdictions** window to set up and define norm jurisdictions that can be used when you calculate tax differences.  
  
### To set up norm jurisdictions  
  
1.  In the **Search** box, enter **Norm Jurisdictions**, and then choose the related link.  
  
2.  Enter an identifying **Code** and **Description** for the norm jurisdiction that you want to set up.  
  
3.  On the **Process** tab, choose **Groups** to open the **Norm Groups** window.  
  
4.  In the **Norm Groups** window, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Enter a code to identify the norm group.|  
    |**Description**|Enter a description for the norm group.|  
    |**Has Details**|Specifies if calculation details are defined for the norm group.|  
    |**Search Detail**|Select the method that you use for norm jurisdiction search. The options include **To Date** and **As of Date.**|  
    |**Storing Method**|Select **Calculation** if the norm jurisdiction is calculated with a specific formula. Leave this field blank if the norm is a constant value.|  
  
5.  On the **Process** tab, choose **Details** to open the **Norm Details** window. In this window, you will define a constant tax rate for the norm.  
  
6.  In the **Norm Details** window, enter the following information.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Effective Date**|Enter an effective date for the norm.|  
    |**Norm**|Enter a value for the norm. This value is used to calculate tax differences.|  
  
7.  Choose the **Close** button to close the **Norm Details** window and save your entries.  
  
 The norm jurisdiction that you set up is now available for use in calculating tax differences.  
  
## See Also  
 [Tax Differences](../FullExperience/tax-differences.md)   
 [Setting up Tax Difference Calculation](../FullExperience/setting-up-tax-difference-calculation.md)   
 [Tax Accounting](../FullExperience/tax-accounting.md)   
 [Tax Reports](assetId:///e42ca8e7-1cee-4fb8-9f71-e596f29cabc3)   
 [Tax Registers](../FullExperience/tax-registers.md)   
 [How to: Create Tax Registers](../FullExperience/how-to-create-tax-registers.md)