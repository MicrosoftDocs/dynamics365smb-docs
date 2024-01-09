---
    title: Swiss electronic payments using LSV+ [CH]
    description: The Lastschrift Verfahren (LSV+)—or direct debit—electronic payment method, allows companies to retrieve payments directly from its customers’ bank accounts. 
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
    ms.date: 12/08/2023
    ms.author: bholtorf
---
# Swiss electronic payments using LSV+ in the Swiss version
The Lastschrift Verfahren (LSV+)—or direct debit—electronic payment method, an improved version of LSV, allows companies to retrieve payments directly from its customers’ bank accounts. To retrieve customer payments, you must send an LSV file to the bank, and the bank will collect the payments requested in the file.  

The LSV+ method is a direct debit principle with right of objection. Business Direct Debit (BDD) is a direct debit system without right of objection. The file format to be sent to the bank is the same for LSV+ and BDD.  

Before using the LSV module, you must define the settings on the **LSV Setup** page.

## Automatic ESR processing  
You can download payment credit transactions in Einzahlungsschein mit Referenznummer (ESR) file format from the bank. You can receive processed LSV payments in the ESR file if the ESR reference number is integrated with the LSV+ system. If LSV+ payments are included in your imported LSV files, the related LSV journal lines are closed automatically. Automatic ESR processing is performed only for payments that use Swiss Francs (CHF), and requires that you do the following:  

- After you have sent the LSV+ file to the bank, submit a payments report within three business days following the requested LSV processing date.  

- Import the ESR files, and post the ESR journals. If an imported ESR transaction is related to an open LSV+ payment line, then the appropriate LSV journal line is automatically closed by ESR.  

    > [!NOTE]  
    >  When importing an ESR file, the LSV journal line is closed by ESR if the appropriate LSV journal is found, regardless of the ESR transaction type.  

- After the LSV processing date, you can check the LSV journal lines. If all of the LSV journal lines are closed, then the status of the **LSV Status** field is updated to  **Finished**.  

## See also  
 [Process an LSV Collection](how-to-process-an-lsv-collection.md)   
 [Close an LSV Collection](how-to-close-an-lsv-collection.md)   
 [Post LSV+ Payments](how-to-post-lsv-payments.md)   
 [Export Payments Using LSV](how-to-export-payments-using-lsv.md)   
 [Swiss Electronic Payments](swiss-electronic-payments.md)   
 [Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)   
 [Making Payments](../../payables-make-payments.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]