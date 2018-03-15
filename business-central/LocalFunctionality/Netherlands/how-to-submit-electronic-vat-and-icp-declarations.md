---
    title: How to Submit Electronic VAT and ICP Declarations
    description: With the eXtensible Business Reporting Language (XBRL) reporter, you can submit the Intracommunautaire Leveringen (ICP) declaration or the VAT declaration in the required XML format. When it is submitted, the file is sent to the tax authorities as defined in the Elec. Tax Declaration Setup Window.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Submit Electronic VAT and ICP Declarations
With the eXtensible Business Reporting Language (XBRL) reporter, you can submit the Intracommunautaire Leveringen (ICP) declaration or the VAT declaration in the required XML format. When it is submitted, the file is sent to the tax authorities as defined in the Elec. Tax Declaration Setup Window.  

The XBRL reporter ensures that all account numbers that are imported from [!INCLUDE[d365fin](../../includes/d365fin_md.md)] are mapped to the XBRL elements in a report. The XBRL reporter also displays a list of errors of unmapped elements or accounts.  

To submit electronic VAT and ICP declarations to the tax authorities, you can use the **Submit electronic VAT Declaration** batch job and **Submit electronic ICP Declaration** batch job, respectively. The batch job will sign, compress, and encrypt the electronic declaration before submitting it to the tax authorities.  

## To submit an electronic VAT or ICP declaration  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Elec. Tax Declarations**, and then choose the related link.  
2.  Select the electronic declaration that you want to submit, and then choose the **Edit** action.  

    > [!NOTE]  
    >  You can only submit an electronic declaration that has the status **Created**. For more information about the status of the electronic declaration, see Status Field.  

3.  Choose the **Submit Electronic Tax Declaration** action.  
4.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**PIN**|The personal identification number of the company.<br /><br /> You can enter a value in this field only if you have set the **Sign Method** field to **PIN** in the **Elec. Tax Declaration Setup** window.|  
    |**User Certificate Password**|The password that will encrypt the user certificates.<br /><br /> You can enter a value in this field only if you have set the **Sign Method**  field to **PKI** in the **Elec. Tax Declaration Setup** window.|  

5.  Choose the **OK** button.  

The electronic declaration is submitted to the tax authorities.  

## See Also  
[Create Reports with XBRL](../../bi-create-reports-with-xbrl.md)
