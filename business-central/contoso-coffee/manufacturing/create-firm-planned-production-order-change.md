---
title: Create a firm planned production order and change it
description: Walkthrough for a production planner at Contoso Coffee who wants to create a firm planned production order and then modify it.
ms.date: 05/19/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---

# Walkthrough: Create a firm planned production order and change it

This article takes you through the steps to use the Contoso Coffee demo data to work with production orders.  

## Scenario

Eduardo, the production planner at Contoso Coffee, must create a production order for 10 units of item **SP-SCM1009, Airpot**. The order must be due on April 28. Eduardo backward schedules the order and confirms that they can start the order on April 27.  

Shortly after the task is complete, Eduardo is asked to increase the order to 50 units. On doing so, backward scheduling pushes the order's start date to be too early. So Eduardo forward schedules the order from April 23 in order to determine a more realistic finish date.  

## Steps

1. Create the initial production order for 10 units of the item **SP-SCM1009, Airpot**.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **firm planned prod. orders**, and then choose the related link.  
    2. Choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**Source Type** |Item|
        |**Source No.** |SP-SCM1009|
        |**Quantity** |10|
        |**Due Date**|April 28  |

    3. Choose the **Refresh Production Order** action.  
    4. On the **Refresh Production Order** page, accept all defaults, and then choose the **OK** button to start the process.  

        In the current setup, this process uses backwards scheduling. In the new line on the production order, the starting date is April 26.  

2. Change the production order's quantity to 50 units and schedule the order.  

    1. On the **Lines** FastTab of the **Production BOM**, select the recently added line, and then, in the **Quantity** field, enter *50*.  

    The start date is now pushed to April 20. This date isn't acceptable for Eduardo.

3. Trigger a forward scheduling of the production order.

    1. On the **Schedule** FastTab, set the **Starting Date** field to *April 23*.

    The starting for the order is now April 23, and the ending date is April 30. The due date for the order is set one day later.

> [!NOTE]
> Based on the year, April 23 might be during a weekend. In such cases, the start date is automatically shifted to the next working day. For example, April 25. The ending date and due date might also change for the same reason.

The new production order is now set up, and Eduardo's requirements are met.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
