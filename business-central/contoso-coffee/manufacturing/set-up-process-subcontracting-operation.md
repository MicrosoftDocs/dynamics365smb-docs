---
title: Set up and Process a Subcontracting Operation
description: Walkthrough to learn how to set up and process a subcontracting operation in Business Central.
ms.date: 04/01/2022
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
---

# Set up and Process a Subcontracting Operation

In this article, we take you through the steps to use the Contoso Coffee demo data in subcontracting.

## Scenario

You are the production planner at Contoso Coffee. Due to capacity constraints, you plan to use a subcontractor to produce the item **SP-SCM1009, Airpot**.

Here, you create a new released production order for 12 units of item SP-SCM1009, Airpot, using Routing - SP-SCM1009-SUB-2. Use the subcontracting worksheet to generate a purchase order for the production, and then finish the operation by receiving and invoicing the purchase order.

## Steps

1. Create a new released production order for 12 units of item SP-SCM1009, Airpot.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Order**, and then choose the related link.  

    2. Choose the **New** action, and then fill in the fields as described in the following table.  

        |Field  |Value  |
        |---------|---------|
        |**Source Type** |Item|
        |**Source No.** |SP-SCM1009|
        |**Quantity** |100|
    3. Choose the **Refresh Production Order** action.  

2. Replace the routing to SP-SCM1009-SUB-2 in the production order line, and then refresh the production order but for routing only.  

    1. Add Production Routing No field to the Lines in the Released Production Order.<!--in code, this is marked as visible=false-->

    2. Change the **Routing No.** field from *SP-SCM1009-SERIAL* to *SP-SCM1009-SUB-2*.  

    3. Choose the **Refresh Production Order** action.  

    4. On the **Refresh Production Order** request page, clear the **Lines** and **Component Need** fields so that the task will run for Routing only, and then choose the **OK** button.

3. Use the subcontracting worksheet to generate a purchase order for the subcontracted operation on the production order that you created in step 2.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **subcontracting worksheets**, and then choose the related link.  

    2. Choose the **Calculate Subcontracts** action.

    3. Select the **Accept Action Message** field for the new line.

    4. Choose the **Carry Out Action Message** action.  

    5. On the **Carry Out Action Msg. – Req.** request page, accept all default values, and then choose the **OK** button.

    6. When the batch job finishes, choose the **OK** button to close the subcontracting worksheet.  

4. Receive and invoice the purchase order.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **purchase orders**, and then choose the related link.  

    2. On the **Purchase Orders** list, find the purchase order from the vendor 82000 Subcontractor.

    3. In the **Vendor Invoice No.** field, enter *542349*.

    4. On the **Lines** FastTab, select the line, and then set the **Direct Cost** field to *18*.

    5. Choose the **Post** action.  

    6. On the request message, choose the **Receive and Invoice** option.  

The output of item SP-SCM1009 Airpot is now registered.

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
