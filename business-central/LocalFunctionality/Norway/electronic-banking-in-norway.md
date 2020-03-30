---
    title: Electronic Banking in Norway
    description: Norwegian enhancements include electronic banking.

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
# Electronic Banking in Norway
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes Norwegian enhancements to electronic banking. You can use this functionality to perform the following operations:  

- Receive electronic payments based on an optical character recognition (OCR) payment ID.  
- Print Kunde ID (KID) numbers on sales and receivables documents.  
- Send electronic payments to vendors.  

## Customer Identification Numbers  
 Kunde ID (KID) is a customer identification number that provides a payment reference to the vendor and ensures that the vendor is posting the payment correctly. If the vendor documents include the KID number, you should use this number as there may be a higher cost for the payment if you do not.  

 The KID can be entered in the following locations:  

- Sales invoices  
- Finance charge memos  
- Reminders  
- Purchase orders  
- Purchase invoices  
- Purchase journals  
- Remittance journals  

> [!NOTE]  
>  The KID cannot be used for credit memos. If a credit memo is part of the payment, invoices in the same payment must be treated as payments without a KID.  

## See Also  
 [Norway Local Functionality](norway-local-functionality.md)   
 [Norwegian Giro and OCR-B Font](norwegian-giro-and-ocr-b-font.md)   
 [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)   
 [Set Up OCR Payments](how-to-set-up-ocr-payments.md)   
 [Import and Post OCR Payments](how-to-import-and-post-ocr-payments.md)   
 [Electronic Payments to Vendors in Norway](electronic-payments-to-vendors-in-norway.md)   
 [Print the OCR Journal - Test Report](how-to-print-the-ocr-journal-test-report.md)
