---
title: Inspect production output
description: Use Contoso Coffee demo data to compare setup-time and run-time postings and create a sampled quality inspection at a production operation.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416
ms.date: 11/04/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Inspect production output

Follow this Contoso Coffee walkthrough to inspect an Airpot production operation. First, post setup time without creating an inspection. Then, change a posting condition so that recording run time creates an inspection with a sample of **5** units.

Learn more about posting conditions in [Configure production inspections](qms-setup.md#configure-production-inspections).

## Prerequisites

You need the **Quality Management** app, the **Premium** experience, and permission to post production output. To configure tests, templates, and rules, you also need the **Quality Admin & Supervisor** permission set.

For the example, generate the **Quality Management** and **Manufacturing** modules in a demonstration company. Learn more in [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

Contoso Coffee wants to check the Airpot reservoir and electrical continuity during the electrical-wiring operation. Use item **SP-SCM1009**, routing **SP-SCM1009-SERIAL**, and a production quantity of **15**.

The example focuses on time postings at intermediate operation **20**. Process other routing operations and component consumption as part of the production process. Learn more in [Batch post output and run times](production-how-to-post-output-quantity.md).

## Prepare the production template and rule

1. Open **Quality Tests**, and then create the following Boolean tests. For each test, set **Pass Condition** to **Yes** and **Pass Description** to **PASS**.

   | Code | Description |
   | --- | --- |
   | **RESERVOIRLEAK** | Reservoir leak check |
   | **ELECCONTINUITY** | Electrical continuity check |

   The reservoir leak test reflects the Airpot reservoir, tubing, and sealed connections. The electrical continuity test reflects the electrical-wiring operation in its routing.
2. Open the **Quality Inspection Templates** page, and then open **PRODUCTION**.
3. In the **Sample Source** field, choose **Fixed Quantity**, and then enter **5** in the **Sample Amount** field.
4. Configure the template with only the **RESERVOIRLEAK** and **ELECCONTINUITY** tests for this demonstration. Learn more in [Create quality inspection templates](qms-quality-templates.md).
5. Open **Quality Inspection Generation Rules**.
6. Open the rule with sort order **50** and template **PRODUCTION**.
7. Verify that the rule's **Table** is **Prod. Order Routing Line**.
8. Use the **Condition Filter** to set **Routing No.** to **SP-SCM1009-SERIAL** and **Operation No.** to **20**.
9. Use the **Item Filter** to set **No.** to **SP-SCM1009**.
10. Verify that **Activation Trigger** is **Manual or Automatic**.
11. In the **Production Order Trigger** field, choose **When Production Output is posted**.

## Create the production order

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Released Production Orders**, and then choose the related link.
2. Choose **New**.
3. On the production order, enter the following values:

   | Field | Value |
   | --- | --- |
   | Source Type | **Item** |
   | Source No. | **SP-SCM1009**, Airpot |
   | Quantity | **15** |
   | Location Code | **MAIN** |

4. Choose **Refresh Production Order**, and then confirm the refresh.
5. On the routing, verify routing **SP-SCM1009-SERIAL** and operations **10**, **20**, **30**, and **40**.
6. Note the production order number so you can identify its inspections and ledger entries.

## Exclude setup-time postings from inspections

1. Open the **Quality Management Setup** page, and record the current **Prod. trigger output condition** value.
2. Set **Prod. trigger output condition** to **Only with Quantity**.

   This setting affects the whole company. Restore the recorded value when you finish the demonstration.

3. Open the **Output Journals** page, and then select an empty journal batch for this demonstration. Enter one line for the production order, item **SP-SCM1009**, and operation **20**.
4. In the **Setup Time** field, enter **22** minutes. Keep **Run Time**, **Output Quantity**, and **Scrap Quantity** at **0**. Verify the posting date. If the **Setup Time** field isn't shown, add the field through [personalization](ui-personalization-user.md).
5. Choose the **Post** action, and then confirm the posting.
6. On the production order, open **Routing**, and then choose the **Show Quality Inspections** action. The list is filtered to the production order. Verify that no inspection was created. **Only with Quantity** excludes this setup-time-only posting.

## Create an inspection from a run-time posting

1. Open the **Quality Management Setup** page, and in the **Prod. trigger output condition** field, choose **Any Output Entry (time or quantity)**.
2. Return to the output journal batch. Enter a new line for the same production order, item **SP-SCM1009**, and operation **20**.
3. In the **Run Time** field, enter **18** minutes. Keep **Setup Time**, **Output Quantity**, and **Scrap Quantity** at **0**. Choose the **Post** action, and then confirm the posting.
4. On the production order routing, choose **Show Quality Inspections** again. Open the new inspection for operation **20**.
5. Verify **Quantity (Base)** of **15** and **Sample Size** of **5**.
6. Enter **Yes** for **RESERVOIRLEAK** and **ELECCONTINUITY**, and then choose the **Finish** action.
7. Verify that the inspection is **Finished** with a **PASS** result and **Passed Quantity** of **5**. The passed quantity doesn't include the other **10** units.

## Restore the company setting

On the **Quality Management Setup** page, restore the recorded **Prod. trigger output condition** value.

## Related information

[Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Set up quality inspection generation rules](qms-test-generation-rules.md)  
[Batch post output and run times](production-how-to-post-output-quantity.md)  
[Process items that failed a quality inspection](qms-non-compliant-processing.md)  

[!INCLUDE [footer-include](includes/footer-banner.md)]