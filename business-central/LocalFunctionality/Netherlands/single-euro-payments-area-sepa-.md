---
title: Single Euro Payments Area (SEPA)
description: Learn about Dutch SEPA payment requirements in Business Central, including euro payments,IBANs, and bank account holder details.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: SEPA, unify payment, standardize payment, simplify international payments, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Single Euro Payments Area (SEPA)

The Single Euro Payments Area (SEPA) unifies euro payment methods in participating countries/regions. Businesses and individuals can make and receive euro payments within or across borders under the same basic conditions.

[!INCLUDE[prod_short](../../includes/prod_short.md)] supports the Dutch requirements for submitting SEPA payments, credit transfers, and direct debit.  

Before you can submit vendor payments electronically in SEPA ISO 20022 format, you must configure SEPA in the following pages:

- Countries/Regions  
- Bank Accounts  
- Export Protocols  
- Transaction Modes  

Additionally you need to verify that vendor payment transaction modes and vendor bank accounts are set up to use SEPA for each vendor.  

Vendor payments made using SEPA ISO 20022 must comply with the following rules.  

- Make all payments in euros.  
- Use bank accounts in participating SEPA countries/regions. Select **SEPA Allowed** for the relevant countries/regions.
- Enter the International Bank Account Number (IBAN) for both your bank account and the vendor bank account.
- Complete the bank account holder information. SEPA supports IBAN-only payments, so a Bank Identifier Code (BIC), entered as **SWIFT Code**, isn't universally required.

## Related information

- [Activate SEPA Payments](how-to-activate-sepa-payments.md)   
- [Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format](how-to-submit-vendor-payments-electronically-in-sepa-iso-20022-payment-format.md)   
- [Netherlands Local Functionality](netherlands-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
