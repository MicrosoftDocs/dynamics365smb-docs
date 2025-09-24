---
title: Export Payments Using LSV [CH]
description: Learn how to export or write Lastschrift Verfahren (LSV+) files that contain payments information after closing the LSV collection.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: LSV files, export LSV files, write LSV files, Swiss version
ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
ms.date: 04/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export payments using LSV in the Swiss version

You can export or write Lastschrift Verfahren (LSV+) files that contain payments information after closing the LSV collection. You can send the generated files to the bank on a disk, or use an electronic file transfer such as your online banking software or an Internet portal.  

## Steps to export payments using LSV  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **LSV Journal List**, and then choose the related link.  
1. On the **LSV Journal List** page, select the required LSV journal.  
1. Choose the **Write LSV File** action.  
1. On the **Write LSV File** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Specify the LSV journal number that you want to export.|  
    |**Test**|Specify if you're sending test deliveries to your bank. The bank doesn't process test files.|  

1. All related lines are transferred to the LSV journal. The LSV file is generated in the predetermined folder.  

## Related information

- [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)
- [Process an LSV Collection](how-to-process-an-lsv-collection.md)
- [Close an LSV Collection](how-to-close-an-lsv-collection.md)
- [Post LSV+ Payments](how-to-post-lsv-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
