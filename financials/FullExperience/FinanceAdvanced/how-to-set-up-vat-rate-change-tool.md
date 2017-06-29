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
# How to: Set Up VAT Rate Change Tool
This topic describes how you set up the VAT rate change tool and corresponding new posting groups before you perform VAT rate conversions.  
  
### To set up the VAT rate change tool  
  
1.  In the **Search** box, enter **VAT Rate Change Setup**, and then choose the related link.  
  
2.  On the **Master Data**, **Journals**, and **Documents** FastTabs, select a posting group value from the option list for needed fields.  
  
     The following table describes the options that you can select for a field.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |----------------------------------|---------------------------------------|  
    |**No**|The selected field will not be updated.|  
    |**VAT Product Posting Group**|The selected field will be updated by the VAT product posting group conversion.|  
    |**Gen. Prod. Posting Group**|The selected field will be updated by the general product posting group conversion.|  
    |**Both**|The selected field will be updated by the both the VAT and the general product posting group conversions.|  
  
3.  Choose the **OK** button.  
  
### To set up product posting group conversion  
  
1.  In the **Search** box, enter **VAT Rate Change Setup**, and then choose the related link.  
  
2.  In the **VAT Rate Change Setup** window, on the **Home** tab, in the **Process** group, choose either **VAT Prod. Posting Group Conv.** or **Gen Prod. Posting Group Conv.**.  
  
3.  In the **From Code** field, enter the current posting group.  
  
4.  In the **To Code** field, enter the new posting group.  
  
5.  Choose the **OK** button.  
  
## See Also  
 [How to: Prepare VAT Rate Change Conversions](../Finance/how-to-prepare-vat-rate-change-conversions.md)   
 [How to: Perform VAT Rate Conversions](../Finance/how-to-perform-vat-rate-conversions.md)