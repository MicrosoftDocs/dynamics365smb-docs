---
    title: How to Import and Post OCR Payments
    description: Before you can receive optical character recognition (OCR) payments, you must make certain preparations.

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
# Import and Post OCR Payments
Before you can receive optical character recognition (OCR) payments, you must make the following preparations:  

- Set up a cash receipt journal template to balance OCR transactions according to the document number, instead of the document type.  
- Import and post the OCR payment files to a cash receipt journal.  

## To import OCR payments  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select a journal batch.  

    > [!NOTE]  
    >  OCR payments can only be posted to a cash receipt journal that does not use a balance account in the **Bal. Account No.** field on the cash receipt journal line.  

3.  Choose the **Import Payments** action.  
4.  On the **OCR Payment-BBS** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |** File Name**|Enter the full path of the import file.|  

5.  Choose the **OK** button to import the payment file to the journal.  

## To post OCR payments  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  Choose the **Post** action.  

The OCR payment files are posted to the cash receipt journal.  

## See Also  
 [Electronic Banking in Norway](electronic-banking-in-norway.md)   
 [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)   
 [Set Up OCR Payments](how-to-set-up-ocr-payments.md)   
 [Work With General Journals](../../ui-work-general-journals.md)   
 [Print the OCR Journal - Test Report](how-to-print-the-ocr-journal-test-report.md)
