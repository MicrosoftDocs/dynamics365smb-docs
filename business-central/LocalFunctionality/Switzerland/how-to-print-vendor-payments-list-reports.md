---
title: Print Vendor Payments List Reports [CH]
description: Learn how to generate the Vendor Payments List report, which provides a detailed overview of payments for each vendor, sorted either chronologically or by vendor grouping.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: vendor payments list, vendor payments report, Swiss version
ms.date: 04/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Print Vendor Payments List reports in the Swiss version

The **Vendor Payments List** report provides a list of payments for each vendor. The report can sort payments chronologically or grouped by vendor.  

> [!NOTE]
> The **Vendor Payments List** report is available in the following markets: Austria, Germany, Switzerland.

## Print the Vendor Payments List report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Payments List**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sorting**|Specifies the sort order. You can sort by vendor or chronologically. If you sort by vendor, you'll see a subtotal for each vendor. If you sort chronologically, you won't see subtotals.|  
    |**Layout**|Specifies the layout of the report.<br><br/> The results can be displayed in the following layouts:<br><br/>- **Standard**: Displays the vendor number and vendor name, together with posting details, such as the document number and the amount in local currency.<br><br/>- **FCY Amounts**: Displays the vendor number, vendor name, document number, payment status (O for open, PP for partial payment, and C for closed), and payment amount.<br><br/>- **Posting Info**: Displays the vendor number, vendor name, cost center, cost object, user ID, and payment amount.|  

 At the end of the report, the number of processed payments is displayed.  

## Related information

[Making Payments](../../payables-make-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
