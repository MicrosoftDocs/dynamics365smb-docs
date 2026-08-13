---
title: Set up and process a subcontracting operation
description: Walkthrough to learn how to set up and process a subcontracting operation with component transfers, work-in-progress tracking, and returns in Business Central.
ms.date: 08/13/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Set up and process a subcontracting operation

This article illustrates ways to use the Contoso Coffee demo data with the Subcontracting app. The scenarios explain how to set up a production scenario where a subcontractor handles the first assembly operation, while you transfer components and track work-in-progress items and then receive the partially assembled output from the vendor for in-house finishing.

## Scenario

You're the production planner at Contoso Coffee, and you need to produce 12 units of item **SP-SCM1009, Airpot**. You outsource the item's body assembly (the first routing operation) to a subcontractor, while you do the electrical wiring, testing, and packing in-house. You send components to the subcontractor, track the work-in-progress item as it moves between facilities, receive the subcontracted output, and return unused materials.

## Prerequisites

To complete this scenario, you need:

- The Contoso Coffee Manufacturing demo data installed with opening balances posted.
- The **Subcontracting** app installed from Marketplace. Here's a link to the app's [download page](https://marketplace.microsoft.com/product/PUBID.microsoftdynsmb%7CAID.subcontracting%7CPAPPID.1f32a50d-0057-4b95-b5df-cc04d7e89470).

> [!IMPORTANT]
> This scenario modifies the routing and production BOM for item SP-SCM1009. If you plan to run the other subcontracting scenarios, [component supply methods](subcontracting-component-supply-methods.md) or [pricing and item charges](subcontracting-pricing-item-charges.md), run them in order or reset the BOM and routing between scenarios.

## Set up the demo data

### Assign the subcontracting routing to the item

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
1. Open the item card page for item **SP-SCM1009, Airpot**.
1. On the **Replenishment** FastTab, set the **Routing No.** field to **SP-SCM1009-SUB-1**.

   This routing has four operations. The first operation uses **Work Center 500 (Subcontractor)**. The remaining three operations (electrical wiring, testing, packing) are performed in-house.

### Configure the production BOM for component transfers

1. On the item card page for item **SP-SCM1009**, select the **Production BOM** action to open BOM **SP-SCM1009**.
1. In the **Status** field, choose **Under Development**.
1. On the **Lines** FastTab, find the line for **SP-BOM1101, Housing Airpot**. Set the following fields:

   | Field | Value |
   | --------- | --------- |
   | **Routing Link Code** | 500 |
   | **Component Supply Method** | Transfer to Vendor |

1. Find the line for **SP-BOM1102, Coffee filter basket**. Set the following fields:

   | Field | Value |
   | --------- | --------- |
   | **Routing Link Code** | 500 |
   | **Component Supply Method** | Transfer to Vendor |

These two components are now linked to the subcontracting operation and will transfer to the subcontractor's location when needed.

1. In the **Status** field, choose **Certified**.
1. Close the Production BOM.

### Set up work-in-progress transfer on the routing

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then select the related link.
1. Open routing **SP-SCM1009-SUB-1**.
1. In the **Status** field, choose **Under Development**.
1. On operation **10** (Work Center 500, Body assembly), set the following fields:

   | Field | Value |
   | --------- | --------- |
   | **Transfer WIP Item** | Yes |
   | **Transfer Description** | Airpot - body assembled (WIP) |

When you create a transfer order for the subcontractor, [!INCLUDE [prod_short](../../includes/prod_short.md)] includes a line for this work-in-progress item. The WIP item appears on transfer documents for tracking purposes but doesn't create item ledger entries.

1. In the **Status** field, choose **Certified**.
1. Close the routing.

### Set the subcontracting location code on the vendor

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link.
1. Open the vendor card for **82000, Subcontractor**.
1. In the **Subcontracting Location Code** field, enter **82000**.

   This field tells [!INCLUDE [prod_short](../../includes/prod_short.md)] where the subcontractor's facility is located. Without this information, the production order refresh fails because [!INCLUDE [prod_short](../../includes/prod_short.md)] can't determine where to send components.

### Create and refresh the production order

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then select the related link.
1. Select the **New** action, and then fill in the fields as described in the following table.

   | Field | Value |
   | --------- | --------- |
   | **Source Type** | Item |
   | **Source No.** | SP-SCM1009 |
   | **Quantity** | 12 |
   | **Location Code** | MAIN |

1. Select the **Refresh Production Order** action, and then select **OK**.

### Inspect the routing and components

1. On the production order, select the **Components** action.

   The two components you configured with the **Transfer to Vendor** supply method (SP-BOM1101 and SP-BOM1102) have **MAIN** in the **Location Code** field. This is the location from which they transfer to the subcontractor.
1. Close the components and select the **Routing** action.

   The **Subcontracting Routing Details** FactBox shows the status of the subcontracting work for the selected routing line. It shows purchase order quantities, transfer order quantities, and quantities received.

   Operation 10 has the **Subcontracting** toggle enabled.

### Create the subcontracting purchase order

1. Select operation **10**.
1. Select the **Functions** action, and then select **Create Subcontracting Order**.

   A purchase order is created for vendor 82000 (Subcontractor).
1. Open the purchase order.

   The **Lines** FastTab shows the subcontracting work line. If you turn on the **Create Production Order Info Line** toggle on the **Manufacturing Setup** page, a comment line with the production order line description also appears.

   The **Subcontracting Details** FactBox (visible only on subcontracting orders) shows the related production order, routing, and component information.

### Transfer components to the subcontractor

1. On the purchase order, select the **Actions** action, and then select **Create Transf. Ord. to Subcontractor** in the **Subcontracting** group.

   A transfer order is created with two types of lines:

   - **Component lines**: the raw materials (SP-BOM1101 and SP-BOM1102) being transferred from MAIN to location 82000 (Subcontracting).
   - **WIP item line**: the work-in-progress item (SP-SCM1009) with the description "Airpot - body assembled (WIP)" that you defined on the routing.

1. Post the transfer order. Because it's set up as a direct transfer, it posts the shipment and receipt together.
1. To verify, select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Ledger Entries**, and then select the related link. Filter on the transfer order number. There are shipment and receipt entries for the component items (SP-BOM1101 and SP-BOM1102). The WIP item doesn't appear in item ledger entries because it's tracked separately.

### Receive subcontracted output

1. Go back to the purchase order. In the **Qty. to Receive** field on the subcontracting line, enter **8** to simulate a partial delivery.
1. Select the **Post** action, and then select **Receive**.
1. Go back to the production order and open the **Routing**. You can also select the production order link in the **Subcontracting Details** FactBox on the purchase order. The **Subcontracting Routing Details** FactBox now shows **8** in the **Quantity Received** field.

### Return unused materials from the subcontractor

1. Go back to the purchase order. Select the **Actions** action, and then select **Create Return from Subcontractor** under the **Subcontracting** group.  

   [!INCLUDE [prod_short](../../includes/prod_short.md)] calculates how many components were transferred versus how many were consumed by the 8 units received, and suggests returning the surplus quantity.
1. Review the transfer order lines with the return quantities.
1. Post the return transfer order.

### Invoice the purchase order

1. Go back to the purchase order. In the **Vendor Invoice No.** field, enter an invoice number (for example, **SC-2026-001**).
1. Select the **Post** action, and then select **Invoice**.

   The subcontracting cost is now recorded against the production order. To verify, go back to the production order and select the **Statistics** action. On the **Cost** tab, you can see the **Expected** subcontracting cost from the routing and the **Actual** cost from the posted purchase invoice.

## Related information

[Introduction to Contoso Coffee Manufacturing](contoso-coffee-manufacturing-intro.md)  
[Use Different Component Supply Methods in Subcontracting](subcontracting-component-supply-methods.md)  
[Set Up Subcontracting Prices and Allocate Item Charges](subcontracting-pricing-item-charges.md)  
[Subcontracting overview](../../production-how-to-subcontract-manufacturing.md)