---
title: Print vendor payments list reports in the German version
description: The Vendor Payments List report lists payments for each vendor in the German version. It can sort payments chronologically or by vendor.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: vendor payments list, sort payments chronologically, sort payments by vendor, vendor payments list report
ms.date: 03/11/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print Vendor Payments List reports in the German version

The **Vendor Payments List** report provides a list of payments for each vendor. The report can sort payments chronologically or grouped by vendor.  

> [!NOTE]
> The **Vendor Payments List** report is available in the following markets: Austria, Germany, Switzerland.

## Procedure to print

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Payments List**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sorting**|Specifies the sort order. You can sort by vendor or chronologically. If you sort by vendor, you see a subtotal for each vendor. If you sort chronologically, you can't see subtotals.|  
    |**Layout**|Specifies the layout of the report.<br><br/> The results can be displayed in the following layouts:<br><br/>**Standard**: Displays the vendor number and vendor name, together with posting details, such as the document number and the amount in local currency.<br><br/>**FCY Amounts**: Displays the vendor number, vendor name, document number, payment status (O for open, PP for partial payment, and C for closed), and payment amount.<br><br/>**Posting Info**: Displays the vendor number, vendor name, cost center, cost object, user ID, and payment amount.|  

 At the end of the report, the number of processed payments is displayed.  

## Related information

[Making Payments](../../payables-make-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
