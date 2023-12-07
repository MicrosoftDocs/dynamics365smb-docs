---
title: Import and post OCR payments [NO]
description: Before you can receive optical character recognition (OCR) payments, you must make certain preparations in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 15000100, 255
ms.date: 12/06/2023
ms.author: bholtorf
---
# Import and post OCR payments
Before you can receive optical character recognition (OCR) payments, you must make the following preparations:  

- Set up a cash receipt journal template to balance OCR transactions according to the document number, instead of the document type.  
- Import and post the OCR payment files to a cash receipt journal.  

## To import OCR payments  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select a journal batch.  

    > [!NOTE]  
    >  OCR payments can only be posted to a cash receipt journal that does not use a balance account in the **Bal. Account No.** field on the cash receipt journal line.  

3.  Choose the **Import Payments** action.  
4.  On the **OCR Payment-BBS** page, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**File Name**|Enter the full path of the import file.|  

5.  Choose the **OK** button to import the payment file to the journal.  

## To post OCR payments  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
2.  Choose the **Post** action.  

The OCR payment files are posted to the cash receipt journal.  

## See also  
 [Electronic Banking in Norway](electronic-banking-in-norway.md)   
 [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)   
 [Set Up OCR Payments](how-to-set-up-ocr-payments.md)   
 [Work With General Journals](../../ui-work-general-journals.md)   
 [Print the OCR Journal - Test Report](how-to-print-the-ocr-journal-test-report.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]