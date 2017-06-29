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
# How to: Post Preliminary Invoices by Using Inward Registration
Use an inward registration to post a preliminary purchase invoice, which you overwrite later when you post the invoice normally. For more information, see Inward Registration.  
  
### To post a preliminary invoice  
  
1.  In the **Search** box, enter **Purchase Invoices**, and then choose the related link.  
  
2.  Select an invoice, or create a new invoice.  
  
3.  On the **Navigate** tab, in the **Invoice** group, choose **Inward Registration**.  
  
4.  Choose **New**, enter a vendor invoice number on the header of the **Inward Registration** window, and then fill in the lines as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**VAT Prod. Posting Group**|Enter a VAT posting group. This code is used in conjunction with the VAT business posting group to retrieve the VAT percentage and the VAT calculation type.|  
    |**Gen. Prod. Posting Group**|Enter a general posting group.|  
  
5.  Choose **Post** to post the preliminary invoice.  
  
6.  Choose **Yes** to confirm that you want to post the inward registration.  
  
 An inward registration is now created to represent the preliminary invoice posting until you overwrite it with the final invoice posting later. You can see the resulting positive entry in the **Inward Reg. Entry** window.  
  
 If you want to cancel the inward registration before the final invoice posting, then you must reverse the inward registration manually. For more information, see [How to: Reverse Preliminary Invoices by Using Inward Registration](../FullExperience/how-to-reverse-preliminary-invoices-by-using-inward-registration.md)  
  
## See Also  
 Inward Registration   
 Inward Reg. Entry   
 Inward Reg. Line   
 [Record Purchase Invoices](../FullExperience/record-purchase-invoices.md)   
 [How to: Reverse Preliminary Invoices by Using Inward Registration](../FullExperience/how-to-reverse-preliminary-invoices-by-using-inward-registration.md)   
 [How to: Record VAT](../FullExperience/how-to-record-vat.md)   
 [Sweden Local Functionality](../FullExperience/sweden-local-functionality.md)