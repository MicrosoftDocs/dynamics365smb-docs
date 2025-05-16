---
title: Create a New Routing 
description: Walkthrough to learn how to enter all of the information for a new routing manually in Business Central.
ms.date: 04/01/2022
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---
# Walkthrough: Create a New Routing

In this article, we take you through the steps to use the Contoso Coffee demo data to manually set up a new production routing in [!INCLUDE [prod_short](../../includes/prod_short.md)].  

## Scenario

Oscar, the process engineer, at Contoso Coffee, decides to create a new routing with the name *New Path*. Because this routing is unlike any other routing at Contoso Coffee, Oscar must manually enter all of the information for the routing.  

## Steps

1. Create the routing header.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **routings**, and then choose the related link.  

    2. Choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**No.** |1099|
        |**Description** |New Path|
2. Create the routing lines.

    1. On the **Lines** FastTab, add a new line, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**Operation No.** |10|
        |**Type** |Work Center|
        |**No.** |100|
        |**Setup Time** |20|
        |**Run Time** |15|

    2. Add a new line, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**Operation No.** |20|
        |**Type** |Work Center|
        |**No.** |200|
        |**Setup Time** |30|
        |**Run Time** |5|
3. Certify the routing.

    1.In the **Status** field, choose *Certified*.  

The new routing is now set up.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
