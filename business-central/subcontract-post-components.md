---
title: Post subcontracting components
description: Learn how to set up and post components for subcontracting operations, including subcontracting types and automatic location changes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, components, production BOM, routing, flushing
ms.search.form: 99000886
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Post subcontracting components

To post components with subcontracting operations, you must set up your production BOMs and routing. This article describes how to configure component posting and work with different subcontracting types.

## Set up component posting in master data

The following steps describe how to set up component posting for subcontracting.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routing**, and then choose the related link.
2. Open the routing for the item you want to manufacture.
3. In the line for the subcontracting operation, add the appropriate routing link code.
4. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Production BOM**, and then choose the related link.
5. Open the production BOM for the item you want to manufacture.
6. In the line for the component to provide for subcontracting, add the routing link code from the subcontracting operation.
7. In the **Subcontracting Type** field, select the type of subcontracting. Learn more about types in [About subcontracting types](#about-subcontracting-types).

## Change component posting in production orders

You can change the component posting or subcontracting type in released production orders.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. On the production order lines, select the line.
4. Choose the **Components** action.
5. In the routing link code field, enter the appropriate code.
6. In the **Subcontracting Type** field, select or change the type.

## About subcontracting types

You can use three different subcontracting types for component posting:

- **Purchase with Service** - The component item is purchased with the service in a separate purchase line from the vendor. The subcontractor procures the components directly, and they're part of the purchase order.
- **Inventory by Vendor** - The vendor stocks the component item. When you place an order, they use the goods they have available for manufacturing. The components are already at the subcontractor location and don't need to be transported. The goods stocked at the vendor are your property.
- **Transfer** - The vendor receives the exact quantity of the component item for each order process. You can create transfer orders to physically transport the components from your warehouse to the subcontractor location. Learn more in [Create transfer orders for subcontracting](#create-transfer-orders-for-subcontracting). When you post the transfer, [!INCLUDE [prod_short](includes/prod_short.md)] temporarily changes the component location to the subcontractor location.

> [!NOTE]
> You can set subcontracting types in the production BOM and in released production orders.

## How location changes work

[!INCLUDE [prod_short](includes/prod_short.md)] automatically changes component locations in production orders based on the subcontracting type you select:

- **Purchase with Service and Inventory by Vendor** - The component location changes to the subcontractor location because the components are consumed there.

- **Transfer** - The location resets to the original location because consumption occurs at the original location.

Automatic location changes ensure correct inventory management and cost accounting according to physical reality.

> [!IMPORTANT]
> For automatic location changes to work, you must set the type of production order operation to **Work Center Group**.

## Create transfer orders for subcontracting

For components with the **Transfer** subcontracting type, you must create transfer orders manually.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the subcontracting purchase order.
3. Choose the **Create Transfer Order for Subcontracting** action.

[!INCLUDE [prod_short](includes/prod_short.md)] creates the required transfer orders. Learn more in [Create transfer orders for subcontracting](subcontract-transfer-order.md).

> [!NOTE]
> The process isn't automated. You must choose the action to create transfer orders.

## Set up flushing for subcontracting components

If a component is used for subcontracting, we recommend that you set its flushing method to **Backward** in the stockkeeping unit card for the subcontracting location.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Stockkeeping Units**, and then choose the related link.
2. Open the stockkeeping unit card for the subcontracting location.
3. On the **Replenishment** FastTab, in the **Flushing Method** field, choose **Backward**.

When you use backward flushing, [!INCLUDE [prod_short](includes/prod_short.md)] automatically consumes the material in the subcontracting warehouse without requiring additional posting.

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
