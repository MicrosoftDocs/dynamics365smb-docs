---
title: Create an inspection automatically from a warehouse receipt and reinspect the lot
description: Use Contoso Coffee demo data to fail an inspection created from a warehouse receipt and then create a passing reinspection.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 20408, 20404, 20402, 20416
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Create an inspection automatically from a warehouse receipt and reinspect the lot

This demo uses the lot-tracked Contoso Coffee item **WRB-1002** at the advanced warehouse location **WHITE**. When you post the warehouse receipt, you create an inspection for the assigned lot.

## Prerequisites

Generate the **Quality Management** and **Warehouse** modules. For instructions, see [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

You need the **Quality Admin & Supervisor** permission set and permission to create and release purchase orders, assign item tracking, create and post warehouse receipts, and register warehouse put-aways. The admin and supervisor permission set provides access to create the generation rule, complete the inspections, and create the reinspection.

## Enable warehouse receipt inspections

1. Open **Quality Inspection Generation Rules**, and then select **Create Receiving Rule**.
2. In **Choose template**, select **RECEIVE**.
3. Choose the **Warehouse Receipt** action, and then select **Next**.
4. In **Location**, enter **WHITE**. Leave **To Zone** and **Bin** blank, and then choose **Next**.
5. In **Specific Item**, enter **WRB-1002**. Leave **Category** and **Inventory Posting Group** blank, and then choose **Next**.
6. Set the **Automatically Create Inspection** field to **When Warehouse Receipt is posted**.
7. Verify that the displayed filters include location **WHITE**, warehouse document type **Receipt**, and item **WRB-1002**, and then choose **Finish**.

## Create and post the warehouse receipt

1. Open **Purchase Orders**, and then create a purchase order with the following values:

   | Field | Value |
   | --- | --- |
   | Vendor | **20000** |
   | Location Code | **WHITE** |
   | Type | **Item** |
   | No. | **WRB-1002** |
   | Quantity | **1** |

2. Release the order, and then choose **Create Whse. Receipt**.
3. Open the warehouse receipt and verify that **Location Code** is **WHITE**.
4. Choose the receipt line, select **Line**, and then choose **Item Tracking Lines**.
5. Assign lot number **WRB1002-QM-02** to the full **Qty. to Receive**, enter **12/31/2027** as the expiration date, and then close the **Item Tracking Lines** page.
6. Post the warehouse receipt.

[!INCLUDE [prod_short](includes/prod_short.md)] creates an inspection for item **WRB-1002** and lot **WRB1002-QM-02** by using the **RECEIVE** template. The inspection shows the posted warehouse receipt document number and retains the originating purchase order line as an additional source.

## Fail the inspection and create a reinspection

1. Open **Quality Inspections**, and then open the inspection for item **WRB-1002** and lot **WRB1002-QM-02**.
2. Enter **10** for Height, **40** for Length, **20** for Width, and **HEAVY** for Packaging visual.
3. Verify that the result is **FAIL**, and then select **Finish**.
4. Choose **Create Re-inspection**. The new inspection keeps the source and item-tracking information, uses the next **Re-inspection No.**, and rebuilds the test lines without copying the earlier test values.
5. On the reinspection, enter **20** for Height, **40** for Length, **20** for Width, and **UNDAMAGED** for Packaging visual.
6. Verify that the result is **PASS**, and then choose **Finish**.
7. Open the warehouse put-away created from the receipt and register it.

The **WHITE** location uses warehouse receipts and put-aways. Other location configurations can use inventory put-aways or direct purchase receipt posting instead. To learn more about these configurations, go to [Design details: Inbound warehouse flow](design-details-inbound-warehouse-flow.md).

## Related information

[Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Create an inspection manually from item tracking](qms-purchase-receipt-testing-simple.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
