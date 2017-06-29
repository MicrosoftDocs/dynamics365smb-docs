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
# How to: Select a Principle for Posting Purchase Discounts
When you post a purchase invoice that includes one or more discounts, you can choose between two principles for posting discount amounts. You can post discounts separately or you can subtract discounts from invoice discounts.  
  
 Before you can do this, you must have already set up the necessary accounts for posting discount amounts in the chart of accounts. You must also check that you have entered the correct account numbers in the general posting setup in the **Purch. Line Disc. Account** and **Purch. Inv. Disc. Account** fields.  
  
### To choose a principle for posting purchase discounts  
  
1.  In the **Search** box, enter **\($ N\_460 Purchases & Payables Setup $\)**, and then choose the related link.  
  
2.  On the **General** FastTab, in the **Discount Posting** field, choose the principle for posting discounts.  
  
     The following table shows which principle you should choose, depending on whether you want invoice discounts and line discounts to be posted separately or subtracted from the invoice amount.  
  
    |**Discount Posting Principle**|**Invoice Discount**|**Line Discount**|  
    |------------------------------------|--------------------------|-----------------------|  
    |**All Discounts**|Posted separately|Posted separately|  
    |**Invoice Discounts**|Posted separately|Subtracted|  
    |**Line Discounts**|Subtracted|Posted separately|  
    |**No Discounts**|Subtracted|Subtracted|  
  
## See Also  
 [How to: Set Up Invoice Discount Terms](../Purchasing/how-to-set-up-invoice-discount-terms.md)   
 [How to: Enter Invoice Discount Codes on Vendor Cards](../Purchasing/how-to-enter-invoice-discount-codes-on-vendor-cards.md)   
 [How to: Invoice Purchases with Invoice Discounts in LCY](../Finance/how-to-invoice-purchases-with-invoice-discounts-in-lcy.md)   
 [How to: Invoice Purchases with Invoice Discounts in a Foreign Currency](../Finance/how-to-invoice-purchases-with-invoice-discounts-in-a-foreign-currency.md)