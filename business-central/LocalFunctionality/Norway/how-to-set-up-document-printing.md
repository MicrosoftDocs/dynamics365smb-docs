---
title: How to Set Up Document Printing
description: Learn how to print sales reports with giro specifications using various paper types and trays.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: print sales reports, giro specifications, paper types and trays, KID information, Norwegian version
ms.date: 05/13/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up document printing

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can print the sales reports that use the required giro specifications by using different paper types and paper trays.  

When you use tray numbers and paper sources for Norwegian sales documents, you must consider how the printer and printer driver interpret this information. You may have to specify other tray numbers for your specific printer.  

> [!NOTE]  
> KID information also prints where the giro information is printed.  

The following documents require a printed giro:  

- Invoices  
- Credit memos  
- Finance charge memos  
- Reminders  

The Norwegian version of [!INCLUDE[prod_short](../../includes/prod_short.md)] contains the following sets of sales documents.  

|**Set**|Description|  
|-------------|---------------------------------------|  
|1|The standard [!INCLUDE[prod_short](../../includes/prod_short.md)] documents. No giro information is printed.|  
|2|The giro is printed on every page. The last page prints the giro total.|  

## Set up paper trays  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Printer Selections**, and then choose the related link.  
1. Select the report.  
1. Choose the **Sales Document Paper Tray Setup** action.  
1. Select a paper source from the **First Page - Paper Source** field.  
1. The **First Page – Tray Number** field automatically displays the selected paper source. You can also manually enter a tray number.  

    > [!IMPORTANT]  
    > Not all printers have the same paper source names. You can specify a number in the **Tray Number** field. The number may correspond to a paper source. To find the number that a specific printer is using, see the technical documentation for the printer.  

    The **Other Pages** and **Giro Page** fields are set up the same way.  

1. Choose the **OK** button.  

## Related information

- [Norwegian Giro and OCR-B Font](norwegian-giro-and-ocr-b-font.md)
- [Set Up KID Numbers on Sales Documents](how-to-set-up-kid-numbers-on-sales-documents.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
