---
title: Transfer WIP items between subcontractors
description: Learn how to transfer work-in-progress (WIP) items between subcontractors using transfer orders, track WIP quantities in a dedicated ledger, and adjust or clean up WIP quantities.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, WIP, work-in-progress, transfer order, WIP ledger, WIP adjustment, multi-stage
ms.search.form: 99001560, 99001561
ms.date: 06/18/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Transfer WIP items between subcontractors

In multi-stage subcontracting scenarios, the semi-finished product (the production order parent item) moves between subcontractor locations as it progresses through operations. [!INCLUDE [prod_short](includes/prod_short.md)] calls this a **WIP item transfer**. This article explains how WIP item transfers work, how to create them, and how to track and adjust WIP quantities.

## About WIP item transfers

A WIP item transfer uses a transfer order to document the physical movement of the production order parent item between subcontractor locations or between your warehouse and a subcontractor. However, unlike standard transfer orders, posting a WIP transfer doesn't create item ledger entries, value entries, or warehouse entries. Instead, quantities are tracked in a dedicated **Subcontractor WIP Ledger Entry** table.

This approach reflects the reality that the WIP item (the semi-finished product) belongs to the production order and isn't a separate inventory item that moves through the standard costing and valuation pipeline. The WIP item remains under the production order's cost umbrella throughout the subcontracting process.

### Key characteristics of WIP item transfers

- WIP transfers use a **Transfer WIP Item** flag on the routing line to control whether an operation triggers a WIP item transfer.
- A single routing line represents a physical operation and controls the transfer behavior. No separate routing lines are needed for WIP transfers.
- Transfer orders document shipments and receipts, but posting only creates entries in the WIP ledger.
- Item tracking (serial numbers, lot numbers) isn't supported for WIP transfer lines.
- The solution supports multi-stage subcontracting, including subcontractor-to-subcontractor movements.

## Set up WIP item transfers on routing lines

To enable WIP item transfers for a subcontracting operation, set the **Transfer WIP Item** field on the routing line.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routing**, and then choose the related link.
2. Open the routing for the item you want to manufacture.
3. On the line for the subcontracting operation, turn on **Transfer WIP Item**.

> [!NOTE]
> The **Transfer WIP Item** field is only available when the routing line is linked to a subcontracting work center. [!INCLUDE [prod_short](includes/prod_short.md)] automatically sets this field when you assign a subcontracting work center to the routing line.

When you create or refresh a production order, the **Transfer WIP Item** setting is copied to the corresponding production order routing line.

### Add an operation-specific transfer description

You can specify an operation-specific description that [!INCLUDE [prod_short](includes/prod_short.md)] uses on transfer orders instead of the standard item description. This is useful when the same parent item passes through multiple operations and you want to identify the stage of completion.

1. On the routing line for the subcontracting operation, fill in the **Transfer Description** field.
2. Optionally, fill in the **Transfer Description 2** field for an additional description line.

If the **Transfer Description** field is empty, [!INCLUDE [prod_short](includes/prod_short.md)] uses the standard item description on transfer orders.

## Create WIP transfer orders

You create WIP transfer orders from the subcontracting purchase order, together with component transfer orders.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the subcontracting purchase order.
3. Choose the **Create Transf. Ord. to Subcontractor** action.

If the **Transfer WIP Item** field is turned on for the operation, [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer line for the production order parent item in addition to transfer lines for components. The WIP transfer line is marked with **Transfer WIP Item** turned on.

### How locations are determined

[!INCLUDE [prod_short](includes/prod_short.md)] automatically determines the transfer-from and transfer-to locations:

- **Transfer-from location**:
  - For the first operation: Your company warehouse (the production order line location).
  - For subsequent operations: The previous subcontractor's location when the WIP item is already at a subcontractor.
- **Transfer-to location**: The current operation's subcontractor location (from the vendor card).

If more than one previous operation exists (parallel routing), [!INCLUDE [prod_short](includes/prod_short.md)] creates a separate transfer order for each unique from-location and to-location combination.

### How quantities are determined

[!INCLUDE [prod_short](includes/prod_short.md)] calculates the WIP transfer quantity based on the scenario:

- **Initial transfer** (from company warehouse): Uses the production order line quantity. For parallel WIP operations, the quantity is divided by the number of parallel WIP operations.
- **Subsequent transfers** (between subcontractors): Uses the current WIP quantity at the source location from WIP ledger entries.

You can manually adjust transfer order quantities before posting.

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] doesn't create a second WIP transfer order for the same operation if the expected quantity is already covered by WIP ledger entries at the destination.

## Post WIP transfer orders

You can post WIP transfer orders using the same methods as standard transfer orders:

- Post from the **Transfer Order** page.
- Post through warehouse shipments and receipts.
- Use direct transfers (if configured).

When you post a WIP transfer order, [!INCLUDE [prod_short](includes/prod_short.md)] creates entries in the **Subcontractor WIP Ledger Entry** table instead of standard item ledger entries.

> [!IMPORTANT]
> No item ledger entries, value entries, warehouse entries, pick documents, or put-away documents are created for WIP transfer lines.

## View WIP ledger entries

You can view WIP ledger entries from several places in [!INCLUDE [prod_short](includes/prod_short.md)]:

- **From a production order**: On the released or finished production order, choose the **Subcontracting WIP Entries** action.
- **From an item**: On the item card or list, choose the **Subcontracting WIP Entries** action to view all WIP entries for that item.
- **From a work center**: On the work center card or list, under **Related**, choose the **Subcontracting WIP Entries** action.
- **Directly**: Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting WIP Entries**, and then choose the related link.

### WIP quantities on production order routing lines

The production order routing line shows two calculated fields that summarize the WIP status:

- **WIP Qty. (Base) at Subc.**: The total WIP quantity currently at the subcontractor location for this operation.
- **WIP Qty. (Base) in Transit**: The total WIP quantity currently in transit for this operation.

### Find WIP entries with Navigate

WIP ledger entries are included in the **Navigate** (Find Entries) results. When you use the Navigate function for a posted transfer document, [!INCLUDE [prod_short](includes/prod_short.md)] shows the related WIP ledger entries alongside other document entries.

## Adjust WIP quantities

You can manually adjust WIP quantities to correct discrepancies, for example, if physical stock doesn't match the system records.

### Adjust from the Subcontracting WIP Entries page

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting WIP Entries**, and then choose the related link.
2. Select the WIP entry you want to adjust.
3. Choose the **WIP Adjustment** action.
4. On the **WIP Adjustment** page, review the **Current Quantity (Base)** and enter the **New Quantity (Base)**.
5. Choose **OK** to create the adjustment entry.

[!INCLUDE [prod_short](includes/prod_short.md)] creates a new WIP ledger entry with document type **Adjustment (Manual)** for the difference between the current and new quantities.

### Adjust from a production order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. Choose the **WIP Adjustment** action.
4. On the **WIP Adjustment** page, review and update the quantities.
5. Choose **OK**.

## Clean up WIP quantities when finishing production orders

When you finish a production order, you can automatically clear all remaining WIP quantities. This is useful when the subcontractor has completed the work and all WIP items have been accounted for.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. Choose the **Change Status** action and set the new status to **Finished**.
4. On the **Change Status** dialog, turn on **WIP Quantity Clean Up**.
5. Choose **Yes** to change the status.

When **WIP Quantity Clean Up** is enabled, [!INCLUDE [prod_short](includes/prod_short.md)] performs the following steps:

1. Finds all WIP ledger entries linked to the production order.
2. Groups remaining quantities by location, item, and variant.
3. For each group with a nonzero remaining quantity, creates a balancing adjustment entry with document type **Adjustment (Finish Prod Order)** to bring the balance to zero.

> [!NOTE]
> If **WIP Quantity Clean Up** is turned off, no automatic cleanup happens. This allows you to handle scrap or other special scenarios manually.

## Transfer modes and warehouse handling

How you configure transfer routes and the **Inventory Setup** page affects which transfer mode [!INCLUDE [prod_short](includes/prod_short.md)] uses, and which warehouse configurations are supported.

### How the transfer mode is determined

When [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order for subcontracting, it checks the transfer route between the two locations:

- If a transfer route with an **In-Transit Code** exists, a standard transfer order is created (ship, then receive through the transit location).
- If no transfer route exists, or the route has no **In-Transit Code**, a **direct transfer** is created. The posting behavior of the direct transfer depends on the **Direct Transfer Posting** field on the **Inventory Setup** page.

### Supported combinations for WIP transfers

The following table shows which transfer modes work for WIP items depending on the warehouse handling at the transfer-from and transfer-to locations.

|Transfer mode|Direction|No warehouse handling|Require Pick / Put-away|Require Shipment / Receive|Directed Put-away and Pick|
|---|---|---|---|---|---|
|In-Transit (recommended)|Send to subcontractor|Supported|Partial (1)|Supported|Supported|
|In-Transit (recommended)|Receive from subcontractor|Supported|Partial (1)|Supported|Supported|
|Direct – Shipment and Receipt|Send to subcontractor|Supported|Supported|Supported|Supported|
|Direct – Shipment and Receipt|Receive from subcontractor|Supported|Not supported|Not supported|Not supported|
|Direct – Direct Transfer|Send to subcontractor|Not supported|Not supported|Not supported|Not supported|
|Direct – Direct Transfer|Receive from subcontractor|Not supported|Not supported|Not supported|Not supported|

(1) Inventory Pick and Put-away creation is not supported forWIP lines. You can post directly from the transfer order as a workaround.

> [!IMPORTANT]
> To ensure WIP transfers work reliably with all warehouse configurations, set up transfer routes with an **In-Transit Code** between your warehouse locations and each subcontractor location. Also review the **Direct Transfer Posting** field on the **Inventory Setup** page if you work without transfer routes.

## Create return transfer orders for WIP items

If you need to return the WIP item from a subcontractor, you can create a return transfer order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the subcontracting purchase order.
3. Choose the **Create Return from Subcontractor** action.

[!INCLUDE [prod_short](includes/prod_short.md)] creates a return transfer order with WIP transfer lines. The transfer-from location is the subcontractor location, and the transfer-to location is your company warehouse (the production order line location). The return quantity is based on the WIP ledger entry quantities at the subcontractor location.

> [!NOTE]
> Return transfer orders use the same transfer mode logic as outbound transfers. If no transfer route with an In-Transit Code exists, [!INCLUDE [prod_short](includes/prod_short.md)] creates a direct transfer, which might fail for locations that require inbound warehouse handling. To avoid issues, configure a transfer route with an In-Transit Code from the subcontractor location back to your warehouse.

## Restrictions and validations

[!INCLUDE [prod_short](includes/prod_short.md)] applies the following restrictions for WIP item transfers:

- **Item tracking**: You can't add serial numbers or lot numbers to WIP transfer lines. The system blocks opening item tracking lines for WIP transfer lines.
- **Reservations**: You can't create reservations against WIP transfer lines.
- **Planning**: WIP transfer lines don't appear as demand or supply in planning calculations because the base quantity fields are set to zero.
- **Warehouse handling**: WIP transfer lines work with warehouse shipments and receipts, but with adapted quantity handling. No pick or put-away documents are created for WIP lines.

### Routing line restrictions

When a routing line has **Transfer WIP Item** turned on and transfer orders exist or stock is at the subcontractor location, you can't change the following fields:

- **No.** (Work Center No.)
- **Operation No.**
- **Routing Link Code**
- **Type**
- **Transfer WIP Item** (turning off)

You also can't delete the routing line.

### Finishing a production order

[!INCLUDE [prod_short](includes/prod_short.md)] blocks finishing a production order if open (unposted) WIP transfer orders exist for it. You must post or delete the transfer orders before you can change the status to **Finished**.

## Related information

[Manage components in subcontracting](subcontract-components.md)  
[Order subcontracting from production orders](subcontract-order.md)  
[Order subcontracting](subcontract-order.md)  
[Set up locations for subcontracting](subcontract-location-management.md)  
[Set up subcontracting](subcontract-setup.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
