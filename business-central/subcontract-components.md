---
title: Manage components in subcontracting
description: Learn how component supply methods determine how you handle components, assign locations, create transfer orders and returns, and how flushing works.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, components, production BOM, routing, flushing, transfer order, location
ms.search.form: 99000886, 99000818, 99001503, 99000788
ms.date: 07/08/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Manage components in subcontracting

When you subcontract manufacturing operations, you must have components available at the right location. That location is either the subcontractor's site or your own warehouse. This article explains the component supply methods that control how you handle components, assign locations, and use transfer orders to move materials to and from subcontractors.

## About component supply methods

The component supply method on a component determines where the component is consumed and how it gets there. Set the method in the production BOM (for master data) or directly on components in released production orders.

Use these three component supply methods:

- **Vendor-Supplied**: The subcontractor procures the component directly and provides it alongside the manufacturing service. [!INCLUDE [prod_short](includes/prod_short.md)] automatically adds a purchase line for the component on the subcontracting purchase order. You don't supply the material, the vendor does. The component location changes to the subcontractor's location.
- **Consignment at Vendor**: The component is already physically at the subcontractor's location, available for them to consume. The components are your property, and you're responsible for keeping that location stocked. For example, you can ship materials in bulk or purchase directly to the vendor's location. Use standard [!INCLUDE [prod_short](includes/prod_short.md)] planning tools, such as requisition worksheets and reorder policies on the SKU at that location, to manage replenishment. The subcontracting extension doesn't create purchase lines or transfer orders for this method. The subcontractor draws from available stock. The component location changes to the subcontractor's location.
- **Transfer to Vendor**: You ship the exact quantity of the component to the subcontractor for each production order. You create transfer orders from the subcontracting purchase order to move materials from your warehouse to the vendor location. The component keeps its original location until the transfer order moves it. You can also create return transfer orders for unused quantities. Learn more in [Create transfer orders](#create-transfer-orders).

> [!NOTE]
> You can set component supply methods in the production BOM and in released production orders.

## Set up components in master data

To link components to subcontracting operations, set up routing link codes in your routing and production BOM.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routing**, and then choose the related link.
1. Open the routing for the item you want to manufacture.
1. In the line for the subcontracting operation, add the appropriate routing link code.
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.
1. Open the production BOM for the item you want to manufacture.
1. In the line for the component to provide for subcontracting, add the routing link code from the subcontracting operation.
1. In the **Component Supply Method** field, select the method. 

## Change component supply methods in production orders

You can change the component supply method on components in released production orders.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
1. Open the production order.
1. On the production order lines, select the line.
1. Choose the **Components** action.
1. In the routing link code field, enter the appropriate code.
1. In the **Component Supply Method** field, select or change the method.

## Set up flushing for subcontracting components

If a component is used for subcontracting, set its flushing method to **Backward** in the stockkeeping unit card for the subcontracting location.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Stockkeeping Units**, and then choose the related link.
1. Open the stockkeeping unit card for the subcontracting location.
1. On the **Replenishment** FastTab, in the **Flushing Method** field, choose **Backward**.

When you use backward flushing, [!INCLUDE [prod_short](includes/prod_short.md)] automatically consumes the material in the subcontracting warehouse without requiring other posting.

## How locations are assigned to components in production order

When you create production orders, [!INCLUDE [prod_short](includes/prod_short.md)] automatically assigns locations to components based on your setup and the component supply method.

### Initial assignment

When [!INCLUDE [prod_short](includes/prod_short.md)] explodes the production BOM to create component lines, it determines the component location using the following priority:

1. **Stockkeeping unit (SKU) for the finished good**: [!INCLUDE [prod_short](includes/prod_short.md)] looks up the SKU for the *parent item on the production order line* (not the component item) at the production order line's location. If the SKU's **Components at Location** field has a value, components use that location.
1. **Manufacturing Setup**: If the SKU doesn't exist or its **Components at Location** field is blank, [!INCLUDE [prod_short](includes/prod_short.md)] uses the **Components at Location** field from the **Manufacturing Setup** page.
1. **Production order line location**: If both the SKU and Manufacturing Setup fields are blank, components use the same location as the production order line.

### Location changes by component supply method

When you set or change the component supply method, [!INCLUDE [prod_short](includes/prod_short.md)] adjusts the component location automatically:

- **Vendor-Supplied** and **Consignment at Vendor**: The location changes to the **Subcontracting Location Code** specified on the vendor card, because the components are consumed at the subcontractor's site.
- **Transfer to Vendor**: The component keeps the location from the initial assignment (based on the SKU, manufacturing setup, or production order line priority). [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order later to move the component to the subcontractor.

### Planning components

During demand planning, [!INCLUDE [prod_short](includes/prod_short.md)] assigns locations the same way:

- **Vendor-Supplied supply method**: The location is set to the subcontracting location of the vendor.
- **Transfer to Vendor supply method**: The location remains at the standard location.

## Create transfer orders

For components with the **Transfer to Vendor** component supply method, you create transfer orders to move materials from your warehouse to the subcontractor.

### Prerequisites

Before you create a transfer order, the following things must be in place:

- A **Subcontracting Location Code** on the vendor card.
- Transfer routes with an **In-Transit Code** between locations (recommended). If you don't configure this code, [!INCLUDE [prod_short](includes/prod_short.md)] uses direct transfers, which have limitations with advanced warehouse locations. For more information, see [Set up transfer routes](subcontract-location-management.md#set-up-transfer-routes) and [Supported combinations for component transfers](#supported-combinations-for-component-transfers).
- Production order components with the **Transfer to Vendor** component supply method.
- A purchase order with subcontracting. Learn more in [Order subcontracting](subcontract-order.md).

### Create a transfer order from a purchase order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
1. Open the subcontracting purchase order.
1. Choose the **Create Transf. Ord. to Subcontractor** action.

[!INCLUDE [prod_short](includes/prod_short.md)] opens the **Transfer Order** page. On the **General** FastTab, you can see the source and destination locations, which are filled in automatically.

When [!INCLUDE [prod_short](includes/prod_short.md)] creates the transfer order, it saves each component's original location code and bin code. If you later delete the transfer order before posting, [!INCLUDE [prod_short](includes/prod_short.md)] restores the location code and bin code to their original values on the production order component.

### How locations are determined for transfer orders

[!INCLUDE [prod_short](includes/prod_short.md)] automatically determines the locations:

- **Transfer-from**: The location of the production order component.
- **Transfer-to**: The **Subcontracting Location Code** from the vendor card.

### Use direct transfers

When [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order for subcontracting (both outbound and return orders), it checks the transfer route between the two locations:

- If a transfer route exists and has an **In-Transit Code**, [!INCLUDE [prod_short](includes/prod_short.md)] creates a regular transfer order that uses the transit location.
- If no transfer route exists, or the route doesn't have an **In-Transit Code**, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates a **direct transfer** order instead.

### Supported combinations for component transfers

The following table shows which transfer modes work for components depending on the warehouse handling at the transfer-from and transfer-to locations.

|Transfer mode|Direction|No warehouse handling|Require Pick / Put-away|Require Shipment / Receive|Directed Put-away and Pick|
|---|---|---|---|---|---|
|In-Transit (recommended)|Send to subcontractor|Supported|Supported|Supported|Supported|
|In-Transit (recommended)|Receive from subcontractor|Supported|Supported|Supported|Supported|
|Direct – Shipment and Receipt|Send to subcontractor|Supported|Supported|Supported|Supported|
|Direct – Shipment and Receipt|Receive from subcontractor|Supported|Not supported|Not supported|Not supported|
|Direct – Direct Transfer|Send to subcontractor|Supported|Supported|Supported|Supported|
|Direct – Direct Transfer|Receive from subcontractor|Supported|Partial (1)|Not supported|Not supported|

(1) Inventory Put-away creation isn't supported. Post directly from the transfer order as a workaround.

> [!IMPORTANT]
> **Sending** components to subcontractors works in all transfer modes and warehouse configurations. **Receiving** components back (returns) fails with direct transfers when the destination location requires inbound warehouse handling (Require Receive, Require Put-away, or Directed Put-away and Pick).
>
> To ensure component returns work reliably, set up transfer routes with an **In-Transit Code** between your subcontractor locations and the destination warehouse. Also review the **Direct Transfer Posting** field on the **Inventory Setup** page.

### How receipt dates are calculated

[!INCLUDE [prod_short](includes/prod_short.md)] automatically calculates the receipt date in the transfer order by using the following formula:

   **Receipt Date = Due date of the production order component - Subcontracting Component Transfer Lead Time**

You define the **Subcontracting Component Transfer Lead Time** on the **Manufacturing Setup** page.

### Use the Subcontracting Details FactBox

On the transfer order, the **Subcontracting Details** FactBox shows the related purchase order, production order, routing operations, and components for the selected transfer line. Select a value to open the related document or list.

### Access transfer entries

You can access posted subcontracting transfer entries from the production order.

- On the production order, choose the **Subcontracting Transfer Entries** action.

[!INCLUDE [prod_short](includes/prod_short.md)] displays the **Item Ledger Entries** page, where you can view all processes and details of the transfer.

## Create a return from the subcontractor

If the subcontractor didn't completely consume the provided components, you can transfer the unused quantities back to your source location.

- On the purchase order, choose the **Create Return from Subcontractor** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] opens the **Transfer Order** page. The **Transfer-from** location is the vendor's subcontracting location. The **Transfer-to** location is your original source location.

When you post the return transfer order, [!INCLUDE [prod_short](includes/prod_short.md)] restores the component's location code and bin code to their original values on the production order component. If you delete the return transfer order instead of posting it, [!INCLUDE [prod_short](includes/prod_short.md)] also restores the original values.

### How return quantities are calculated

[!INCLUDE [prod_short](includes/prod_short.md)] calculates the return quantity
for each component as the lesser of:

- **Physically available at the subcontractor**: components in transit to the subcontractor (shipped but not yet received), plus components that arrived and aren't consumed, minus quantities already on a return transfer order or in transit back.
- **Quantity needed for outstanding production**: the outstanding quantity on the purchase order line multiplied by the quantity per from the production BOM.

**Example:** You ordered 10 units from a subcontractor. The BOM requires 1 component
per unit, so you transferred 10 components.

| Scenario | Received | Outstanding | Available | Return qty |
|---|---|---|
| No receipts posted | 0 | 10 | 10 | 10 |
| Reduce purchase order to 8 | 0 | 8 | 10 | 8 |
| Receive 4 of 10 | 4 | 6 | 6 | 6 |
| Receive 4, then reduce to 4 | 4 | 0 | 6 | 0 |

> [!NOTE]
> When the outstanding purchase order quantity is zero, the return quantity is also zero even if unconsumed components remain at the subcontractor.

### One return per purchase order line

You can create one return transfer order per purchase order line. If you try to create a second return for the same line, you receive the error message: "The Return from Subcontractor has already been created."

If you need to return a different quantity, delete the existing return transfer order (if it isn't posted) and create a new one.

## Restrictions and validations

[!INCLUDE [prod_short](includes/prod_short.md)] protects fields on subcontracting documents after you transfer components or WIP items to the subcontractor (or while transfer orders exist). This protection prevents inventory discrepancies between what is physically at the vendor and what the system expects.

### Transfer line restrictions

After you link a transfer line to a production order, you can't change the following fields on that line:

- **Quantity**
- **Item No.**
- **Variant Code**

This restriction applies to both outbound transfers (to the subcontractor) and return transfers (from the subcontractor). 

### Transfer header restrictions

You can't change the **Transfer-from Code** or **Transfer-to Code** fields on a subcontracting transfer order if any of its lines are linked to a production order.

### Component restrictions

When a component with the **Transfer to Vendor** component supply method has transfer orders or stock at the subcontractor location, you can't change the following fields:

- **Location Code**
- **Bin Code**
- **Item No.**
- **Variant Code**
- **Expected Quantity**
- **Component Supply Method** (changing away from Transfer to Vendor)

### Item tracking restrictions

You can't open item tracking lines when transfer orders exist for a component.

## Related information

[Manage locations in subcontracting](subcontract-location-management.md)  
[Set up subcontracting](subcontract-setup.md)  
[Assign item charges to subcontracting receipts](subcontract-item-charges.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
