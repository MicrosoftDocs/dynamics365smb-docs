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
# How to: Submit Electronic VAT and ICP Declarations
With the eXtensible Business Reporting Language \(XBRL\) reporter, you can submit the Intracommunautaire Leveringen \(ICP\) declaration or the VAT declaration in the required XML format. When it is submitted, the file is sent to the tax authorities as defined in the Elec. Tax Declaration Setup Window.  
  
 The XBRL reporter ensures that all account numbers that are imported from ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> are mapped to the XBRL elements in a report. The XBRL reporter also displays a list of errors of unmapped elements or accounts.  
  
 To submit electronic VAT and ICP declarations to the tax authorities, you can use the **Submit electronic VAT Declaration** batch job and **Submit electronic ICP Declaration** batch job, respectively. The batch job will sign, compress, and encrypt the electronic declaration before submitting it to the tax authorities.  
  
### To submit an electronic VAT or ICP declaration  
  
1.  In the **Search** box, enter **Elec. Tax Declarations**, and then choose the related link.  
  
2.  Select the electronic declaration that you want to submit, and then, on the **Home** tab, choose **Edit**.  
  
    > [!NOTE]  
    >  You can only submit an electronic declaration that has the status **Created**. For more information about the status of the electronic declaration, see Status Field.  
  
3.  On the **Home** tab, in the **Process** group, choose **Submit Electronic Tax Declaration**.  
  
4.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**PIN**|The personal identification number of the company.<br /><br /> You can enter a value in this field only if you have set the **Sign Method** field to **PIN** in the **Elec. Tax Declaration Setup** window.|  
    |**User Certificate Password**|The password that will encrypt the user certificates.<br /><br /> You can enter a value in this field only if you have set the **Sign Method**  field to **PKI** in the **Elec. Tax Declaration Setup** window.|  
  
5.  Choose the **OK** button.  
  
     The electronic declaration is submitted to the tax authorities.  
  
## See Also  
 Elec. Tax Declaration Setup Window   
 [eXtensible Business Reporting Language](../extensible-business-reporting-language.md)