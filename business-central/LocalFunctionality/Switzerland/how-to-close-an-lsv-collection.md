---
title: Close an LSV Collection in the Swiss Version [CH]
description: Close an LSV+ collection in the Swiss version of Business Central to prepare a payment collection file, or reopen it before submission to the bank.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: LSV+, LSV files, payment collection, close LSV collection, reopen LSV collection, Swiss version
ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Close an LSV collection in the Swiss version

You must close Lastschrift Verfahren (LSV+) collections to write LSV files that can be sent to the bank for payment collection. When you close a collection, the collection is complete, and the postings in the LSV journal are combined.  

The collection number is assigned when you create the LSV journal. Adding an invoice to the journal transfers this number to the related customer ledger entry and sets **On Hold** to **LSV** to avoid duplicate collection suggestions. Closing the collection checks the invoice amounts and changes the journal status to **Released**. You can also reopen a closed collection.

## Steps to close an LSV collection  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **LSV Journal List**, and then choose the related link.  
1. Select the required journal line, and then choose the **Modify Posting Date** action. This modifies the value in the **Credit Date** field by using the value suggested during the LSV collection.  
1. In the **New Date** field, enter the new date.  
1. Choose the **LSV Close Collection** action.

    > [!NOTE]  
    > The fields on the **Options** FastTab for the **LSV Close Collection** batch job can't be modified, and correspond to the selected journal line.  

1. Choose the **OK** button.  

   On the **LSV Journal List** page, the value in the **LSV Status** field is changed from **Edit** to **Released**. The journal lines can no longer be modified.  

## Steps to reopen an LSV collection  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **LSV Journal List**, and then choose the related link.  
1. Select the journal line for which you want to reopen the collection, and then choose the **LSV Reopen Collection** action.

    > [!NOTE]  
    > You can only reopen the collection if you haven't yet submitted the LSV+ file to the bank.  

1. Choose the **Yes** button to confirm the reopening of the collection.  

## Related information

- [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)
- [Process an LSV Collection](how-to-process-an-lsv-collection.md)
- [Post LSV+ Payments](how-to-post-lsv-payments.md)
- [Export Payments Using LSV](how-to-export-payments-using-lsv.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
