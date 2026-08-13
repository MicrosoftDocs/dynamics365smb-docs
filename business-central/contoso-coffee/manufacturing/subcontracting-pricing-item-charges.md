---
title: Set up subcontracting prices and allocate item charges
description: Walkthrough to learn how to set up subcontracting price lists and allocate extra costs using item charges in Business Central.
ms.date: 08/13/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Set up subcontracting prices and allocate item charges

This article explains how to use the Contoso Coffee demo data to set up a subcontracting price list and allocate extra costs to subcontracted work using item charges. Instead of using a fixed cost on the routing, you can maintain a price list that [!INCLUDE [prod_short](../../includes/prod_short.md)] uses automatically when you create purchase orders.

## Scenario

You work with the subcontractor that assembles Airpots for Contoso Coffee. The subcontractor charges per unit, but there's a minimum order amount of 100.00 in local currency (LCY). You must set up a price list so that [!INCLUDE [prod_short](../../includes/prod_short.md)] applies the correct price when you create subcontracting purchase orders.

After receiving the subcontracted work, a separate transport cost arrives from a logistics provider. You need to allocate this cost to the subcontracting output so that the production order reflects the true cost.

## Prerequisites

To run this scenario, you need:

- The Contoso Coffee Manufacturing demo data installed with opening balances posted.
- The **Subcontracting** app installed from the marketplace.
- Item **SP-SCM1009** with **Routing No.** set to **SP-SCM1009-SUB-F** (single subcontracting operation). If you ran a previous walkthrough with routing SUB-1, change it back to SUB-F on the item card.

> [!IMPORTANT]
> This scenario creates subcontracting price entries and posts purchase documents. If you want to repeat the scenario, delete the price entry and any open production or purchase orders from the previous run.

## Set up the subcontracting price list

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Prices**, and then select the related link.
1. Select the **New** action and fill in the fields as described in the following table.

   | Field | Value |
   | --------- | --------- |
   | **Vendor No.** | 82000 |
   | **Item No.** | SP-SCM1009 |
   | **Work Center No.** | 500 |
   | **Direct Unit Cost** | 15.00 |
   | **Minimum Amount** | 100.00 |

   The Vendor No., Item No., and Work Center No. fields are required. The **Minimum Amount** means that even if the unit price multiplied by quantity results in a lower amount, the purchase order line amount is at least 100.00.

   > [!TIP]
   > For more granular pricing, define prices by **Variant Code**, **Standard Task Code**, and **Unit of Measure Code**. [!INCLUDE [prod_short](../../includes/prod_short.md)] resolves the most specific match.

### Create the production order

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
1. Select the **New** action, and then fill in the fields as described in the following table.

    | Field | Value |
    | --------- | --------- |
    | **Source Type** | Item |
    | **Source No.** | SP-SCM1009 |
    | **Quantity** | 5 |
    | **Location Code** | MAIN |

1. Select the **Refresh Production Order** action, and then select **OK**.

### Create the subcontracting order and verify pricing

1. On the production order, select the **Routing** action.
1. Select the subcontracting operation, and then select **Functions**, **Create Subcontracting Order**.
1. Open the purchase order.
1. On the **Lines** FastTab, check the **Direct Unit Cost Excl. Tax** field. [!INCLUDE [prod_short](../../includes/prod_short.md)] got the price from the subcontracting price list, but because 5 × 15.00 = 75.00 is less than the minimum amount of 100.00, the unit cost is adjusted to **20.00** (100.00 ÷ 5) to meet the minimum.
1. Check the **Line Amount** field. It shows **100.00** minus the minimum amount applies.
1. The **Subcontracting Prices** FactBox shows matching price entries for this vendor, item, and work center combination.

### Receive and invoice the subcontracting order

1. On the purchase order, in the **Vendor Invoice No.** field, enter an invoice number (for example, **SC-PRICE-001**).
1. Select the **Post** action, and then select **Receive and Invoice**.

### Allocate an item charge for transport costs

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then select the related link.
1. Select the **New** action. In the **Vendor No.** field, select **10000, Fabrikam, Inc.**.
1. In the **Vendor Invoice No.** field, enter an invoice number (for example, **TRANSPORT-001**).
1. On the **Lines**, set the **Type** field to **Charge (Item)**.
1. In the **No.** field, select **JB-FREIGHT**.
1. Set the **Quantity** to **1** and the **Direct Unit Cost** to **50.00**.
1. With the item charge line selected, select the **Line** action, and then select **Item Charge Assignment**.
1. On the **Item Charge Assignment** page, select the **Get Receipt Lines** action.
1. Find the posted receipt line for the subcontracting work (vendor 82000, item SP-SCM1009). Select it, and then select **OK**.
1. Verify that the **Qty. to Assign** is set to **1** on the receipt line. Close the **Item Charge Assignment** page.
1. Select the **Post** action to post the purchase invoice.

### Verify costs on the production order

1. Go back to the released production order for **SP-SCM1009**.
1. Select the **Statistics** action.
1. On the **Cost** tab, compare the columns:

    - **Expected**: the subcontracting cost calculated from the routing (based on the routing line unit cost).
    - **Actual**: the subcontracting cost from the posted purchase invoice plus the allocated item charge.

    The actual cost includes both the subcontracting work, 100.00, and the 50.00 freight charge, so it exceeds the expected cost.

## Related information

[Introduction to Contoso Coffee Manufacturing](contoso-coffee-manufacturing-intro.md)  
[Set Up and Process a Subcontracting Operation](set-up-process-subcontracting-operation.md)  
[Use Different Component Supply Methods in Subcontracting](subcontracting-component-supply-methods.md)  
[Subcontracting prices](../../subcontract-prices.md)  
[Subcontracting overview](../../production-how-to-subcontract-manufacturing.md)  
