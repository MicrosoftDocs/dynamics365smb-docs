---
title: Print the OCR Journal - Test Report
description: Print the Norwegian OCR journal test report in Business Central to review imported payment transactions, OCR warnings, and dimensions before posting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: OCR Journal Test report, test imported payment transactions, reconcile conflicts
ms.search.form: 15000100, 255
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print the OCR journal test report

You can use **OCR control report** on the **Cash Receipt Journal** page to test imported payment transactions. The report request page is captioned **General Journal - Test**. Review warnings and resolve conflicts before posting the payments.

## Print the OCR journal test report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Cash Receipt Journals**, and then choose the related link.
1. Open the journal batch with the imported payments, and then choose **OCR control report**.
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Show only Lines with OCR Errors**|Select to print only the journal lines that contain a warning in the test report.|  
    |**Show Dimensions**|Select to print dimension information on the test report.|  

1. Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information

- [Electronic Banking in Norway](electronic-banking-in-norway.md)
- [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)
- [Set Up OCR Payments](how-to-set-up-ocr-payments.md)
- [Import and Post OCR Payments](how-to-import-and-post-ocr-payments.md)
- [Work with General Journals](../../ui-work-general-journals.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
