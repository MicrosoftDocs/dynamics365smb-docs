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
# How to: Correct VAT
You can make corrections to already posted VAT entries and change the total sales or purchase VAT amounts without changing the VAT base. You may need to do this, for example, if you receive an invoice from a vendor that has calculated VAT incorrectly.  
  
 Even though you may have set up one or more combinations to handle import VAT, you must set up at least one VAT product posting group code. For example, you can name it **CORRECT** for correction purposes, unless you can use the same general ledger account in the **Purchase VAT Account** field on the VAT posting setup line.  
  
 For more information, see [How to: Set Up Codes for Import VAT](../how-to-set-up-codes-for-import-vat.md).  
  
### To correct VAT  
  
1.  In the **Search** box, enter **General Journal**, and then choose the related link.  
  
2.  In the **General Journal** window, fill in a journal line for the correction. Enter the corrective amount in the **Amount** field. Note that the **VAT Base Amount** field remains 0.00.  
  
    > [!NOTE]  
    >  You cannot enter anything in the field. The base amount fields are not included in the standard layout, but they can be inserted by the system administrator.  
  
3.  On the **Home** tab, choose **Post** to post the journal.  
  
## See Also  
 [How to: Record VAT](../how-to-record-vat.md)