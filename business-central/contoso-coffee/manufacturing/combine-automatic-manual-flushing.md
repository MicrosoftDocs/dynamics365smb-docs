---
title: Combine Automatic and Manual Flushing
description: Walkthrough for a production planner at Contoso Coffee, who wants to combine automatic and manual flushing.
ms.date: 05/19/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.custom: bap-template
---

# Walkthrough: Combine automatic and manual flushing

This article takes you through the steps to use the Contoso Coffee demo data in flushing.  

## Scenario

You're the production planner at Contoso Coffee. You must create a new production order for five units of item SP-SCM1004, AutoDrip. Some components and operations are forward flushed, others backward flushed based on different conditions.

## Steps

1. Create a firm planned production order for five units of the item **SP-SCM1004, AutoDrip** on *MAIN* location. For guidance, see [Walkthrough: Create a Firm Planned Production Order and Change It](create-firm-planned-production-order-change.md).  
2. Release the production order.

    1. Choose the **Change Status** action.  
    2. In the page that appears, set the **New Status** field to *Released*, and then choose the **Yes** button.  

        A message that has a status bar appears and references automatic consumption. This message is followed by a confirmation message that the order is changed to have the status *Released*.  

    3. Choose the **OK** button to close the confirmation message.

3. Review the item and capacity ledger entries for the production order.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Order**, and then choose the related link.  
    2. Open the production order with the 5 units of the AutoDrip coffee machine.  
    3. Choose the **Item Ledger Entries** action.  

        The item **SP-BOM1305 Screw Hex M3 Zink** is flushed immediately with the full expected quantity. Close the **Item Ledger Entries** page.  

    4. Choose the **Capacity Ledger Entries** action. A body assembly operations entry was also completed when the order was released. Close the **Capacity Ledger Entries** page.

    You can manually flush component items by using a consumption or production journal. Manual flushing allows you to adjust quantity before posting. For example, if more quantity is needed to cover a low quality of raw materials.
4. Flush components manually.  
    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Consumption Journal**, and then choose the related link.  

    2. Choose the **Calc. Consumption** action.  

    3. In the **Calc. Consumption** request page, on the **Production Order** FastTab, define a filter for the specific order in the **Order No.** field, and then choose the **OK** button. After the batch job request page closes, the **Consumption Journal** page shows the components that require manual consumption.

    4. Choose the **Post** action. Close the consumption journal.

5. Manually register output for electrical wiring.  

    You must manually fill in the **Run Time** field. You can also specify the quantity and scrap that was produced. Enter **3** as the output quantity and post the output.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.  
    2. On the **Output Journal** page, create a new journal line.  
    3. In the **Order No.** field, specify the order.  
    4. Choose the **Explode Routing** action.  

        The **Output Journal** page shows the operation line only for electrical wiring.

    5. In the **Run Time** field, enter **10**.  
    6. Change the **Quantity** field from **5** to **3**.

    7. Choose **Post**.  
    8. Close the output journal.

6. Review the item ledger entries for the production order.

    1. On the page for the production order, choose the **Item Ledger Entries** action.  

    The item **SP-BOM1302, Control panel display** is posted with a quantity of **3**, based on the actual output. **SP-BOM1303, Button** is posted with the full expected quantity. Close the **Item Ledger Entries** page.

7. Finish the production order.  

    1. Choose the **Change Status** action.
    2. In the page that appears, choose **Finished** in the **New Status** field, and then choose the **Yes** button.  

        A message displays with a status bar that reflects the automatic consumption. This message is followed by a confirmation message that the order is changed to an order with the status **Finished**. The finished production order has the same number as it had as with the status **Released**.
    3. Choose the **OK** button to close the confirmation message.

8. Review the item and capacity ledger entries for the production order again.

    1. Choose the **Capacity Ledger Entries** action.  

        The packing operations entry was completed when the order was finished. The produced (output) quantity is **5**, regardless of the output of the previous step. Close the **Capacity Ledger Entries** page.

    2. Choose the **Item Ledger Entries** action.  

        The quantity in the item ledger entry of type **Output** is equal to the output quantity in the capacity ledger entry. The consumed quantity of **SP-BOM1301, Housing AutoDrip**, and **SP-BOM1304, Stainless still thermal carafe** is **5** for both because the expected output and the actual output are the same.

    3. Close the **Item Ledger Entries** page.  

That's it for manual and automatic flushing of components.

## Related information

[Flush Components According to Operation Output](../../production-how-to-flush-components-according-to-operation-output.md)  
[Introduction to Contoso Coffee Demo Data](contoso-coffee-manufacturing-intro.md)  
