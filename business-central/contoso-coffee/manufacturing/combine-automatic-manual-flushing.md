---
title: Combine Automatic and Manual Flushing
description: Walkthrough for a production planner at Contoso Coffee, who wants to combine automatic and manual flushing.
ms.date: 04/01/2022
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
---

# Walkthrough: Combine Automatic and Manual Flushing

In this article, we take you through the steps to use the Contoso Coffee demo data in flushing.  

## Scenario

You are the production planner at Contoso Coffee. You must create a new production order for ten units of item SP-SCM1004, AutoDrip. Some components and operations will be forward flushed, others backward flushed based on different conditions.

## Steps

> [Note!]
> Remember to adjust inventory by posting Item Journal with opening balances.

1. Create a firm planned production order for five units of the item **SP-SCM1004, AutoDrip** on *MAIN* location. For guidance, see [Walkthrough: Create a Firm Planned Production Order and Change It](create-firm-planned-production-order-change.md).  

2. Release the production order.

    1. Choose the **Change Status** action.  

    2. In the page that appears, set the **New Status** field to *Released*, and then choose the **Yes** button.  

        A message that has a status bar appears and references automatic consumption. This is followed by a confirmation message that the order is changed to have the status *Released*.  

    3. Choose the **OK** button to close the confirmation message.

3. Review the item and capacity ledger entries for the production order.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Order**, and then choose the related link.  

    2. Open the production order with the 5 units of the AutoDrip coffee machine.  

    3. Choose the **Item Ledger Entries** action.  

        The item **SP-BOM1305 Screw Hex M3 Zink** is flushed immediately with the full expected quantity. Close the **Item Ledger Entries** page.  

    4. Choose the **Capacity Ledger Entries** action.  Note that a body assembly operations entry was also completed at moment when order was released. Close the **Capacity Ledger Entries** window.

    You can manually flush component items by using the consumption or production journal. Manual flushing allows you to adjust quantity before posting. For example, if additional quantity is needed to cover low quality raw materials.
4. Flush components manually.  
    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Consumption Journal**, and then choose the related link.  

    2. Choose the **Calc. Consumption** action.  

    3. In the **Calc. Consumption** request page, on the **Production Order** FastTab, define a filter for the specific order in the **Order No.** field, and then choose the **OK** button. After the batch job request page closes, notice that the **Consumption Journal** page populates with the components that require manual consumption.

    4. Choose **Post** action. Close the consumption journal.

5. Manually register output for electrical wiring.  

    You must manually fill in the **Setup Time** and **Run Time** fields. You can also specify the actually produced quantity and scrap. Enter *3* as the output quantity and post the output.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.  

    2. In the **Output Journal** page, create a new journal line.  

    3. In the **Order No.** field, specify the order.  

    4. Choose the **Explode Routing** action.  

        The **Output Journal** page populates with the operation line only for electrical wiring.

    5. Set the **Run Time** field to *10*.  

    6. Change the **Quantity** field from *5* to *3*.

    7. Choose **Post**.  
    8. Close the output journal.

6. Review the item ledger entries for the production order.

    1. In the page for the production order, choose the **Item Ledger Entries** action.  

    The item **SP-BOM1302, Control panel display** is posted with a quantity of *3*, based on the actual output, while **SP-BOM1303, Button** is posted with the full expected quantity. Close the **Item Ledger Entries** page.

7. Finish the production order.  

    1. Choose the **Change Status** action.
    2. In the page that appears, set the **New Status** field to *Finished*, and then choose the **Yes** button.  

        A message  displays with a status bar that reflects the automatic consumption. This is followed by a confirmation message that the order is changed to an order with the status *Finished*. The finished production order has the same number as it had as with the status *Released*.
    3. Choose the **OK** button to close the confirmation message.

8. Review the item and capacity ledger entries for the production order again.

    1. Choose the **Capacity Ledger Entries** action.  

        The packing operations entry was completed at the moment when the order was released. The produced (output) quantity is *5*, regardless of the output of the previous step. Close the **Capacity Ledger Entries** page.

    2. Choose the **Item Ledger Entries** action.  

        The quantity in the item ledger entry of type *Output* is equal to the output quantity in the capacity ledger entry. The consumed quantity of **SP-BOM1301, Housing AutoDrip**, and **SP-BOM1304, Stainless still thermal carafe** is 5 for both because the expected output and the actual output are the same. 

    3. Close the **Item Ledger Entries** page.  

That's it for manual and automatic flushing of components.

## Related information

[Flush Components According to Operation Output](../../production-how-to-flush-components-according-to-operation-output.md)  
[Introduction to Contoso Coffee Demo Data](contoso-coffee-manufacturing-intro.md)  
