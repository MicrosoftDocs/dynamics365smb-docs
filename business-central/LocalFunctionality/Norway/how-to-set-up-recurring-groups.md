---
title: How to Set Up Recurring Groups
description: Learn how to use the Recurring Group Code field on the Blanket Sales Order page to define date formulas for creating sales orders based on date intervals.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: recurring group code, blanket sales order, define date formulas, create sales orders, Norwegian version
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up recurring groups

The **Recurring Group Code** field on the **Blanket Sales Order** page defines date formulas that can be used both as a template and to create sales orders based on date intervals. You must set up recurring groups before you can set up recurring orders.  

## Steps to set up recurring groups  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Recurring Groups**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Enter a code to identify the recurring group.|  
    |**Description**|Enter a description for the recurring group.|  
    |**Date formula**|Enter a date formula to calculate the time interval between orders.|  
    |**Create only the latest**|Select if you want only the latest recurring order created if the recurring group interval created by the **Date formula** is exceeded.<br> If the order date on the blanket sales order has exceeded more than one interval period, selecting this checkbox prevents how all orders are created, and only creates the latest order.|  
    |**Starting date**|Enter the first date of the recurring group.|  
    |**Closing date**|Enter the last date of the recurring group.|  

1. On the **Update** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Update Document Date**|Select one of the following options to update the document date:<br>- **Posting Date**: The document date is calculated using the posting date and the date formula specified in the **Document Date Formula** field.<br>- **Processing Date**: The document date is calculated using the processing date and the date formula specified in the **Document Date Formula** field.|  
    |**Document Date Formula**|Enter a date formula to calculate the document date on the order.|  
    |**Delivery Date Formula**|Enter a date formula to calculate the delivery date on the order.|  
    |**Update Price**|Select one of the following options for updating prices on new orders:<br>- **Fixed**: The price used on a new order is the same price that is specified in the blanket order.<br>- **Recalculate**: The price on a new order is recalculated to reflect the current price for the customer.<br>- **Reset**: The price on a new order is cleared to specify a new price.|  
    |**Update Number**|Select one of the following options to manage the quantity specified on the original order:<br>- **Constant**: The quantity on the blanket order remains unchanged. This enables you to make orders indefinitely from the blanket order.<br>- **Reduce**: The quantity on the blanket order is reduced with the quantity that is specified on the new order. The recurring order processing stops when the quantity specified on the blanket order is used on new orders.|  
    |**Reset Delivery**|Select to reset the delivery options for the recurring group.|  

1. Choose the **OK** button.  

## Related information

- [Recurring Orders](recurring-orders.md)
- [Set Up Recurring Orders](how-to-set-up-recurring-orders.md)
- [Create Recurring Orders](how-to-create-recurring-orders.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
