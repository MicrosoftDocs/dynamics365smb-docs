---
    title: VAT Recalculation
    description: When a customer makes payment in a foreign currency, VAT must be recalculated using the exchange rate at the time of the invoice payment.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# VAT Recalculation
When a customer makes payment in a foreign currency, VAT must be recalculated using the exchange rate at the time of the invoice payment.  

A company creates an invoice in a foreign currency for the purchase of taxable goods and taxable services by a foreign customer. This invoice includes VAT. When the customer makes the payment at a later date, VAT is recalculated based on the original sales amount, and adjusted for the new currency rates.  

The following steps show how to create a report for unrealized VAT amounts:  

- Set up an option to allow recalculation of VAT upon receipt of payment.  
- Recalculate VAT upon receipt of payment.  
- Adjust journal entries for realization of VAT taxes payable to recognize exchange differences.  
- Create a VAT statement that shows the unrealized VAT amounts.

## See Also  
 [Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
 [Set Up Unrealized Sales Tax and Sales Payment Discounts](how-to-set-up-unrealized-sales-tax-and-sales-payment-discounts.md)   
 [Mexico Local Functionality](mexico-local-functionality.md)
