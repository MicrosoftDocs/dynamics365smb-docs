---
title: Use Order Planning to Create and Reserve Supply
description: Walkthrough to learn how to use order planning to create the required production order for the supply in Business Central.
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Walkthrough: Use Order Planning to Create and Reserve Supply

Intro

## Scenario

You are the production planner at CONTOSO. Unknown to you, Susan, the order processor at CONTOSO, has just entered a sales order for 100 units of item 1001, Touring Bicycle, due on February 05, 2014. The order is from customer 10000, The Canon Group PLC. You become aware of this demand when you run your weekly **Calculate Plan** function in order planning. You use order planning to create the required production order for the supply. Because you are creating the production order to fulfill the requirements of a specific sales order, you decide to reserve the output of the production order on behalf of the sales order.

## Steps

1. Create the new released production order for 100 units of item SP-SCM1009, Airpot.

    1. In the **Tell Me** window, type "released prod. order", and then select the related link.

    2. Create a new Released Prod. Order.

    3. In the Source No. field, type "SP-SCM1009" to select the Airpot.

    4. In **Quantity** field, type "100".

    5. Choose **Refresh Production Order** action.

    6. Note the **No.** of the released production order.

2. Open the **Order Planning** page and calculate a new plan.

    1. Choose **Planning** action.

    2. On the **Order Planning** page choose **Calculate Plan** action.

    3. Scroll down to the demand line representing released production order created earlier.

    4. Expand lines to view the details for the demand line. Confirm that it is a suggestion for a production order of 100 units of item 1001.

3. Create the new production order for 100 units of item SP-BOM2000, Reservoir Assy., and reserve the output of this production order on behalf of the related parent order.

    1. Select the check box in the **Reserve** field on the demand line for the 100 units of item SP-BOM2000.

    2. Choose **Make Orders** action.

    3. In the **Make Orders for** field select The Active Line.

    4. In the **Create Production Order** field, select Firm Planned.

    5. Click **OK** to create the production order.

    6. On the **Order Planning** page, confirm that the demand line for the 100 units of item 1001 is removed.


