---
title: Set up locations for subcontracting
description: Learn how to configure subcontracting locations on vendor cards and set up transfer routes between your warehouse and subcontractor locations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, location, transfer routes
ms.search.form: 99000886,
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

# Set up locations for subcontracting

Each subcontractor needs a location so that [!INCLUDE [prod_short](includes/prod_short.md)] knows where components are consumed or transferred. This article explains how to configure subcontracting locations on vendor cards and set up transfer routes.

For information about how locations are assigned to components at runtime, and how transfer orders move materials, learn more in [Manage components in subcontracting](subcontract-components.md).

## Set up subcontracting locations for vendors

Each subcontractor must have a location for subcontracting operations. We recommend that you create a separate location for each subcontractor to keep inventories separate.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the vendor card for the subcontractor.
3. On the **Shipping** FastTab, in the **Subcontracting Location Code** field, specify the location.

The **Linked to Work Center Group No.** field shows whether the vendor is connected to a work center group. [!INCLUDE [prod_short](includes/prod_short.md)] creates this link automatically through the **Subcontractor No.** field in the work center group.

## Set up transfer routes

For components with the **Transfer** subcontracting type, set up transfer routes between your locations and the subcontractor locations.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Routes**, and then choose the related link.
2. Create a new route with the following information:
   - **Transfer-from Code**: The location where the component is stored.
   - **Transfer-to Code**: The subcontracting location code from the vendor card.
   - **In-Transit Code**: A transit location for the transfer.

If no transfer route is configured between two locations, [!INCLUDE [prod_short](includes/prod_short.md)] automatically uses a direct transfer (without a transit location) when creating transfer orders.

> [!IMPORTANT]
> Correct location configuration is important for subcontracting processes to work properly. Incorrect configurations can lead to posting errors and inconsistent inventories.

## Related information

[Manage components in subcontracting](subcontract-components.md)  
[Set up subcontracting](subcontract-setup.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]