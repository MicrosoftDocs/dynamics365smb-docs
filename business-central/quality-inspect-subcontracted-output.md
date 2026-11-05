---
title: Inspect subcontracted production operations
description: Use Contoso Coffee data to create serial-specific quality inspections when you receive output from a subcontracted final production operation.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20405, 20406, 99000831, 50
ms.date: 11/04/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Inspect subcontracted production operations

Create quality inspections when you receive subcontracted production work. Use a production-output inspection rule to inspect the work recorded against the production operation.

In this Contoso Coffee walkthrough, a subcontractor assembles two Airpot Duo units. Use item **SP-SCM1011** and the existing **SP-SCM1009-SUB-F** routing, which has one final assembly operation. Inspect the finished output separately for each serial number.

## Prerequisites

Use a demonstration company with the **Premium** experience and the **Quality Management** and **Subcontracting** apps installed. Enable the Subcontracting app functionality and use the default quality management settings. Generate the **Quality Management** and **Manufacturing** Contoso Coffee modules. The Manufacturing module supplies item **SP-SCM1011**, routing **SP-SCM1009-SUB-F**, work center **600**, and vendor **83000**. Learn more in [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

You need the **Quality Admin & Supervisor** permission set and standard access to the manufacturing and subcontracting processes.

The production order, purchase orders, and inspections use their configured number series. Note their generated numbers as you work through the steps.

## Prepare the item

1. Open the **Items** page, and then open **SP-SCM1011**, Airpot Duo.
2. In the **Routing No.** field, choose **SP-SCM1009-SUB-F**.

## Prepare the inspection template

1. Open the **Quality Tests** page, and then create a Boolean test named **SUBCFINAL** with the description **Finished unit functional**.
2. In the **Pass Condition** field, choose **Yes** and set **Pass Description** to **PASS**.
3. Open the **Quality Inspection Templates** page, and then create **SUBC-FINAL**. Add the test **SUBCFINAL**.

Learn more about configuring tests and sampling in [Create quality inspection templates](qms-quality-templates.md).

## Configure inspections for subcontracting output

Receiving a subcontracting purchase order posts output for the linked production operation. A subcontracting purchase receipt isn't the same as receiving a purchased inventory item, even though you post it from a purchase order. Configure **Production Order Trigger**, rather than a purchase-receipt trigger, for this walkthrough.

### Create the generation rule

Use **Prod. Order Routing Line** as the source table. Its **Subcontracting** field identifies operations whose work center has a subcontractor.

1. On template **SUBC-FINAL**, choose the **Inspection Generation Rules** action, and then create a rule.
2. In the **Intent** field, choose **Production** and set **Table** to **Prod. Order Routing Line**.
3. Use the **Condition Filter** to set **Routing No.** to **SP-SCM1009-SUB-F** and **Subcontracting** to **Yes**.
4. Use the **Item Filter** to set **No.** to **SP-SCM1011**.
5. In the **Activation Trigger** field, choose **Automatic only**.
6. In the **Production Order Trigger** field, choose **When Production Output is posted**.

## Create the production order

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Released Production Orders**, and then choose the related link.
2. Choose the **New** action, and then enter the following values.

   | Field | Value |
   | --- | --- |
   | **Source Type** | **Item** |
   | **Source No.** | **SP-SCM1011**, Airpot Duo |
   | **Quantity** | **2** |
   | **Location Code** | **MAIN** |

3. Choose the **Refresh Production Order** action, and then confirm the refresh.
4. Select the production order line, and then choose the **Routing** action.
5. Verify routing **SP-SCM1009-SUB-F** with operation **10** as its only operation. The **Subcontracting** field must be **Yes**.

## Receive and inspect the last operation with serial numbers

1. On the production order routing, select operation **10**, and then choose the **Create Subcontracting Order** action.
2. Open the new purchase order. Verify vendor **83000**, the linked production order, and quantity **2**. Note the purchase order number.
3. Select the subcontracting purchase line, and then choose the **Item Tracking Lines** action. Enter serial numbers **SN-001** and **SN-002** on separate lines. On each tracking line, enter **1** in **Quantity (Base)** and verify **Qty. to Handle (Base)** of **1**. Verify that the total assigned quantity is **2**.
4. On the subcontracting purchase line, enter **2** in **Qty. to Receive**.
5. Choose the **Post** action, choose **Receive**, and then confirm the posting.
6. On the production order routing, choose **Show Quality Inspections**. The list is filtered to the production order.
7. Verify that two inspections use template **SUBC-FINAL** and operation **10**.

   | Serial number | Quantity (Base) |
   | --- | --- |
   | **SN-001** | **1** |
   | **SN-002** | **1** |

8. On each inspection, record **Yes** for **SUBCFINAL**, and then choose the **Finish** action. Verify **Passed Quantity** of **1** for each unit.
9. Open **Item Ledger Entries**, and then filter to the production order. Verify output of **1** for each of the two serial numbers.

## Review the results

You received two serial-tracked Airpot Duo units from the subcontractor and created one inspection for each unit.

An inspection doesn't automatically block a transaction while the inspection is open or fails. Configure and validate any blocking or inventory workflow separately. Learn more in [Quality management workflows](qms-quality-workflows.md).

## Related information

[Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md)  
[Set up quality inspection generation rules](qms-test-generation-rules.md)  
[Order subcontracting](subcontract-order.md)  
[Process items that failed a quality inspection](qms-non-compliant-processing.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
