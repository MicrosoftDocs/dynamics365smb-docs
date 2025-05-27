---
title: Process an LSV collection [CH]
description: Learn how to create and process payments using LSV journals for Lastschrift Verfahren (LSV+) customers in the Swiss version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: process LSV collection, create LSV collection, LSV collection, LSV journal, LSV, Swiss version
ms.search.form: 3010830, 3010831, 3010832,3010834, 3010835
ms.date: 04/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Process an LSV collection in the Swiss version

You can use the **LSV Journal** page to create and process payments from Lastschrift Verfahren (LSV+) customers. You can register these payments in the cash receipt journal, create an LSV file, and then print the collection order. For more information, see the Cash Receipt Journal page and [Export Payments Using LSV](how-to-export-payments-using-lsv.md).  

When you run the **LSV Suggest Collection** batch job, each suggested collection is registered on an LSV journal line, and the open invoices are transferred to the LSV journals. For more information, see the LSV Journal table.  

You can view, edit, or delete the suggested payment lines. If you correct the suggested amount, then the difference is marked as a discount. You can run the batch job multiple times for different customer groups. The suggestion lines can be placed in the same journal.  

## Create an LSV collection  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **LSV Journal List**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **LSV Journal List** page, fill in the required fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**LSV Bank Code**|Select the LSV bank code for the bank that performs the collection.|  
    |**LSV Journal Description**|Enter a description for the entry.|

1. Select the required LSV journal entry, and then choose the **LSV Suggest Collection** action to create the payments to be collected automatically by LSV+.  
1. On the **LSV Suggest Collection** page, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**No.**|Enter the LSV journal number.|  
    |**From due date**|Specify the starting due date of open entries to be suggested for collection.|  
    |**To due date**|Specify the ending due date of open entries to be suggested for collection.|  
    |**Collection date**|Specify the date on which the collection closes. The LSV+ order must be submitted at least three banking days before the collection date.|  

1. Choose the **OK** button.  

All related lines are transferred to the LSV journal. After processing the LSV collection, you can view, check, or edit the suggested payments on the **LSV Journal** page. For more information, see the LSV Journal Line table.  

## Manage suggested payments  

1. On the **LSV Journal List** page, select the required journal entry, and then choose the **LSV Journal Line** action.  

   You can view and modify the suggested payments in this page. You can enter the required payments manually. For new journal lines, the **LSV Status** field is set to **Open** to indicate that the invoice is unpaid.  

1. Choose the **OK** button.  

## Related information

- [Swiss Electronic Payments Using LSV+](swiss-electronic-payments-using-lsv-.md)
- [Close an LSV Collection](how-to-close-an-lsv-collection.md)
- [Post LSV+ Payments](how-to-post-lsv-payments.md)
- [Export Payments Using LSV](how-to-export-payments-using-lsv.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
