---
    title: Invoice Discounts on Service Documents | Microsoft Docs
    description: After all the information has been entered on the service lines, you can calculate the invoice discount for the whole service document by using the **Calculate Invoice Discount** function. If the **Calc. Inv. Discount** check box is selected in the **Sales & Receivables Setup** window, the amount will be calculated automatically.
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
# Invoice Discounts on Service Documents
After all the information has been entered on the service lines, you can calculate the invoice discount for the whole service document by using the **Calculate Invoice Discount** function. If the **Calc. Inv. Discount** check box is selected in the **Sales & Receivables Setup** window, the amount will be calculated automatically.  
  
 The discount will be allocated over all the lines in the service document for items, resources, general ledger accounts, and costs where the **Allow Invoice Disc.** field on the service line is set to **Yes**. This is the default setting for items and resources.  
  
 To calculate the invoice discount, the invoice discount terms defined in the **Cust. Invoice Disc.** table are used. To see the invoice discounts that have been set up, in the **Customer** card window, on the **Navigate** tab, in the **Sales** group, choose **Invoice Discounts**.  
  
 The currency code on the service document is used to find the invoice discount terms in the corresponding currency. If invoice discounts have not been defined for foreign currencies, the invoice discount terms in LCY set up in the **Cust. Invoice Disc.** table and the exchange rate as of the posting date on the service document are used.  
  
## See Also  
 [How to: Invoice with Sales Invoice Discounts in LCY](../how-to-invoice-with-sales-invoice-discounts-in-lcy.md)