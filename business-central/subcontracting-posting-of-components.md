---
title: Subcontract manufacturing
description: This article gives an extended overview of the extended functionality of subcontracting, including work center fields and routing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 06/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Component Posting

If you want to post components in connection with subcontracting, setups must be made in production BOMs and the routing.

## Setup in Master Data

1. Open the routing of the item to be manufactured.

1. Add an appropriate routing link code in the line of the subcontracting operation.

1. Open the production BOM of the item to be manufactured.

1. Add the routing link code of the subcontracting operation in the line of the component to be provided for subcontracting.

1. Select the desired type of subcontracting in the "Subcontracting Type" column (see [Subcontracting Types](#subcontracting-types)).

## Override in Production Order

You can override the component posting or its subcontracting type in the released production order:

1. Select the corresponding line in the released production order.

1. Navigate via the ribbon to "Line" → "Components".

1. Enter the appropriate routing link code.

1. Select the desired type in the "Subcontracting Type" column or override the existing setting (see [Subcontracting Types](#subcontracting-types)).

## Subcontracting Types

Three different subcontracting types are available for component posting:

+ **Purchase with Service**\
  The component item is purchased with the service in a separate purchase line from the vendor. The components are procured directly by the subcontractor and are part of the purchase order.

+ **Inventory by Vendor**\
  The supplier stocks the component item. In case of an order, they use the goods available to them for manufacturing. The components are already at the subcontractor location and do not need to be transported. **Note:** The goods stocked at the supplier are your property.

+ **Transfer**\
  The supplier is provided with the exact quantity of the component item for each order process. The system allows creating transfer orders via action (see [Create Transfer Orders](#create-transfer-orders)) to physically transport the components from the company warehouse to the subcontractor location. During subcontracting (after posting the transfer), the location of the component is temporarily changed to the subcontractor location.

> [!NOTE]
> These subcontracting types can be set both in the master data (production BOM) and directly in the released production orders.

## Automatic Location Changes

The system automatically changes the locations of components in the production order, depending on the selected subcontracting type:

+ **Purchase with Service & Inventory by Vendor**: The component location is changed to the subcontractor location, as the components are consumed there.

+ **Transfer**: The location is reset to the original location, as consumption occurs at the original location.

This automatic change ensures correct inventory management and cost accounting according to physical reality.

> [!IMPORTANT]
> Prerequisite for automatic location change is that the type of production order operation is set to "Work Center Group".

## Create Transfer Orders

For components with subcontracting type "Transfer", transfer orders must be created **manually**:

1. Open the subcontracting purchase order
2. Click the **"Create Transfer Order for Subcontracting"** button
3. The system automatically creates the required transfer orders

> [!IMPORTANT]
> There is no automated process - the button must be pressed manually.
> More information is available in [Create and Post Transfer Order](enhanced-subcontracting-tranfer-order.md).

## Recommendation

If a component is used for subcontracting, it is recommended to set its flushing method in the stockkeeping unit card of the subcontracting location to "Backward". Enter this data in the "Replenishment" tab. This way, the material in the subcontracting warehouse is automatically consumed without additional posting by the user.






## Related information  

[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]