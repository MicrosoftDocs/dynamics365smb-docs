---
title: Manage components in subcontracting
description: Learn how subcontracting types determine component handling, how locations are assigned, how to create transfer orders and returns, and how flushing works.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, components, production BOM, routing, flushing, transfer order, location
ms.search.form: 99000886
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Manage components in subcontracting

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

When you subcontract manufacturing operations, components must be available at the right location — either at the subcontractor's site or at your own warehouse. This article explains the subcontracting types that control how components are handled, how locations are assigned, and how to use transfer orders to move materials to and from subcontractors.

## About subcontracting types

The subcontracting type on a component determines where the component is consumed and how it gets there. You can set the type in the production BOM (for master data) or directly on components in released production orders.

There are three subcontracting types:

- **Purchase with Service**: The subcontractor procures the component directly and provides it alongside the manufacturing service. [!INCLUDE [prod_short](includes/prod_short.md)] automatically adds a purchase line for the component on the subcontracting purchase order. You don't supply the material — the vendor does. The component location changes to the subcontractor's location.
- **Inventory by Vendor**: The component is already physically at the subcontractor's location, available for them to consume. The components are your property, and you're responsible for keeping that location stocked. For example, by shipping materials in bulk or purchasing directly to the vendor's location. You can use standard [!INCLUDE [prod_short](includes/prod_short.md)] planning tools (requisition worksheets, reorder policies on the SKU at that location) to manage replenishment. The subcontracting extension doesn't create purchase lines or transfer orders for this type — the subcontractor simply draws from available stock. The component location changes to the subcontractor's location.
- **Transfer**: You ship the exact quantity of the component to the subcontractor for each production order. You create transfer orders from the subcontracting purchase order to move materials from your warehouse to the vendor location. The component keeps its original location until the transfer order moves it. You can also create return transfer orders for unused quantities. Learn more in [Create transfer orders](#create-transfer-orders).

> [!NOTE]
> You can set subcontracting types in the production BOM and in released production orders.

## Set up components in master data

To link components to subcontracting operations, set up routing link codes in your routing and production BOM.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routing**, and then choose the related link.
2. Open the routing for the item you want to manufacture.
3. In the line for the subcontracting operation, add the appropriate routing link code.
4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.
5. Open the production BOM for the item you want to manufacture.
6. In the line for the component to provide for subcontracting, add the routing link code from the subcontracting operation.
7. In the **Subcontracting Type** field, select the type. Learn more in [About subcontracting types](#about-subcontracting-types).

## Change subcontracting types in production orders

You can change the subcontracting type on components in released production orders.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. On the production order lines, select the line.
4. Choose the **Components** action.
5. In the routing link code field, enter the appropriate code.
6. In the **Subcontracting Type** field, select or change the type.

## How locations are assigned to components

When you create production orders, [!INCLUDE [prod_short](includes/prod_short.md)] automatically assigns locations to components based on your setup and the subcontracting type.

### Initial assignment

When [!INCLUDE [prod_short](includes/prod_short.md)] explodes the production BOM to create component lines, it determines the component location using the following priority:

1. **Stockkeeping unit (SKU) for the finished good**: [!INCLUDE [prod_short](includes/prod_short.md)] looks up the SKU for the *parent item on the production order line* (not the component item) at the production order line's location. If the SKU's **Components at Location** field has a value, components use that location.
2. **Manufacturing Setup**: If the SKU doesn't exist or its **Components at Location** field is blank, [!INCLUDE [prod_short](includes/prod_short.md)] uses the **Components at Location** field from the **Manufacturing Setup** page.
3. **Production order line location**: If both the SKU and Manufacturing Setup fields are blank, components use the same location as the production order line.

### Location changes by subcontracting type

When you set or change the subcontracting type, [!INCLUDE [prod_short](includes/prod_short.md)] adjusts the component location automatically:

- **Purchase with Service and Inventory by Vendor**: The location changes to the **Subcontracting Location Code** specified on the vendor card, because the components are consumed at the subcontractor's site.
- **Transfer**: The component keeps the location from the initial assignment (based on the SKU, manufacturing setup, or production order line priority). [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order later to move the component to the subcontractor.

### Planning components

During demand planning, [!INCLUDE [prod_short](includes/prod_short.md)] assigns locations the same way:

- **Purchase subcontracting type**: The location is set to the subcontracting location of the vendor.
- **Transfer subcontracting type**: The location remains at the standard location.

## Create transfer orders

For components with the **Transfer** subcontracting type, you create transfer orders to move materials from your warehouse to the subcontractor.

### Prerequisites

Before you create a transfer order, the following must be in place:

- A purchase order with subcontracting. Learn more in [Order subcontracting from production orders](subcontract-order.md) or [Use the subcontracting worksheet](subcontract-worksheet.md).
- Production order components with the **Transfer** subcontracting type.
- Transfer routes between locations (optional, if not configured, direct transfers are used). Learn more in [Set up locations for subcontracting](subcontract-location-management.md#set-up-transfer-routes).
- A **Subcontracting Location Code** on the vendor card.

### Create a transfer order from a purchase order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the subcontracting purchase order.
3. Choose the **Create Transfer Order for Subcontracting** action.

[!INCLUDE [prod_short](includes/prod_short.md)] opens the **Transfer Order** page. On the **General** FastTab, you can see the source and destination locations, which are filled in automatically.

> [!NOTE]
> You must choose the action to create transfer orders — the process isn't automated.

### How locations are determined for transfer orders

[!INCLUDE [prod_short](includes/prod_short.md)] automatically determines the locations:

- **Transfer-from**: The location of the production order component. If you change the component location after creating the transfer order, [!INCLUDE [prod_short](includes/prod_short.md)] automatically uses the new location.
- **Transfer-to**: The **Subcontracting Location Code** from the vendor card.

### Use direct transfers

When [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order for subcontracting (both outbound and return orders), it checks the transfer route between the two locations:

- If a transfer route exists and has an **In-Transit Code**, [!INCLUDE [prod_short](includes/prod_short.md)] creates a regular transfer order that uses the transit location.
- If no transfer route exists, or the route doesn't have an **In-Transit Code**, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates a **direct transfer** order instead.

### How receipt dates are calculated

[!INCLUDE [prod_short](includes/prod_short.md)] automatically calculates the receipt date in the transfer order using the following formula:

   **Receipt Date = Due date of the production order component - Subcontracting Inbound Whse. Handling Time**

The **Subcontracting Inbound Whse. Handling Time** is defined on the **Manufacturing Setup** page.

### Use the Subcontracting Details FactBox

On the transfer order, the **Subcontracting Details** FactBox shows the related purchase order, production order, routing operations, and components for the selected transfer line. Choose a value to open the related document or list.

### Post a transfer order

You can post the transfer order using one of the following methods:

- Post from the **Transfer Order** page.
- Post through warehouse shipments.
- Post through picking.

After you post the transfer order, [!INCLUDE [prod_short](includes/prod_short.md)] changes the status in the **Operation Status** field in the production order routing to **In Process**.

### Access transfer entries

You can access posted subcontracting transfer entries from the production order.

1. On the production order, choose the **Subcontracting Transfer Entries** action.

[!INCLUDE [prod_short](includes/prod_short.md)] displays the **Item Ledger Entries** page, where you can view all processes and details of the transfer.

## Create a return from the subcontractor

If the subcontractor didn't completely consume the provided components, you can transfer the unused quantities back to your source location.

1. On the purchase order, choose the **Create Return from Subcontractor** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] opens the **Transfer Order** page. The **Transfer-from** location is the vendor's subcontracting location. The **Transfer-to** location is your original source location.

2. The components with the **Transfer** subcontracting type are available for transfer in the lines. In the lines, enter the quantities you want to post with this transfer order.
3. Post the transfer order from the **Transfer Order** page, through warehouse shipments, or through picking.

### How return quantities are calculated

[!INCLUDE [prod_short](includes/prod_short.md)] automatically calculates the maximum quantity you can return for each component. The calculation considers:

- Components in transit to the subcontractor (shipped but not yet received).
- Components that arrived at the subcontractor and haven't been consumed yet.
- Components already on a return transfer order or in transit back.
- The quantity still needed for remaining production (based on outstanding purchase order quantity).

The return quantity is the lesser of what's physically available at the subcontractor and what's no longer needed for production.

**Example:** You ordered 100 units from the subcontractor. The BOM requires 2 kg of steel per unit, so you transferred 200 kg to the subcontractor.

- The subcontractor delivered 80 units (you posted receipt for 80), consuming 160 kg.
- Remaining at subcontractor: 40 kg.
- Outstanding purchase order quantity: 20 units, which need 40 kg.
- **Return quantity: 40 kg** (the lesser of 40 kg available and 40 kg needed).

If you cancel the remaining 20 units on the purchase order, the outstanding quantity drops to zero, and the return quantity also becomes zero — because no production remains to justify a return.

> [!NOTE]
> When the subcontractor delivers the finished goods (you post the purchase receipt), [!INCLUDE [prod_short](includes/prod_short.md)] automatically reduces the components available for return. Only unconsumed components can be returned.

### One return per purchase order line

You can create one return transfer order per purchase order line. If you try to create a second return for the same line, you receive the error message: "The Return from Subcontractor has already been created."

If you need to return a different quantity, delete the existing return transfer order (if it hasn't been posted) and create a new one.

## Set up flushing for subcontracting components

If a component is used for subcontracting, we recommend that you set its flushing method to **Backward** in the stockkeeping unit card for the subcontracting location.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Stockkeeping Units**, and then choose the related link.
2. Open the stockkeeping unit card for the subcontracting location.
3. On the **Replenishment** FastTab, in the **Flushing Method** field, choose **Backward**.

When you use backward flushing, [!INCLUDE [prod_short](includes/prod_short.md)] automatically consumes the material in the subcontracting warehouse without requiring additional posting.

## Restrictions and validations

[!INCLUDE [prod_short](includes/prod_short.md)] applies the following restrictions to help ensure data consistency.

### Location changes after transfer orders

After [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order for a production order component:

- You can't change the component location.
- You receive the error message: "The component has already been assigned to the subcontracting transfer order."

### Item tracking restrictions

When transfer orders exist for a component:

- You can't open item tracking lines.
- You receive the error message: "You cannot open Tracking Specification because this component is already specified in Transfer Order [Number]."

### Bin code management

[!INCLUDE [prod_short](includes/prod_short.md)] manages bin codes automatically:

- When it creates transfer orders, it saves the original bin code.
- When you delete the transfer order, it restores the location and bin code to the original values.

## Related information

[Manage locations in subcontracting](subcontract-location-management.md)  
[Set up subcontracting](subcontract-setup.md)  
[Assign item charges to subcontracting receipts](subcontract-item-charges.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
