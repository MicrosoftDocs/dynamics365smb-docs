---
title: Create GST Liability
description: Learn how to create GST liability for subcontracting vendors in Business Central when materials aren't returned within the specified period.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, create GST liability, GST liability
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create GST liability

Use **Create GST Liability** to prepare liability lines for eligible overdue delivery challans. The page shows lines with a positive remaining quantity, a nonzero total GST amount, no GST liability already created, **GST Credit** set to **Availment**, and **Exempted** cleared.

Before posting, configure the **GST Liability - Job Work** source code, **Sub-Con Interim Account** in **General Ledger Setup**, and **GST Liability Invoice** number series on the company location. Confirm the applicable tax requirements separately.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Create GST Liability**, and then choose the related link.
1. On the General FastTab, fill in the fields as described in the following table.
  
    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|Specify the Vendor No in this field.|
    |**Subcontracting Order No.**|Specify the Subcontracting Order No.|
    |**Delivery Challan No.**|Filter the delivery challan lines by challan number.|
    |**Liability Date**|Specify the Liability Date. The program shows the delivery challan lines where the last date is less than the liability date.|
    |**Liability Document No.**|Specify the document number, which is to be used for creating the GST liability in this field.|

1. Review the filtered lines. The following fields are read-only.

    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|The program shows the vendor number of delivery challan line. This field is noneditable.|
    |**Delivery Challan No.**|The program shows the delivery challan number of delivery challan line. This field is noneditable.|
    |**Item No.**|The program shows the item number of delivery challan line. This field is noneditable.|
    |**Description**|The program shows the description of item number. This field is noneditable.|
    |**Quantity**|The program shows the quantity of delivery challan line. This field is noneditable.|
    |**Remaining Quantity**|The program shows the remaining quantity of delivery challan line. This field is noneditable.|
    |**Posting Date**|The program shows the posting date of delivery challan line. This field is noneditable.|
    |**Last Date**|The program shows the last date of delivery challan line. This field is noneditable.|
    |**Job Work Return Period**|The program shows the job work return period of delivery challan line. This field is noneditable.|

1. Select **Create GST Liability**. **Liability Date** and **Liability Document No.** are required.
1. On the **GST Liability Line**, select **Post**.

Creation processes all lines in the current filters, not just the highlighted line. The GST base amount is calculated from the production order component unit cost and remaining quantity; a zero unit cost causes an error. A liability document number already used in posted liability lines can't be reused.

> [!WARNING]
> Creating liability lines clears existing unposted **GST Liability Line** records when eligible filtered challan lines exist. Finish or review outstanding liability work before creating another set.

## Related information

[Subcontracting Report](Subcontracting-Reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
