---
title: Electronic banking in Norway
description: Learn about the Norwegian-specific enhancements in Business Central for managing electronic banking operations efficiently.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: Norwegian enhancements, manage electronic banking, KID, Kunde ID
ms.date: 05/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic banking in Norway

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Norwegian enhancements to electronic banking. You can use this functionality to perform the following operations:  

- Receive electronic payments based on an optical character recognition (OCR) payment ID.  
- Print Kunde ID (KID) numbers on sales and receivables documents.  
- Send electronic payments to vendors.  

## Customer identification numbers

Kunde ID (KID) is a customer identification number that provides a payment reference to the vendor and ensures that the vendor is posting the payment correctly. If the vendor documents include the KID number, you should use this number as there might be a higher cost for the payment if you don't.  

The KID can be entered in the following locations:  

- Sales invoices  
- Finance charge memos  
- Reminders  
- Purchase orders  
- Purchase invoices  
- Purchase journals  
- Remittance journals  

> [!NOTE]  
> The KID can't be used for credit memos. If a credit memo is part of the payment, invoices in the same payment must be treated as payments without a KID.  

## Related information

- [Norway Local Functionality](norway-local-functionality.md)
- [Norwegian Giro and OCR-B Font](norwegian-giro-and-ocr-b-font.md)
- [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)
- [Set Up OCR Payments](how-to-set-up-ocr-payments.md)
- [Import and Post OCR Payments](how-to-import-and-post-ocr-payments.md)
- [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)
- [Print the OCR Journal - Test Report](how-to-print-the-ocr-journal-test-report.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
