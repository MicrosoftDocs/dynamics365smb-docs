---
title: Export Payments Using LSV in the Swiss Version [CH]
description: Learn how to export or write Lastschrift Verfahren (LSV+) files that contain payments information after closing the LSV collection.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: LSV files, export LSV files, write LSV files, Swiss version
ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Export payments using LSV in the Swiss version

You can export or write Lastschrift Verfahren (LSV+) files that contain payments information after closing the LSV collection. You can send the generated files to the bank on a disk, or use an electronic file transfer such as your online banking software or an Internet portal.  

## Steps to export payments using LSV  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **LSV Journal List**, and then choose the related link.  
1. On the **LSV Journal List** page, select the required LSV journal.  
1. Choose the **Write LSV File** action.  
1. On the **Write LSV File** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specify the LSV journal number that you want to export.|  
    |**Test**|Specify if you're sending test deliveries to your bank. The bank doesn't process test files.|  

1. Choose **OK**, confirm that you want to write the file, and save the downloaded LSV file.

For a production file, the journal status changes to **File Created**. A test export doesn't advance the status to **File Created**.

## Related information

- [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)
- [Process an LSV Collection](how-to-process-an-lsv-collection.md)
- [Close an LSV Collection](how-to-close-an-lsv-collection.md)
- [Post LSV+ Payments](how-to-post-lsv-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
