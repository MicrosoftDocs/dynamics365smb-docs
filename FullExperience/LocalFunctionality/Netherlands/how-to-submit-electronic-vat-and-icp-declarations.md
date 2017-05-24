---
title: "How to: Submit Electronic VAT and ICP Declarations"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "exporting, XBRL documents"
  - "VAT declarations, submitting"
  - "ICL declarations"
  - "XBRL documents"
ms.assetid: 0951a12d-f4aa-45ad-9129-079a61f4eda2
caps.latest.revision: 17
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "nl-nl"
---
# How to: Submit Electronic VAT and ICP Declarations
With the eXtensible Business Reporting Language \(XBRL\) reporter, you can submit the Intracommunautaire Leveringen \(ICP\) declaration or the VAT declaration in the required XML format. When it is submitted, the file is sent to the tax authorities as defined in the [\($ N\_11410 Elec. Tax Declaration Setup Window $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_11410-elec.-tax-declaration-setup-window-$-.md).  
  
 The XBRL reporter ensures that all account numbers that are imported from [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] are mapped to the XBRL elements in a report. The XBRL reporter also displays a list of errors of unmapped elements or accounts.  
  
 To submit electronic VAT and ICP declarations to the tax authorities, you can use the **Submit electronic VAT Declaration** batch job and **Submit electronic ICP Declaration** batch job, respectively. The batch job will sign, compress, and encrypt the electronic declaration before submitting it to the tax authorities.  
  
### To submit an electronic VAT or ICP declaration  
  
1.  In the **Search** box, enter **Elec. Tax Declarations**, and then choose the related link.  
  
2.  Select the electronic declaration that you want to submit, and then, on the **Home** tab, choose **Edit**.  
  
    > [!NOTE]  
    >  You can only submit an electronic declaration that has the status **Created**. For more information about the status of the electronic declaration, see [\($ T\_11409\_10 Status Field $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-t_11409_10-status-field-$-.md).  
  
3.  On the **Home** tab, in the **Process** group, choose **Submit Electronic Tax Declaration**.  
  
4.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**PIN**|The personal identification number of the company.<br /><br /> You can enter a value in this field only if you have set the **Sign Method** field to **PIN** in the **\($ N\_11410 Elec. Tax Declaration Setup $\)** window.|  
    |**User Certificate Password**|The password that will encrypt the user certificates.<br /><br /> You can enter a value in this field only if you have set the **Sign Method**  field to **PKI** in the **\($ N\_11410 Elec. Tax Declaration Setup $\)** window.|  
  
5.  Choose the **OK** button.  
  
     The electronic declaration is submitted to the tax authorities.  
  
## See Also  
 [\($ N\_11410 Elec. Tax Declaration Setup Window $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/-$-n_11410-elec.-tax-declaration-setup-window-$-.md)   
 [eXtensible Business Reporting Language](../../BusinessIntelligence/extensible-business-reporting-language.md)