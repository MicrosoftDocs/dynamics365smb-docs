---
title: Create a Firm Planned Production Order and Change It
description: Walkthrough for a production planner at Contoso Coffee who wants to create a firm planned production order and then modify it.
ms.date: 11/12/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Create a firm planned production order and change it

This article takes you through the steps to use the Contoso Coffee demo data to work with production orders.  

## Scenario for scheduling an Airpot production order

Eduardo, the production planner at Contoso Coffee, must create a production order for 10 units of item **SP-SCM1009, Airpot**. The order must be due on April 28. Eduardo backward schedules the order and reviews the calculated starting date.

Shortly after the task is complete, Eduardo is asked to increase the order to 50 units. On doing so, backward scheduling pushes the order's start date to be too early. So Eduardo forward schedules the order from April 23 in order to determine a more realistic finish date.  

## Create and reschedule the production order

Before you begin, [generate the Manufacturing demo data](contoso-coffee-manufacturing-intro.md#set-up-contoso-coffee-manufacturing-data). The walkthrough uses item **SP-SCM1009**, its default routing **SP-SCM1009-SERIAL**, and the default manufacturing location **MAIN**. Use dates in the configured starting year.

1. Create the initial production order for 10 units of the item **SP-SCM1009, Airpot**.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **firm planned prod. orders**, and then choose the related link.
    1. Choose the **New** action, and then fill in the fields as described in the following table.

        |Field  |Value  |
        |---------|---------|
        |**Source Type** |Item|
        |**Source No.** |SP-SCM1009|
        |**Quantity** |10|
        |**Location Code**|MAIN|
        |**Due Date**|April 28  |

    1. Choose the **Refresh Production Order** action.
    1. On the **Refresh Production Order** page, accept all defaults, and then choose the **OK** button to start the process.

        This process uses backward scheduling by default. Review the calculated starting date on the production order line. The result depends on the year, the work and machine center calendars, and the routing setup.

1. Change the production order's quantity to 50 units and schedule the order.

    1. On the **Lines** FastTab of the **Firm Planned Prod. Order**, select the production order line, and then, in the **Quantity** field, enter **50**.

    Review the recalculated starting date. The larger quantity requires more production time, so backward scheduling can move the starting date earlier.

1. Trigger a forward scheduling of the production order.

    1. On the **Schedule** FastTab, set the **Starting Date** field to *April 23*.

    Review the calculated ending date and due date. Use the dates calculated for your demo company's calendars rather than expecting fixed results for April 30 and May 1.

> [!NOTE]
> Based on the year, April 23 might be during a weekend. In such cases, the start date is automatically shifted to the next working day. For example, April 25. The ending date and due date might also change for the same reason.

The new production order is now set up, and Eduardo's requirements are met.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
