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
# How to: Set Up General Ledger Accounts for Invoice Rounding Differences
To use the automatic invoice rounding function, you must set up the general ledger account or accounts where rounding differences will be posted. Before you can do this, you must set up VAT product posting groups.  
  
### To set up general ledger accounts for invoice rounding differences  
  
1.  In the **Search** box, enter **Chart of Accounts**, and then choose the related link.  
  
2.  Set up the account in the **Chart of Accounts** window and name it **Invoice Rounding** or something similar. [!INCLUDE[d365fin](../../includes/d365fin_md.md)] will use the account name as text for invoices that are rounded.  
  
3.  In the **Gen. Posting Type** field, select <Blank>.  
  
4.  Leave the **VAT Bus. Posting Group** field blank.  
  
5.  Fill in the **VAT Prod. Posting Group** field. You may want to set up a new group code that can be used for invoice rounding.  
  
 Now you can assign the invoice rounding account to posting groups in the **Vendor Posting Groups** window.  
  
## See Also  
 [How to: Set Up Rounding Rules for the LCY](../how-to-set-up-rounding-rules-for-the-lcy.md)   
 [How to: Set Up Rounding Rules for Foreign Currency](../how-to-set-up-rounding-rules-for-foreign-currency.md)   
 [How to: Enable the Invoice Rounding Function](../how-to-enable-the-invoice-rounding-function.md)   
 [How to: Set Up VAT Product Posting Groups](../how-to-set-up-vat-product-posting-groups.md)