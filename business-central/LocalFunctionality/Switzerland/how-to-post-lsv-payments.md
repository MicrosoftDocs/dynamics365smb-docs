---
title: How to Post LSV+ payments
description: Learn how to post payments after you receive Lastschrift Verfahren (LSV+) payment advice from the bank.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: post LSV+ payments, LSV+ payment advice, Swiss version
ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
ms.date: 04/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Post LSV+ payments

You can post payments after you receive Lastschrift Verfahren (LSV+) payment advice from the bank.  

## Steps to post LSV+ payments  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Receipt Journals**, and then choose the related link.  
1. Select the required journal, and then choose the **Edit Journal** action.  

    > [!NOTE]  
    > You can select the journal batch for LSV where the balance account you want to address is defined. You can't import more than one LSV journal line into the same cash receipt journal. For more information, see the Cash Receipt Journal page.  

1. Choose the **Get From LSV Journal** action.  
1. On the **LSV Journal List** page, select the LSV journal line that you want to import to the cash receipt journal.  

    > [!NOTE]  
    > You can only import journal lines where the **LSV Status** field is set to **File Created**.  

1. Choose the **OK** button.  

   The LSV journal line is imported into the cash receipt journal. The value in the **LSV Status** field on the **LSV Journal List** page changes from **File Created** to **Finished**.  

   You can check the imported payments, and compare them with your bank payment advice on the **Cash Receipt Journal** page. You can also delete the payment lines that the bank doesn't process, and for which you must follow up with the customer manually.  

1. Choose the **Post** action.  

## Related information

- [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)
- [Process an LSV Collection](how-to-process-an-lsv-collection.md)
- [Close an LSV Collection](how-to-close-an-lsv-collection.md)
- [Export Payments Using LSV](how-to-export-payments-using-lsv.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
