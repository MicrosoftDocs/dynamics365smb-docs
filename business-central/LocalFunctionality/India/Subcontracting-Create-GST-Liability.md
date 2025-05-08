---
title: Create GST Liability
description: Create GST Liability

    
author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Create GST Liability


If the subcontracting vendor does not return the material within specified period, you need to create the GST liability for the delivery challans that are liable to create the GST liability.

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Create GST Liability**, and then choose the related link. 
2. On the General FastTab, fill in the fields as described in the following table.
  
    |Field|Description| 
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|Specify the Vendor No in this field.|
    |**Subcontracting Order No.**|Specify the Subcontracting Order No.|
    |**Delivery Challan Number**|Specify the Delivery Challan No. Program will show the Delivery Challan lines for which GST liability has to be created.|
    |**Liability Date**|Sepcify the Liability Date. The program will show the delivery challan lines where the last date is less than the liability date.|
    |**Liability Document No.**|Specify the document number which is to be used for creating the GST liability in this field.|

3. On the Create GST Liability FastTab, following fields will be shown.

    |Field|Description| 
    |---------------------------------|---------------------------------------|  
    |**Vendor No.**|The program will show the vendor number of delivery challan line. This field is non-editable.|
    |**Delivery Challan No.**|The program will show the delivery challan number of delivery challan line. This field is non-editable.|
    |**Item No.**|The program will show the item number of delivery challan line. This field is non-editable.|
    |**Description**|The program will show the description of item number. This field is non-editable.|
    |**Quantity**|The program will show the quantity of delivery challan line. This field is non-editable.|
    |**Remaining Quantity**|The program will show the remaining quantity of delivery challan line. This field is non-editable.|
    |**Posting Date**|The program will show the posting date of delivery challan line. This field is non-editable.|
    |**Last Date**|The program will show the last date of delivery challan line. This field is non-editable.|
    |**Job Work Return Period**|The program will show the job work return period of delivery challan line. This field is non-editable.|

4.	Click on **Create GST Liability**.
5.	On the **GST Liability Line**, click **Post**.





## Related information 
[Subcontracting Report](Subcontracting-Reports.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
