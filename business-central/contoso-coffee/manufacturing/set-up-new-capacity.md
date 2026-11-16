---
title: Set Up New Manufacturing Capacity
description: Learn how to use Contoso Coffee demo data to set up a work center, a machine center, and a single-shift capacity calendar in Business Central.
ms.date: 11/12/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Set up new manufacturing capacity

In this article, we take you through the steps to use the Contoso Coffee demo data in how you manage capacity.  

## Scenario for the testing work center

You are the production planner at Contoso Coffee. In response to changes on the shop floor, you must set up a new work center, Test Department. The new work center has one machine center, Testing. The new centers must have a capacity calendar for a single shift from 08:00:00 AM to 4:00:00 PM, Monday to Friday.  

## Set up the centers and calculate capacity

1. Set up the work center.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **work centers**, and then choose the related link.

    1. Choose the **New** action, and then fill in the fields as described in the following table.

        |Field  |Value  |
        |---------|---------|
        |**No.** |700|
        |**Name** |Test Department|
        |**Work Center Group Code** |1, Production department|
        |**Direct Unit Cost**|3.25|
        |**Unit Cost Calculation**|Time|
        |**Flushing Method**|Manual|
        |**Gen. Prod. Posting Group**|MANUFACT<br><br>Note that this selection depends on your accounting setup and country/region.|
        |**Unit of Measure Code** |MINUTES|
        |**Capacity** |1|
        |**Efficiency** |90|
        |**Shop Calendar Code** |One shift|

        In the **Shop Calendar Code** field, select the demo calendar **One shift**, which defines working hours from 8:00 AM to 4:00 PM, Monday to Friday.

    1. Close the work center card.

1. Set up the machine center.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **machine centers**, and then choose the related link.

    1. Choose the **New** action, and then fill in the fields as described in the following table.

        |Field  |Value  |
        |---------|---------|
        |**No.** |760|
        |**Name** |Testing|
        |**Work Center No.** |700, Test department|
        |**Direct Unit Cost**|3.25|
        |**Flushing Method**|Manual|
        |**Gen. Prod. Posting Group**|MANUFACT<br><br>Note that this selection depends on your accounting setup and country/region.|
        |**Capacity** |1|
        |**Efficiency** |90|
    1. Expand the **Routing Setup** FastTab, and then, in the **Setup Time** field, enter *10*.

1. Calculate the machine center capacity calendar.

    1. Choose the **Calendar** action.  

    1. In the **Machine Center Calendar** page, on the **Matrix Options** FastTab, set the **View by** field to *Month*.

    1. Choose the **Show Matrix** action.

    1. On the **Machine Center Calendar Matrix** page, choose the **Calculate** action.

    1. In the **Calc. Machine Center Calendar** page, on the **Options** FastTab, set the **Starting Date** field to *January 01*.

    1. Set the **Ending Date** field to December 31.

    1. On the **Machine Center** FastTab, in the **No.** filter field, select *760, Testing*.

    1. Choose the **OK** button. After the batch job finishes, it returns you to the **Machine Center Calendar Matrix** page.

    1. Choose the **Refresh** action.

    1. On the line for machine center 760, Testing, drill down into the value in the January column.

On the **Calendar Entries** page, the daily capacity entries in the **Capacity (Total)** field are for 480 minutes. This reflects one eight-hour shift for each work day. Also, the **Capacity (Effective)** field shows 432 minutes. This reflects the 90 percent efficiency rate that you assigned to the machine center.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
