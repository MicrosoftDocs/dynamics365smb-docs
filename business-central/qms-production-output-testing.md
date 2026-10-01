---
title: Create a sampled inspection automatically from production output
description: Use Contoso Coffee demo data to create a quality inspection automatically when posting production output.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Create a sampled inspection automatically from production output

This demo shows how to automatically create a sampled quality inspection when you post output for the Contoso Coffee Airpot item. You create two tests that match the Airpot production process, add them to the empty **PRODUCTION** template, set a sample amount of five units, and post output for 20 units.

## Prerequisites

Generate the **Quality Management** and **Manufacturing** modules. The Premium experience is required. Learn more in [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

You need the **Quality Admin & Supervisor** permission set and permission to create released production orders and post production output. The Manufacturing module provides the item and routing used in this demo. You create the production order in the following procedure.

## Prepare the production template and rule

1. Open **Quality Tests**, and then create the following Boolean tests. For each test, enter **No** as the condition for **FAIL** and **Yes** as the condition for **PASS**.

   | Code | Description |
   | --- | --- |
   | **RESERVOIRLEAK** | Reservoir leak check |
   | **ELECCONTINUITY** | Electrical continuity check |

   The reservoir leak test reflects the Airpot reservoir, tubing, and sealed connections. The electrical continuity test reflects the electrical-wiring operation in its routing.
2. Open **Quality Inspection Templates**, and then open **PRODUCTION**.
3. In **Sample Source**, select **Fixed Quantity**, and then enter **5** in **Sample Amount**.
4. Add the **RESERVOIRLEAK** and **ELECCONTINUITY** tests. Learn more in [Create quality inspection templates](qms-quality-templates.md).
5. Open **Quality Inspection Generation Rules**.
6. Open the rule with sort order **50** and template **PRODUCTION**.
7. Verify that **Activation Trigger** is **Manual or Automatic**.
8. Set **Production Order Trigger** to **When Production Output is posted**.
9. Set **Prod. Trigger Output Condition** to **Only with Quantity**.

## Create and post the production order

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Released Production Orders**, and then choose the related link.
2. Choose **New**.
3. On the production order, enter the following values:

   | Field | Value |
   | --- | --- |
   | Source Type | **Item** |
   | Source No. | **SP-SCM1009**, Airpot |
   | Quantity | **20** |
   | Location Code | **MAIN** |

4. Choose **Refresh Production Order**, and then confirm the refresh.
5. On the routing, verify routing **SP-SCM1009-SERIAL** and operations **10**, **20**, **30**, and **40**.
6. Select **Prod. Order**, and then choose **Production Journal**.
7. On operation **40**, enter **20** in **Output Quantity**.
8. Choose **Post**, and then confirm the posting.

[!INCLUDE [prod_short](includes/prod_short.md)] creates an inspection linked to the production routing line and output transaction.

## Complete the inspection

1. Open **Quality Inspections**, and then open the inspection for item **SP-SCM1009**.
2. Verify that **Quantity (Base)** is **20** and **Sample Size** is **5**.
3. Enter **Yes** for **RESERVOIRLEAK** and **ELECCONTINUITY**.
4. Add a note or picture if needed, and then select **Finish**.
5. Verify that **Passed Quantity** is **5**. The remaining 15 units aren't automatically classified by the sampled inspection.
6. Choose **Inspection Report** from the **Report** menu to review the source and test results.

## Related information

[Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Set up quality inspection generation rules](qms-test-generation-rules.md)  

[!INCLUDE [footer-include](includes/footer-banner.md)]