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
# How to: Create an Audit File for the Tax Authority
During an examination of the books for a fiscal year, a tax inspector can ask for data about the basis transactions from the general ledger for that fiscal year. Basis transactions usually are processed via journal entries. That is the reason why the journal entries are the basis for the audit file.  
  
 The tax authority stimulates companies to use the audit file but it is not prescribed.  
  
 The audit file can also be used to exchange data between companies. You can select every period you want, but the start and end date of the entered period must be in the same fiscal year.  
  
### To make an Audit file  
  
1.  In the **Search** box, enter **Tax Authority - Audit File**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_11412\_N\_2\_1101100000 Start Date $\)**|Specify the start date of the period on which the data must be based.|  
    |**\($ B\_11412\_N\_2\_1000003 End Date $\)**|Specify the end date of the period on which the data must be based.|  
    |**\($ B\_11412\_N\_2\_1000005 Exclude Begin Balance $\)**|Specifies if the audit file must contain the begin balance of general ledger accounts.<br /><br /> The field is editable if the start date of the period is equal to the start date of a fiscal year.|  
  
3.  Choose the **OK** button to create the audit file. If you do not want to create the audit file, choose the **Cancel** button to close the window.  
  
     When you run the report, you must specify the name and location of the exported file. The default file name is **audit.xaf**, but you can change that. The file extension must be .xaf.  
  
## See Also  
 [Electronic VAT and ICP Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/electronic-vat-and-icp-declarations.md)   
 [How to: Submit Electronic VAT and ICP Declarations](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Netherlands/how-to-submit-electronic-vat-and-icp-declarations.md)   
 Tax Authority - Audit File