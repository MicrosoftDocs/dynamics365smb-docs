---
title: Print Vendor Payments List Reports in the Swiss Version [CH]
description: Print a vendor payments list in the Swiss version of Business Central, sorted by vendor or chronologically, with local or foreign currency amounts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: vendor payments list, vendor payments report, Swiss version
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print vendor payments list reports in the Swiss version

The **Vendor Payments List** report provides a list of payments for each vendor. The report can sort payments chronologically or grouped by vendor.  

> [!NOTE]
> The **Vendor Payments List** report is available in the following markets: Austria, Germany, Switzerland.

## Print the vendor payments list report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendor Payments List**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Sorting**|Specifies the sort order. You can sort by vendor or chronologically. If you sort by vendor, you'll see a subtotal for each vendor. If you sort chronologically, you won't see subtotals.|  
    |**Layout**|Specifies the layout of the report.<br><br/> The results can be displayed in the following layouts:<br><br/>- **Standard**: Displays the vendor number and vendor name, together with posting details, such as the document number and the amount in local currency.<br><br/>- **FCY Amounts**: Displays the vendor number, vendor name, document number, payment status (O for open, PP for partial payment, and C for closed), and payment amount.<br><br/>- **Posting Info**: Displays the vendor number, vendor name, cost center, cost object, user ID, and payment amount.|  

 At the end of the report, the number of processed payments is displayed.  

## Related information

[Making Payments](../../payables-make-payments.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
