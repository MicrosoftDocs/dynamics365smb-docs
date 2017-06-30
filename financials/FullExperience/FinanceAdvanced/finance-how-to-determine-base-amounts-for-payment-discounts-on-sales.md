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
# How to: Determine Base Amounts for Payment Discounts on Sales
Payment discounts are dependent on when an invoice is paid. They function independently of the other discounts, which are dependent on the item or customer.  
  
 You must decide if payment discounts are based on the invoice amount with or without VAT.  
  
### To determine a base amount for payment discounts on sales  
  
1.  In the **Search** box, enter **General Ledger Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, select the **Pmt. Disc. Excl. VAT** field, if you want payment discounts to be calculated from the invoice amount without VAT.  
  
     If you want payment discounts to be calculated from the invoice amount including VAT, clear the **Pmt. Disc. Excl. VAT** field.  
  
> [!IMPORTANT]  
>  The selection that you make in this field also determines how payment discounts are calculated for purchase invoices.