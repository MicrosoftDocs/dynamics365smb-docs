---
title: Combine Automatic and Manual Flushing
description: Walkthrough for a production planner at CONTOSO, who wants to combine automatic and manual flushing.
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Walkthrough: Combine Automatic and Manual Flushing

Intro

## Scenario

You are the production planner at CONTOSO. You must create a new production order for ten units of item SP-SCM1004, AutoDrip. Some components and operations will be forward flushed, others backward flushed based on different conditions.

## Steps

1. Create a firm planned production order for five units of item SP-SCM1004, AutoDrip.

2. Release the production order.

    1. Choose **Change Status** action.

    2. On the request message, set the **New Status** field to Released, and then click **Yes**. A message that has a status bar appears and references automatic consumption. This is followed by a confirmation message that the order is changed to an order with a status of Released. Note the No. of the Released Production Order.

    3. Click **OK** to close the confirmation message.

3. Review the item and capacity ledger entries for the production order.

    1. In the Tell Me window, type "Released Production Order", and then select the related link.

    2. Locate the production order with 5 units of the AutoDrip.

    3. Choose **Item Ledger Entries** action. Note that item SP-BOM1305 Screw Hex M3, Zink is flushed immediately in whole Expected Quantity. Close Item Ledger Entries window.

    4. Choose **Capacity Ledger Entries** action. Note that Body assembly operations entry was also completed at moment when order was released. Close Capacity Ledger Entries window.

4. You can manually flush component items by using the consumption or production journal. Manual flushing allows you to adjust quantity before posting. For example, if additional quantity is needed to cover low quality raw materials.

    1. In the **Tell Me** window, type "Consumption Journal", and then select the related link.

    2. Choose **Calc. Consumption** action.

    3. On the **Production Order** FastTab of the **Calc. Consumption** request page, define filter for specific order in the **Order No.** field and choose **OK**. After the batch job request page closes, notice that the **Consumption Journal** page populates with the components that require manual consumption.

    4. Choose **Post** action. Close the consumption journal.

5. Manually register output for Electrical wiring. You need manually enter Setup and Run Time. You can also specify the actually produced quantity and scrap. Enter **six** as output quantity and **two** as scrap quantity. Post output.

    1. In the **Tell Me** window, type "Output Journal", and then select the related link.

    2. On the **Output Journal** page create new journal line.

    3. In the Order No. field select the order.

    4. Choose **Explode Routing** action. Notice that the **Output Journal** page populates with the operation line only for Electrical wiring.

    5. Type 10 into the **Run Time** field.

    6. Change the **Quantity** field from 5 to 3.

    7. Choose **Post**. Close the consumption journal.

6. Review the item ledger entries for the production order.

    1. Choose **Item Ledger Entries** action, and notice that the item SP-BOM1302, Control panel display is posted with Qty 3, based on actual output, while SP-BOM1303, Button posted in whole expected quantity. Close Item Ledger Entries window.

7. Finish the production order.

    1. Choose **Change Status** action.
    2. On the request message, set the **New Status** field to Finished, and then click **Yes**. 

    A message that has a status bar appears and references automatic consumption. This is followed by a confirmation message that the order is changed to an order with a status of Finished. Finished Production Order has the same No as Released.
   3. Click **OK** to close the confirmation message.

8. Review the item and capacity ledger entries for the production order again.

    1. Choose **Capacity Ledger Entries** action. Note that Packing operations entry was completed at moment when order was released. The produced (output) quantity is 5, regardless of output for previous step. Close Capacity Ledger Entries window.

    2. Choose **Item Ledger Entries** action. Note that quantity in item ledger entry of type output is equal to output quantity in the Capacity Ledger Entry. Consumed quantity of SP-BOM1301, Housing AutoDrip, and SP-BOM1304, Stainless still thermal carafe is 5 for both is because expected output and actual output are equal. Close Item Ledger Entries window.


