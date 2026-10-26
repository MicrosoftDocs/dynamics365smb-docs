---
title: Import and Post OCR Payments [NO]
description: Learn how to prepare for and receive optical character recognition (OCR) payments in the Norwegian version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: OCR, Optical Character Recognition, OCR payments, Norwegian version
ms.search.form: 15000100, 255
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Import and post OCR payments

Before you can receive optical character recognition (OCR) payments, you must make the following preparations:  

- Set up a cash receipt journal template to balance OCR transactions according to the document number, instead of the document type.  
- Import and post the OCR payment files to a cash receipt journal.  

## Import OCR payments  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Cash Receipt Journals**, and then choose the related link.  
1. In the **Batch Name** field, select a journal batch.  

    > [!NOTE]  
    > The journal batch must have a blank **Bal. Account No.**. The OCR import creates separate balancing lines using the account specified in **OCR Setup**.

1. Choose the **Import Payments** action.  
1. On the **OCR Payment - BBS** page, fill in the fields as described in the following table. If **Format** on **OCR Setup** is **Data Dialog**, the corresponding import report opens instead.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**File Name**|Choose the assist-edit button to upload the OCR payment file.|

1. Choose the **OK** button to import the payment file to the journal.  

## Post OCR payments  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Cash Receipt Journals**, and then choose the related link.  
1. Choose the **Post** action.  

The imported journal lines are posted to the relevant accounts.

## Related information

- [Electronic Banking in Norway](electronic-banking-in-norway.md)
- [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)
- [Set Up OCR Payments](how-to-set-up-ocr-payments.md)
- [Work With General Journals](../../ui-work-general-journals.md)
- [Print the OCR Journal - Test Report](how-to-print-the-ocr-journal-test-report.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
