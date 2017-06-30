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
# How to: Set Up EHF
You must define a location for storing Elektronisk Handelsformat \(EHF\) files when you create electronic documents such as invoices or credit memos. You must also define payment methods and set up relevant customers for EHF.  
  
### To set up EHF file locations for sales and receivables  
  
1.  In the Search box, enter **\($ N\_459 Sales & Receivables Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_459 Sales & Receivables Setup $\)** window, on the **E-Invoice** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Invoice Path**|The path and name of the folder where you want to store the EHF files for sales invoices.|  
    |**Cr. Memo Path**|The path and name of the folder where you want to store the EHF files for sales credit memos.|  
    |**E-Invoice Reminder Path**|The path and name of the folder where you want to store the EHF files for reminders.|  
    |**E-Invoice Fin. Charge Path**|The path and name of the folder where you want to store the EHF files for finance charge memos.|  
  
3.  Choose the **OK** button.  
  
### To set up EHF file locations for service management  
  
1.  In the **Search** box, enter **Service Mgt. Setup**, and then choose the related link.  
  
2.  In the **Service Mgt. Setup** window, on the **E-Invoice** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**E-Invoice Service Invoice Path**|The path and name of the folder where you want to store the EHF files for service invoices.|  
    |**E-Invoice Serv. Cr. Memo Path**|The path and name of the folder where you want to store the EHF files for service credit memos.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [How to: Set Up Customers for EHF](../how-to-set-up-customers-for-ehf.md)   
 [EHF Electronic Invoicing in Norway](../ehf-electronic-invoicing-in-norway.md)