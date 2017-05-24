---
title: "How to: Post Preliminary Invoices by Using Inward Registration"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "invoices, posting inward registrations"
  - "inward registration, posting"
ms.assetid: 29a35918-cb8e-4854-96df-94c78253b546
caps.latest.revision: 22
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "sv-se"
---
# How to: Post Preliminary Invoices by Using Inward Registration
Use an inward registration to post a preliminary purchase invoice, which you overwrite later when you post the invoice normally. For more information, see [\($ N\_11200 Inward Registration $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-n_11200-inward-registration-$-.md).  
  
### To post a preliminary invoice  
  
1.  In the **Search** box, enter **Purchase Invoices**, and then choose the related link.  
  
2.  Select an invoice, or create a new invoice.  
  
3.  On the **Navigate** tab, in the **Invoice** group, choose **Inward Registration**.  
  
4.  Choose **New**, enter a vendor invoice number on the header of the **\($ N\_11200 Inward Registration $\)** window, and then fill in the lines as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_11201\_6 VAT Prod. Posting Group $\)**|Enter a VAT posting group. This code is used in conjunction with the VAT business posting group to retrieve the VAT percentage and the VAT calculation type.|  
    |**\($ T\_11201\_5 Gen. Prod. Posting Group $\)**|Enter a general posting group.|  
  
5.  Choose **Post** to post the preliminary invoice.  
  
6.  Choose **Yes** to confirm that you want to post the inward registration.  
  
 An inward registration is now created to represent the preliminary invoice posting until you overwrite it with the final invoice posting later. You can see the resulting positive entry in the **\($ N\_11205 Inward Reg. Entry $\)** window.  
  
 If you want to cancel the inward registration before the final invoice posting, then you must reverse the inward registration manually. For more information, see [How to: Reverse Preliminary Invoices by Using Inward Registration](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/how-to-reverse-preliminary-invoices-by-using-inward-registration.md)  
  
## See Also  
 [\($ N\_11200 Inward Registration $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-n_11200-inward-registration-$-.md)   
 [\($ N\_11205 Inward Reg. Entry $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-n_11205-inward-reg.-entry-$-.md)   
 [\($ T\_11201 Inward Reg. Line $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/-$-t_11201-inward-reg.-line-$-.md)   
 [Record Purchase Invoices](../../Finance/record-purchase-invoices.md)   
 [How to: Reverse Preliminary Invoices by Using Inward Registration](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/how-to-reverse-preliminary-invoices-by-using-inward-registration.md)   
 [How to: Record VAT](../../Finance/how-to-record-vat.md)   
 [Sweden Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/sweden-local-functionality.md)