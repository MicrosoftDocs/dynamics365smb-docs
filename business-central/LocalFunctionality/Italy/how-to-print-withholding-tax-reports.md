---
title: Print Withholding Tax Reports in the Italian Version
description: Learn how to print the Italian Withholding Taxes report in Business Central and understand how final printing updates payment records and paid status.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: withholding tax, print withholding tax reports, Italian version
ms.search.form: 12103
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Print withholding tax reports in the Italian version

The **Withholding Taxes** report displays a list of withholding taxes that are payable to the Italian government.  

## Print a withholding tax report

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Withholding Taxes**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Reference Month**|Enter the month of the withholding tax period in numeric format.|
    |**Reference Year**|Enter the year of the withholding tax period in numeric format.|
    |**Print Details**|Select if you want to show all detailed information about withholding tax transactions.|
    |**Final Printing**|Select for a final run. When you print rather than preview, the report creates withholding tax payment records for nonzero payable amounts and marks the processed withholding entries as **Paid**.|

1. Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen.  

> [!IMPORTANT]
> **Final Printing** changes the withholding records when you print the report. Preview doesn't perform those updates. Marking entries as paid in this report doesn't transfer funds to the tax authority.

## Related information

[Report VAT to Tax Authorities](../../finance-how-report-vat.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
