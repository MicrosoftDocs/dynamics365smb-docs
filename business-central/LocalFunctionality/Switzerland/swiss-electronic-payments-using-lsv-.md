---
title: Swiss electronic payments using LSV+ [CH]
description: Learn about the LSV+, or direct debit, which is an electronic payment method that permits companies to retrieve payments directly from their customers' bank accounts.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: LSV+, direct debit, direct payment retrieval, Swiss version
ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
ms.date: 04/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Swiss electronic payments using LSV+ in the Swiss version

The Lastschrift Verfahren (LSV+)—or direct debit—electronic payment method, an improved version of LSV, allows companies to retrieve payments directly from its customers’ bank accounts. To retrieve customer payments, you must send an LSV file to the bank, the bank then collects the payments requested in the file.  

The LSV+ method is a direct debit principle with right of objection. Business Direct Debit (BDD) is a direct debit system without right of objection. The file format to be sent to the bank is the same for LSV+ and BDD.  

Before using the LSV module, you must define the settings on the **LSV Setup** page.

## Automatic ESR processing

You can download payment credit transactions in Einzahlungsschein mit Referenznummer (ESR) file format from the bank. You can receive processed LSV payments in the ESR file if the ESR reference number is integrated with the LSV+ system. If LSV+ payments are included in your imported LSV files, the related LSV journal lines are closed automatically. Automatic ESR processing is performed only for payments that use Swiss Francs (CHF), and requires that you do the following steps:  

1. After sending the LSV+ file to the bank, submit a payments report within three business days following the requested LSV processing date.  

1. Import the ESR files, and post the ESR journals. If an imported ESR transaction is related to an open LSV+ payment line, then the ESR automatically closes the appropriate LSV journal line.  

    > [!NOTE]  
    > When importing an ESR file, the ESR closes the LSV journal line if the appropriate LSV journal is found, regardless of the ESR transaction type.  

1. After the LSV processing date, you can check the LSV journal lines. If all of the LSV journal lines are closed, then the status of the **LSV Status** field is updated to  **Finished**.  

## Related information

- [Process an LSV Collection](how-to-process-an-lsv-collection.md)
- [Close an LSV Collection](how-to-close-an-lsv-collection.md)
- [Post LSV+ Payments](how-to-post-lsv-payments.md)
- [Export Payments Using LSV](how-to-export-payments-using-lsv.md)
- [Swiss Electronic Payments](swiss-electronic-payments.md)
- [Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)
- [Making Payments](../../payables-make-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
