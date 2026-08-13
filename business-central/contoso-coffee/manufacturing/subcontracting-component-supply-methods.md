---
title: Use different component supply methods in subcontracting
description: Walkthrough to learn how the three component supply methods work in subcontracting and how they affect planning in Business Central.
ms.date: 08/13/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Use different component supply methods in subcontracting

This article illustrates how the three component supply methods work in the Subcontracting app. Using the Contoso Coffee demo data, you set up a production BOM where different components reach the subcontractor through different channels. Then, you explore how the planning system handles each method differently.

## Scenario

You produce the **SP-SCM1009, Airpot** at Contoso Coffee. A subcontractor handles the full assembly. Different components reach the subcontractor through different channels:

- **Housing**: you transfer it from your warehouse to the subcontractor.
- **Circuit board**: you order it from your supplier and have it delivered directly to the subcontractor's location.
- **Power cord**: the subcontractor provides it. You don't need to plan for it.

You want to know how [!INCLUDE [prod_short](../../includes/prod_short.md)] handles each supply method in planning and on the purchase order.

## Prerequisites

To run this scenario, you need:

- The Contoso Coffee Manufacturing demo data installed with opening balances posted.
- The **Subcontracting** app installed from Marketplace. Here's a link to the app's [download page](https://marketplace.microsoft.com/product/PUBID.microsoftdynsmb%7CAID.subcontracting%7CPAPPID.1f32a50d-0057-4b95-b5df-cc04d7e89470).

> [!IMPORTANT]
> This scenario changes the routing to SP-SCM1009-SUB-F and sets different component supply methods on the BOM. If you previously ran the [Set Up and Process a Subcontracting Operation](set-up-process-subcontracting-operation.md) scenario, you must change the routing back and clear the routing link codes before you proceed.

## Set up the demo data

### Assign the routing and configure the BOM

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link.
1. Open the item card page for **SP-SCM1009, Airpot**.
1. On the **Replenishment** FastTab, verify or set the **Routing No.** field to **SP-SCM1009-SUB-F**.

   This routing has a single subcontracting operation, which keeps the focus on component supply rather than routing complexity.

1. On the item card page, select the **Production BOM** action to open BOM **SP-SCM1009**.
1. In the **Status** field, choose **Under Development**.
1. On the **Lines** FastTab, configure the following components:

    For **SP-BOM1101, Housing Airpot**:

    |Field | Value |
    | --------- | --------- |
    | **Routing Link Code** | 500 |
    | **Component Supply Method** | Transfer to Vendor |

    You transfer this component from your MAIN warehouse to the subcontractor. [!INCLUDE [prod_short](../../includes/prod_short.md)] creates a transfer order when you process the production order.

    For **SP-BOM1107, Circuit board**, set the following fields:

    | Field | Value |
    | --------- | --------- |
    | **Routing Link Code** | 500 |
    | **Component Supply Method** | Consignment at Vendor |

    You purchase this component, but it's delivered directly to the subcontractor's location. The planning system creates purchase demand at the subcontracting location.

    For **SP-BOM1108, Power cord**, fill in the following fields:

    | Field | Value |
    | --------- | --------- |
    | **Routing Link Code** | 500 |
    | **Component Supply Method** | Vendor-Supplied |

    The subcontractor provides this component. Exclud it from your planning.

1. In the **Status** field, choose **Certified**.

1. Close the production BOM.

### Set the subcontracting location code on the vendor

> [!NOTE]
> If you already completed this step in the [Set Up and Process a Subcontracting Operation](set-up-process-subcontracting-operation.md) scenario, skip this section.

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then select the related link.
1. Open the vendor card page for **82000, Subcontractor**.
1. In the **Subcontracting Location Code** field, enter **82000**.

    This field tells [!INCLUDE [prod_short](../../includes/prod_short.md)] where the subcontractor's facility is located. Without this information, the production order refresh fails because [!INCLUDE [prod_short](../../includes/prod_short.md)] can't determine where to send components.

### Create the production order

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then select the related link.
1. Select the **New** action, and then fill in the fields as described in the following table.

    | Field | Value |
    | --------- | --------- |
    | **Source Type** | Item |
    | **Source No.** | SP-SCM1009 |
    | **Quantity** | 10 |
    | **Location Code** | MAIN |

1. Select the **Refresh Production Order** action, and then select **OK**.

### Review how components are set up

1. On the production order, select the **Components** action.
1. Notice the differences in the **Location Code** column:

    | Component | Location Code | Why |
    | --------- | --------- | --------- |
    | SP-BOM1101 (Housing) | MAIN | Transfer from MAIN to the subcontractor |
    | SP-BOM1107 (Circuit board) | 82000 | Purchased and delivered directly to the subcontracting location |
    | SP-BOM1108 (Power cord) | 82000 | Vendor supplied, excluded from planning |

    The location code shows where the component needs to be before the subcontracting operation starts.

1. For each of these components, set the **Flushing Method** field to **Backward**. This setting ensures that component consumption posts automatically when you receive the output from the subcontractor.

### Explore how planning handles each method

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheets**, and then select the related link.
1. Select the **Calculate Regenerative Plan** action.
1. On the request page, set the **Item Filter** to **SP-BOM1101|SP-BOM1107|SP-BOM1108** to focus on the three components. select **OK**.
1. Review the results:

    - **SP-BOM1107 (Circuit board)**: the planning system suggests a purchase order with **82000** in the **Location Code** field. The component is delivered directly to the subcontractor. Standard purchase planning rules (reorder policy, safety stock) apply to this location.
    - **SP-BOM1101 (Housing)**: depending on available inventory at MAIN, a planning line might appear. The component is handled through a transfer order, not purchase planning.
    - **SP-BOM1108 (Power cord)**: no planning line appears. The subcontractor provides this component, so your planning system ignores it.

1. Select the planning line for **SP-BOM1107 (Circuit board)** and select **Carry Out Action Message**. This creates a purchase order for the circuit board at location 82000.
1. Open the purchase order for **SP-BOM1107** and post the receipt. This makes the circuit board available at the subcontractor's location before the subcontracting work begins.

### Create the subcontracting order and process the transfer

1. Go back to the production order and select the **Routing** action.
1. Select the subcontracting operation, and select **Functions**, **Create Subcontracting Order**.
1. Open the purchase order. On the **Lines** FastTab, the vendor-supplied component (SP-BOM1108) appears on the purchase order alongside the subcontracting work line.
1. Select **Create Transf. Ord. to Subcontractor** in the **Subcontracting** action group.

    A transfer order is created only for **SP-BOM1101 (Housing)**. The circuit board (consignment at vendor) is handled through separate purchase planning, and the power cord (vendor supplied) doesn't need a transfer.

1. Post the transfer order.

### Receive the subcontracting output

1. On the purchase order, select the **Post** action, and then select **Receive**.
1. To verify component consumption, select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Ledger Entries**, and then select the related link. Filter on the production order number and then choose **Consumption** in the **Entry Type** field.

    Consumption entries display for all three components, posted from location 82000 (the subcontracting location). The housing was transferred there earlier, the circuit board was purchased directly to that location, and the power cord is vendor-supplied at that location. The backward flushing method posted consumption automatically when the subcontracting output was received.

## Related information

[Introduction to Contoso Coffee Manufacturing](contoso-coffee-manufacturing-intro.md)  
[Set Up and Process a Subcontracting Operation](set-up-process-subcontracting-operation.md)  
[Set Up Subcontracting Prices and Allocate Item Charges](subcontracting-pricing-item-charges.md)  
[Subcontracting overview](../../production-how-to-subcontract-manufacturing.md)  
