---
title: Use Order Planning to Create and Reserve Supply
description: Learn how to use Contoso Coffee demo data and order planning to create and reserve subassembly supply for a production order in Business Central.
ms.date: 11/12/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Use order planning to create and reserve supply

In this article, we take you through the steps to use the Contoso Coffee demo data in order planning.

## Scenario for planning subassembly supply

You are the production planner at Contoso Coffee. You created a production order for 100 units of the item **SP-SCM1009, Airpot**, and you want to plan subassemblies for this order. You use order planning to create the required production order for the supply. Because you are creating the production order to fulfill the requirements of a specific order, you decide to reserve the output of the production order.  

## Create and reserve the subassembly production order

1. Create the new released production order for 100 units of item **SP-SCM1009, Airpot**.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Released Production Order**, and then choose the related link.

    1. Choose the **New** action, and then fill in the fields as described in the following table.

        |Field  |Value  |
        |---------|---------|
        |**Source Type** |Item|
        |**Source No.** |SP-SCM1009|
        |**Quantity** |100|
    1. Choose the **Refresh Production Order** action.

    Note the number of the released production order.

1. Open the **Order Planning** page and calculate a new plan.

    1. Choose the **Planning** action.  

    1. On the **Order Planning** page, choose the **Calculate Plan** action.

    1. Scroll down to the demand line that represents the released production order that you created earlier.

    1. Expand the lines to view the details for the demand line. Confirm that it is a suggestion for a production order of 100 units of item **SP-BOM2000, Reservoir Assembly**.

1. Create a new production order for 100 units of item **SP-BOM2000, Reservoir Assembly**, and reserve the output of this production order on behalf of the related parent order.

    1. Select the check box in the **Reserve** field on the demand line for the 100 units of item SP-BOM2000.

    1. Choose the **Make Orders** action.

    1. Set the **Make Orders for** field to *The Active Line*.

    1. Set the **Create Production Order** field to *Firm Planned*.

    1. Choose the **OK** button to create the production order.

    1. On the **Order Planning** page, confirm that the demand line for the 100 units of item **SP-BOM2000** is removed.

That's it for order planning in [!INCLUDE [prod_short](../../includes/prod_short.md)].  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
[About Production Orders](../../production-about-production-orders.md)  

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
