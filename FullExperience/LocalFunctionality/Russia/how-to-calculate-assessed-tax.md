---
title: "How to: Calculate Assessed Tax"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "taxes, calculating assessed"
ms.assetid: b074afee-03b5-4426-abda-8474b8dc7055
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Calculate Assessed Tax
The assessed tax feature enables you to calculate the assessed tax for fixed assets. The assessed tax is based on the information provided in the **\($ N\_5607 Fixed Asset Setup $\)** window. You can also export the results of the calculated tax as a Microsoft Office Excel template.  
  
### To calculate assessed tax  
  
1.  In the **Search** box, enter **Assessed Tax Allowances**, and then choose the related link.  
  
2.  In the **\($ N\_14920 Assessed Tax Allowances $\)** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_14920\_1 Code $\)**|Specifies the code for the assessed tax that is associated with the fixed asset.|  
    |**\($ T\_14920\_2 Name $\)**|Specifies the name of the assessed tax code.|  
  
3.  Choose the **OK** button.  
  
4.  In the **Search** box, enter **Assessed Tax Codes**, and then choose the related link.  
  
5.  In the **\($ N\_14921 Assessed Tax Codes $\)**window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_14921\_1 Code $\)**|Specifies a code for an assessed tax allowance.|  
    |**\($ T\_14921\_2 Description $\)**|Specifies a description for the assessed tax code.|  
    |**\($ T\_14921\_4 Region Code $\)**|Specifies a two\-character region code that is used together with the Tax Authority No. field to determine the OKATO code.|  
    |**\($ T\_14921\_5 Rate % $\)**|Specifies the tax rate for the assessed tax. If there are any tax allowances that reduce the tax rate, they must be included in the rate percentage.|  
    |**\($ T\_14921\_6 Dec. Rate Tax Allowance Code $\)**|Specifies a code for the assessed tax allowance code that reduces the calculated assessed tax amount according to the tax allowances directory. This code is defined in the **\($ T\_14920 Assessed Tax Allowance $\)** table.|  
    |**\($ T\_14921\_7 Dec. Amount Tax Allowance Code $\)**|Specifies the amount of an assessed tax allowance.|  
    |**\($ T\_14921\_8 Decreasing Amount $\)**|Specifies the value to be used in the assessed tax calculation if there is a tax allowance that reduces assessed taxes.|  
    |**\($ T\_14921\_9 Exemption Tax Allowance $\)**|Specifies a code for an assessed tax allowance exemption. This code is defined in the **\($ T\_14920 Assessed Tax Allowance $\)** table.|  
    |**\($ T\_14921\_10 Decreasing Amount Type $\)**|Specifies whether the decreasing amount value is a percentage or an amount.|  
  
6.  Choose the **Close** button.  
  
7.  In the **Search** box, enter **OKATO Codes**, and then choose the related link.  
  
8.  In the **\($ N\_12430 OKATO Codes $\)** window, fill in the **\($ T\_12427\_3 Region Code $\)** and the **\($ T\_12427\_4 Tax Authority No. $\)** fields, and then choose the **OK** button.  
  
9. In the **Search** box, enter **Fixed Assets**, and then choose the related link.  
  
10. On the **Assessed Tax** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_5600\_14921 Assessed Tax Code $\)**|Specifies the assessed tax code that is associated with the fixed asset.|  
    |**\($ T\_5600\_14927 Property Type $\)**|Specifies the property type of the fixed the fixed asset. Property types include: **Immovable UGSS Property**, **Immovable Distributed Property**, **Other Property**, and **Special Economic Zone Property**.|  
    |**\($ T\_5600\_14926 Book Value per Share $\)**|Specifies the book value of the fixed asset, per share.|  
    |**\($ T\_5600\_14925 OKATO Code $\)**|Specifies the region where the current fixed asset is situated.|  
    |**\($ T\_5600\_14928 Tax Amount Paid Abroad $\)**|Specifies the amount of tax that was paid abroad for the fixed asset.|  
  
11. Choose the **OK** button.  
  
12. To print the assessed tax declaration, you have to first import the declaration template. In the **\($ N\_5607 Fixed Asset Setup $\)** window, select the template name from the **Templates** FastTab.  
  
13. In the **Search** box, enter **Calculate Assessed Tax**, and then choose the related link.  
  
14. In the **\($ B\_14920 Calculate Assessed Tax $\)** window, fill in the **\($ B\_14920\_N\_2\_1470011 Tax Authority No. $\)**, **\($ B\_14920\_N\_2\_1470001 Year $\)**, and the **\($ B\_14920\_N\_2\_1470003 Reporting Period $\)** fields.  
  
15. Choose the **OK** button.  
  
## See Also  
 [\($ N\_5607 Fixed Asset Setup $\)](../Topic/\($%20N_5607%20Fixed%20Asset%20Setup%20$\).md)   
 [Fixed Assets Accounting Setup](../../Finance/fixed-assets-accounting-setup.md)   
 [\($ N\_5600 Fixed Asset Card $\)](../Topic/\($%20N_5600%20Fixed%20Asset%20Card%20$\).md)   
 [\($ B\_14920 Calculate Assessed Tax $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-b_14920-calculate-assessed-tax-$-.md)   
 [\($ T\_14921 Assessed Tax Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_14921-assessed-tax-code-$-.md)   
 [\($ T\_5600\_14921 Assessed Tax Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-t_5600_14921-assessed-tax-code-$-.md)