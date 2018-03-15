---
    title: How to Post Preliminary Invoices by Using Inward Registration
    description: Use an inward registration to post a preliminary purchase invoice, which you overwrite later when you post the invoice normally.

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
# Post Preliminary Invoices by Using Inward Registration
Use an inward registration to post a preliminary purchase invoice, which you overwrite later when you post the invoice normally. For more information, see Inward Registration.  

## To post a preliminary invoice  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoices**, and then choose the related link.  
2.  Select an invoice, or create a new invoice.  
3.  Choose the **Inward Registration** action.  
4.  Choose **New**, enter a vendor invoice number on the header of the **Inward Registration** window, and then fill in the lines as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**VAT Prod. Posting Group**|Enter a VAT posting group. This code is used in conjunction with the VAT business posting group to retrieve the VAT percentage and the VAT calculation type.|  
    |**Gen. Prod. Posting Group**|Enter a general posting group.|  

5.  Choose the **Post** action to post the preliminary invoice.  
6.  Choose the **Yes** button to confirm that you want to post the inward registration.  

An inward registration is now created to represent the preliminary invoice posting until you overwrite it with the final invoice posting later. You can see the resulting positive entry in the **Inward Reg. Entry** window.  

If you want to cancel the inward registration before the final invoice posting, then you must reverse the inward registration manually. For more information, see [Reverse Preliminary Invoices by Using Inward Registration](how-to-reverse-preliminary-invoices-by-using-inward-registration.md)  

## See Also  
 [Record Purchases](../../purchasing-how-record-purchases.md)   
 [Reverse Preliminary Invoices by Using Inward Registration](how-to-reverse-preliminary-invoices-by-using-inward-registration.md)   
 [Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
 [Sweden Local Functionality](sweden-local-functionality.md)
