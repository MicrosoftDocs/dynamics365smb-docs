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
# How to: Allocate and Post Fixed Asset Charges
After an invoice has been created you can allocate and post fixed asset charges. The following procedure shows how to allocate and post a fixed asset charge.  
  
### To allocate and post a fixed asset charge  
  
1.  In the **Search** box, enter **Allocate FA Charges**, and then choose the related link.  
  
2.  On the **Options** FastTab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**\($ R\_14912\_F\_1\_1210000 Source Document Type $\)**|Specify the source document type. Types include **Invoice**, **Order**, and **Posted Invoice**.|  
    |**\($ R\_14912\_F\_1\_1210002 Source Document No. $\)**|Specify the source document number that is associated with the fixed asset charge.|  
    |**\($ R\_14912\_F\_1\_1210004 Amount $\)**|Specify the amount of the fixed asset charge.|  
    |**\($ R\_14912\_F\_1\_1210006 FA Charge No. $\)**|Specify the number of the fixed asset charge.|  
  
3.  Choose the **OK** button, and then post the invoice. If the fixed asset has already been released, lines with the relevant general ledger account will be displayed.  
  
## See Also  
 Purchase Header   
 [Fixed Assets Accounting Setup](../fixed-assets-accounting-setup.md)   
 Allocate FA Charges