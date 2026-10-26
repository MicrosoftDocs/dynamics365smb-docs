---
title: Create Recurring Orders in the Norwegian Version [NO]
description: Create sales orders from Norwegian recurring blanket orders in Business Central, using a processing date and the option to create only the latest order.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: recurring orders, create recurring orders, Norwegian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Create recurring orders in the Norwegian version

The create recurring orders process finds all of the recurring orders based on the options selected on the **Create Recurring Orders** page and creates the new sales orders. This is a periodic activity that you must run regularly.  

The process skips blanket orders dated after the processing date, orders outside the recurring group's starting and closing dates, and orders with **Deactivate recurrence** selected.

## Create recurring orders  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Create Recurring Orders**, and then choose the related link.  
1. On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Processing Date**|Enter the date to process the blanket orders.|  
    |**Create only latest**|Select to create only the latest recurring order for the blanket orders processed. This option overrides the equivalent option for the recurring group.|

1. Choose the **OK** button.  

## Related information

- [Recurring Orders](recurring-orders.md)
- [Set Up Recurring Groups](how-to-set-up-recurring-groups.md)
- [Set Up Recurring Orders](how-to-set-up-recurring-orders.md)
- [Create Blanket Sales Orders](../../sales-how-to-create-blanket-sales-orders.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
