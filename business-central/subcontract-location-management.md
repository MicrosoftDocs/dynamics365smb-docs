---
title: Set up locations for subcontracting
description: Learn how to configure subcontracting locations on vendor cards and set up transfer routes between your warehouse and subcontractor locations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, location, transfer routes
ms.search.form: 99000788, 99000818
ms.date: 05/20/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up locations for subcontracting

Each subcontractor needs a location so that [!INCLUDE [prod_short](includes/prod_short.md)] knows where components are consumed or transferred. This article explains how to configure subcontracting locations on vendor cards and set up transfer routes.

To learn more about how locations are assigned to components at runtime, and how transfer orders move materials, go to [Manage components in subcontracting](subcontract-components.md).

## Set up subcontracting locations for vendors

Each subcontractor vendor can be assigned one subcontracting location. This location represents the subcontractor's workshop where components are sent and where output is received. We recommend that you define a separate location for each vendor. The location cannot use warehouse handling features such as bins, picks, or put-aways.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the vendor card for the subcontractor.
3. On the **Shipping** FastTab, in the **Subcontracting Location Code** field, specify the location.

The **Linked to Work Center** field shows whether the vendor is connected to a work center. [!INCLUDE [prod_short](includes/prod_short.md)] creates this link automatically through the **Subcontractor No.** field on the work center card.

## Set up transfer routes

For components with the **Transfer to Vendor** component supply method, set up transfer routes between your locations and the subcontractor locations.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Routes**, and then choose the related link.
2. Create a new route with the following information:
   - **Transfer-from Code**: The location where the component is stored.
   - **Transfer-to Code**: The subcontracting location code from the vendor card.
   - **In-Transit Code**: A transit location for the transfer.

If no transfer route is configured between two locations, [!INCLUDE [prod_short](includes/prod_short.md)] automatically uses a direct transfer (without a transit location) when creating transfer orders.

> [!IMPORTANT]
> If the transfer-from or transfer-to location uses advanced warehouse settings (such as **Require Pick**, **Require Shipment**, **Require Receive**, **Require Put-away**, or **Directed Put-away and Pick**), you must configure a transfer route with an **In-Transit Code**. Direct transfers aren't fully supported with locations that require warehouse handling, and transfer order creation or posting can fail.
>
> We recommend that you always set up transfer routes with an in-transit location, both from your warehouse to each subcontractor location and back. Also review the **Direct Transfer Posting** field on the **Inventory Setup** page to control how direct transfers are posted if some routes don't have an in-transit code.
>
> To learn more about which transfer modes work with each warehouse configuration, go to [Supported combinations for WIP transfers](subcontract-wip-transfers.md#supported-combinations-for-wip-transfers) and [Supported combinations for component transfers](subcontract-components.md#supported-combinations-for-component-transfers).

## Related information

[Manage components in subcontracting](subcontract-components.md)  
[Set up subcontracting](subcontract-setup.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]