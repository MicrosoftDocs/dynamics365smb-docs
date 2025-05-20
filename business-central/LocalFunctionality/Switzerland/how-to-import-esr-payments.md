---
title: Import ESR Payments [CH]
description: Learn how to electronically import ESR files from your bank, which include details about paid invoices. You can also receive this file by mail.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: import ESR files, paid invoices, ESR payments, ESR invoice data, Swiss version
ms.search.form: 3010531, 3010532
ms.date: 04/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Import ESR payments in the Swiss version

After you receive payment from a customer, you receive a file that contains information about paid invoices. You can receive this file from your bank electronically, or by mail.  

You can import the Einzahlungsschein mit Referenznummer (ESR) invoice data from the file, print the data by using the sales invoice ESR report or the sales ESR coupon report, and verify before posting. Learn more in [Print ESR Invoices](how-to-print-esr-invoices.md).  

## Steps to import ESR payments  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch.  

    > [!NOTE]  
    > The journal must be empty before you import the ESR file. You can't import more than one ESR file into the same cash receipt journal.  

1. Choose the **Read ESR File** action.  

    > [!NOTE]  
    > If you defined more than one ESR bank, a warning message displays instructing you to choose the relevant bank. For more information, see the ESR Setup table.  

1. Choose the **Yes** button, and then choose the **OK** button.  

The payments information is imported to the journal lines. The payments are automatically applied to the respective invoices according to unique ESR reference numbers.  

## Related information

- [Swiss Electronic Payments Using ESR](swiss-electronic-payments-using-esr.md)
- [Print ESR Invoices](how-to-print-esr-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
