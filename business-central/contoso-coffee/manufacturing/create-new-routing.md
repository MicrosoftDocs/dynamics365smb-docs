---
title: Create a New Production Routing
description: Learn how to use Contoso Coffee demo data to manually create a production routing with two work center operations in Business Central.
ms.date: 11/12/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Create a new production routing

In this article, we take you through the steps to use the Contoso Coffee demo data to manually set up a new production routing in [!INCLUDE [prod_short](../../includes/prod_short.md)].  

## Scenario for the New Path routing

Oscar, the process engineer, at Contoso Coffee, decides to create a new routing with the name *New Path*. Because this routing is unlike any other routing at Contoso Coffee, Oscar must manually enter all of the information for the routing.  

## Create and certify the production routing

1. Create the routing header.  

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **routings**, and then choose the related link.

    1. Choose the **New** action, and then fill in the fields as described in the following table.

        |Field  |Value  |
        |---------|---------|
        |**No.** |1099|
        |**Description** |New Path|

1. Create the routing lines.

    1. On the **Lines** FastTab, add a new line, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**Operation No.** |10|
        |**Type** |Work Center|
        |**No.** |100|
        |**Setup Time** |20|
        |**Run Time** |15|

    1. Add a new line, and then fill in the fields as described in the following table.

        |Field  |Value  |
        |---------|---------|
        |**Operation No.** |20|
        |**Type** |Work Center|
        |**No.** |200|
        |**Setup Time** |30|
        |**Run Time** |5|

1. Certify the routing.

    1. In the **Status** field, choose **Certified**.

The new routing is now set up.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
