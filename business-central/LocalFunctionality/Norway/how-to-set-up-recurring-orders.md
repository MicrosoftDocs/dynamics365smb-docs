---
title: How to Set Up Recurring Orders
description: Learn how to set up recurring orders by adding a recurring group to a blanket sales order.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: recurring order, blanket sales order, recurring group, Norwegian version
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up recurring orders

After you create a recurring group, you can set up recurring orders on the blanket sales order by adding the group to the order. For more information, see [Create Blanket Sales Orders](how-to-set-up-recurring-groups.md).  

## Steps to set up a recurring order  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Blanket Sales Orders**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Order Date**|Enter the order date. The order date is used when you create new recurring orders. Orders with an order date on or before the processing date are processed.|  
    |**Recurring Group Code**|Enter the recurring group code for the recurring group. When a blanket order contains a recurring group code, the blanket order is available as a recurring order.|  

1. On the **Lines** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Quantity**|Enter the quantity for the blanket order.|  
    |**Qty. to Ship**|Enter the quantity to ship. This quantity is used when you create new orders as recurring orders.|  

1. Choose the **OK** button.  

## Related information

- [Recurring Orders](recurring-orders.md)
- [Set Up Recurring Groups](how-to-set-up-recurring-groups.md)
- [Create Recurring Orders](how-to-create-recurring-orders.md)
- [Work with Blanket Sales Orders](../../sales-how-to-create-blanket-sales-orders.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
