---
title: Create GST Liability
description: Learn how to create GST liability for subcontracting vendors in Business Central when materials aren't returned within the specified period.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, create GST liability, GST liability
ms.date: 06/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Create GST liability

If the subcontracting vendor doesn't return the material within specified period, you need to create the GST liability for the delivery challans that are liable to create the GST liability.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Create GST Liability**, and then choose the related link.
1. On the General FastTab, fill in the fields as described in the following table.
  
    |Field|Description|
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|Specify the Vendor No in this field.|
    |**Subcontracting Order No.**|Specify the Subcontracting Order No.|
    |**Delivery Challan Number**|Specify the Delivery Challan No. Program shows the Delivery Challan lines for which GST liability has to be created.|
    |**Liability Date**|Specify the Liability Date. The program shows the delivery challan lines where the last date is less than the liability date.|
    |**Liability Document No.**|Specify the document number, which is to be used for creating the GST liability in this field.|

1. On the Create GST Liability FastTab, following fields are shown.

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

1. Select **Create GST Liability**.
1. On the **GST Liability Line**, select **Post**.

## Related information

[Subcontracting Report](Subcontracting-Reports.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
