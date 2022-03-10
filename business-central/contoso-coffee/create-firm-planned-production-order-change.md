---
title: Create a Firm Planned Production Order and Change It
description: Walkthrough for a production planner at CONTOSO who wants to create a firm planned production order and then change It
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Walkthrough: Create a Firm Planned Production Order and Change It

Intro

## Scenario

Eduardo, the production planner at CONTOSO, must create a new production order for 10 units of item SP-SCM1009, Airpot, due on April 28. He backward schedules this and confirms that he can start the order on April 27.

Shortly after he finishes this task, he is asked to increase the order to 50 units. When he does this, the backward scheduling functionality pushes the order start date too early. So he forward schedules the order from April 23 in order to determine a more realistic finish date.

## Steps

1. Create the initial production order for 10 units of item SP-SCM1009, Airpot.

    1. In the **Tell Me** window, type "firm planned prod. orders", and then select the related link.

    2. Create a new Firm Planned Prod. Order.

    3. In the Source No. field, type "SP-SCM1009" to select the Airpot.

    4. In **Quantity** field, type "10".

    5. Set the **Due Date** field to April 28.

    6. Choose **Refresh Production Order** action.

    7. On the **Refresh Production Order** request page, accept all defaults, and then click **OK** to start the batch job. When the batch job is finished, and you return to the production order card, notice that the starting date for the production order is April 26.

2. Change the production order to 50 units and schedule the order.

    1. On the **Lines** FastTab of the **Production BOM**, select line and in **Quantity** field, type "50". Notice that the start date has now been pushed back to April 20. This is nonacceptable date.

3. Change the start date to April 23, to trigger a forward scheduling of the production order.

    1. Expand the **Schedule** FastTab on the production order card.

    2. On the **Schedule** FastTab, set the **Starting Date** field to April 23.

    3. Notice that the starting for the order is now April 25, and that the ending date is May 2. The due date for the order is set one day later, on May 3. Eduardo now knows that it will take until May 3 to deliver the increased order.

> [!NOTE]
> Scheduling an order by changing its starting or ending date does not require the **Refresh Production Order** batch job because all dates recalculate automatically.


