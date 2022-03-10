---
title: Set up and Process a Subcontracting Operation
description: Walkthrough to learn how to set up and process a subcontracting operation in Business Central.
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Set up and Process a Subcontracting Operation

Intro 

## Scenario

You are the production planner at CONTOSO. Due to capacity constraints you plan to use Subcontractor to produce SP-SCM1009, Airpot.

Create a new released production order for 12 units of item SP-SCM1009, Airpot, using Routing - SP-SCM1009-SUB-2. Use the subcontracting worksheet to generate a purchase order for the production, and then finish the operation by receiving and invoicing the purchase order.

## Steps

1. Create a new released production order for 12 units of item SP-SCM1009, Airpot.

    1. In the **Tell Me** window, type "released prod. order", and then select the related link.

    2. Create a new Released Prod. Order.

    3. In the Source No. field, type "SP-SCM1009" to select the Airpot.

    4. In **Quantity** field, type "100".

    5. Choose **Refresh Production Order** action.

2. Replace routing to SP-SCM1009-SUB-2 in the production order line and refresh production order – routing only.

    1. Add Production Routing No field to the Lines in the Released Production Order.

    2. Change Routing No. from "SP-SCM1009-SERIAL" to "SP-SCM1009-SUB-2"

    3. Choose **Refresh Production Order** action.

    4. On the **Refresh Production Order** request page, keep toggle Routing on only and then click **OK** to start the batch job.

3. Use the subcontracting worksheet to generate a purchase order for the subcontracted operation on the production order that you created in step 2.

    1. In the **Tell Me** window, type "subcontracting worksheets", and then select the related link.

    2. Choose **Calculate Subcontracts** action.

    3. Select the **Accept Action Message** check box for the created line.

    4. Choose **Carry Out Action Message** action.

    5. On the **Carry Out Action Msg. – Req.** request page, accept all default values, and then click **OK** to start the batch job.

    6. When the batch job finishes, click **OK** to close the subcontracting worksheet.

4. Receive and invoice the purchase order.

    1. In the **Tell Me** window, type "purchase orders", and then select the related link.

    2. On the **Purchase Orders** list find the purchase order from vendor 82000 Subcontractor.

    3. In the **Vendor Invoice No.** field, type "542349".

    4. On the **Lines** FastTab, select line and type 18 into **Direct Cost** field.

    5. Choose **Post** action.

    6. On the request message, select Receive and Invoice. Output of item SP-SCM1009 Airpot is registered.


