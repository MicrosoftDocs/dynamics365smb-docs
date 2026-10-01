---
title: Create an inspection manually from item tracking
description: Use Contoso Coffee demo data to create a quality inspection manually from a purchase order item-tracking line.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Create an inspection manually from item tracking

This demo uses the lot-tracked Contoso Coffee item **WRB-1002** at the **MAIN** location. You create an inspection manually from the purchase order's item-tracking line before you post the receipt.

## Prerequisites

Generate the **Quality Management** and **Warehouse** modules. Learn more in [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

You need permission to create purchase orders and assign item tracking. You also need the **Quality Inspector** or **Quality Admin & Supervisor** permission set to enter test values and finish the inspection, plus effective access to quality management integration objects. The **Quality Inspection - Create** permission set provides the minimum quality management integration permissions.

## Prepare the generation rule

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Generation Rules**, and then choose the related link.
2. Open the rule with sort order **40** and template **RECEIVE**.
3. Verify that **Activation Trigger** is **Manual or Automatic** or **Manual only**.

## Create the inspection from item tracking

1. Open **Purchase Orders**, and then create a purchase order with the following values:

   | Field | Value |
   | --- | --- |
   | Vendor | **20000** |
   | Type | **Item** |
   | No. | **WRB-1002** |
   | Quantity | **1** |
   | Location Code | **MAIN** |

2. On the purchase line, choose **Item Tracking Lines**.
3. Assign lot number **WRB1002-QM-01** to the full quantity, and enter **12/31/2027** as the expiration date.
4. Select the tracking line, select **Quality Management**, and then choose **Create Quality Inspections**.

[!INCLUDE [prod_short](includes/prod_short.md)] creates an inspection that's linked to the purchase line and selected lot. To review it from the tracking page, select **Quality Management**, and then select **Show Quality Inspections for Item with tracking specification**.

## Complete the inspection

1. Open **Quality Inspections**, and then open the inspection for item **WRB-1002** and lot **WRB1002-QM-01**.
2. Enter **20** for Height, **40** for Length, **20** for Width, and **UNDAMAGED** for Packaging visual.
3. Verify that the result is **PASS**, and then select **Finish**.
4. From the **Report** menu, choose **Certificate of Analysis** to preview the completed measurements.

To explore a failed receipt, use **10** for Height or **HEAVY** for Packaging visual. Learn more in [Process items that failed a quality inspection](qms-non-compliant-processing.md).

## Related information

[Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Create an inspection automatically from a warehouse receipt and reinspect the lot](qms-purchase-receipt-testing-warehouse.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
