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
# How to: Create VAT Entry Codes
Invoices must specify a VAT entry type code. The VAT entry type codes are based on a list that is established by legislation. Some types of documents, such as corrective or revision invoices, have several codes from the list.  
  
> [!IMPORTANT]  
>  VAT entry type codes are not supported for service documents.  
  
### To set up VAT Type Codes  
  
1.  In the Search box, enter **VAT Entry Types**, and then choose the related link.  
  
2.  In the **VAT Entry Types** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Specify a unique code for the VAT entry type. The code must be two characters long.|  
    |**Description**|Specify a description of the VAT entry.|  
    |**Comment**|Specify a comment, such as a description of when the code must be used.<br /><br /> The maximum length of the comment is 250 characters.|  
  
## See Also  
 [VAT](../vat.md)