---
title: Set Up New Capacity 
description: Walkthrough to learn how to set up a new work center with a capacity calendar for a single shift in Business Central.
ms.date: 04/01/2022
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
---

# Walkthrough: Set Up New Capacity

In this article, we take you through the steps to use the Contoso Coffee demo data in how you manage capacity.  

## Scenario

You are the production planner at Contoso Coffee. In response to changes on the shop floor, you must set up a new work center, Test Department. The new work center has one machine center, Testing. The new centers must have a capacity calendar for a single shift from 08:00:00 AM to 4:00:00 PM, Monday to Friday.  

## Steps

1. Set up the work center.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **work centers**, and then choose the related link.  

    2. Choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**No.** |700|
        |**Name** |Test Department|
        |**Work Center Group Code** |1, Production department|
        |**Direct Unit Cost**|3.25|
        |**Unit Cost Calculation**|Time|
        |**Flushing Method**|Manual|
        |**Gen. Prod. Posting Group**|NO VAT</br></br>Note that this selection depends on your accounting setup and country/region.|
        |**Unit of Measure Code** |MINUTES|
        |**Capacity** |1|
        |**Efficiency** |90|
        |**Shop Calendar Code** |1|

        In the **Shop Calendar Code** field, the setting 1 means one shift from Monday to Friday.

    3. Close the work center card.

2. Set up the machine center.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **machine centers**, and then choose the related link.  

    2. Choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**No.** |760|
        |**Name** |Testing|
        |**Work Center No.** |700, Test department|
        |**Direct Unit Cost**|3.25|
        |**Flushing Method**|Manual|
        |**Gen. Prod. Posting Group**|NO VAT</br></br>Note that this selection depends on your accounting setup and country.|
        |**Capacity** |1|
        |**Efficiency** |90|
    3. Expand the **Routing Setup** FastTab, and then, in the **Setup Time** field, enter *10*.  

3. Calculate the machine center capacity calendar.  

    1. Choose the **Calendar** action.  

    2. In the **Machine Center Calendar** page, on the **Matrix Options** FastTab, set the **View by** field to *Month*.  

    3. Choose the **Show Matrix** action.  

    4. On the **Machine Center Calendar Matrix** page, choose the **Calculate** action.  

    5. In the **Calc. Machine Center Calendar** page, on the **Options** FastTab, set the **Starting Date** field to *January 01*.  

    6. Set the **Ending Date** field to December 31.  

    7. On the **Machine Center** FastTab, in the **No.** filter field, select *760, Testing*.  

    8. Choose the **OK** button. After the batch job finishes, it returns you to the **Machine Center Calendar Matrix** page.  

    9. Choose the **Refresh** action.  

    10. On the line for machine center 760, Testing, drill down into the value in the January column.  

On the **Calendar Entries** page, the daily capacity entries in the **Capacity (Total)** field are for 480 minutes. This reflects one eight-hour shift for each work day. Also, the **Capacity (Effective)** field shows 432 minutes. This reflects the 90 percent efficiency rate that you assigned to the machine center.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
