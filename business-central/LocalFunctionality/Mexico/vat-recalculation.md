---
title: VAT recalculation
description: When a customer pays in a foreign currency, VAT must be recalculated using the exchange rate at the time of the invoice payment.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: exchange rate, foreign currency, invoice payment
ms.date: 02/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# VAT recalculation

When a customer makes payment in a foreign currency, VAT must be recalculated using the exchange rate at the time of the invoice payment.  

A company creates an invoice in a foreign currency for the purchase of taxable goods and taxable services by a foreign customer. This invoice includes VAT. When the customer makes the payment at a later date, VAT is recalculated based on the original sales amount, and adjusted for the new currency rates.  

The following steps show how to create a report for unrealized VAT amounts:  

1. Set up an option to allow recalculation of VAT upon receipt of payment.  
1. Recalculate VAT upon receipt of payment.  
1. Adjust journal entries for realization of VAT taxes payable to recognize exchange differences.  
1. Create a VAT statement that shows the unrealized VAT amounts.

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
[Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
