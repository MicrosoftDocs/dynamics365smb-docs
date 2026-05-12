---
title: Manage locations in subcontracting
description: Learn how to configure component locations and transfer routes for subcontracting operations between your warehouse and subcontractor locations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, location, transfer routes, components
ms.search.form: 99000886,
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Manage locations in subcontracting

You can manage locations for subcontracting to control where components come from and how they're transferred between your warehouse and subcontractor locations. Location management helps you track inventory at different sites and ensures that components are available where they're needed.

## Set up default component locations

You can specify which location [!INCLUDE [prod_short](includes/prod_short.md)] uses by default to provide components for subcontracting.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Setup**, and then choose the related link.
2. On the **Purchase Provisions** FastTab, in the **Components at Location** field, choose one of the following options:

|Option|Description|
|------|----------|
|**Purchase**|Components come from the standard purchase location. [!INCLUDE [prod_short](includes/prod_short.md)] determines the location automatically.|
|**Company**|Components come from the company location specified in the **Location Code** field on the **Company Information** page.|
|**Manufacturing**|Components come from the manufacturing location specified in the **Components at Location** field on the **Manufacturing Setup** page.|

> [!NOTE]
> If you choose **Company** or **Manufacturing**, make sure the location code is specified in the respective setup pages.

## Set up subcontracting locations for vendors

Each subcontractor must have a location for subcontracting operations. We recommend that you create a separate location for each subcontractor to keep inventories separate.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the vendor card for the subcontractor.
3. On the **Shipping** FastTab, in the **Subcontracting Location Code** field, specify the location.

The **Linked to Work Center Group No.** field shows whether the vendor is connected to a work center group. [!INCLUDE [prod_short](includes/prod_short.md)] creates this link automatically through the **Subcontractor No.** field in the work center group.

## How locations are assigned to production order components

When you create production orders, [!INCLUDE [prod_short](includes/prod_short.md)] automatically assigns locations to components based on your setup and the subcontracting type.

### Initial assignment

When [!INCLUDE [prod_short](includes/prod_short.md)] explodes the production BOM to create component lines, it determines the component location using the following priority:

1. **Stockkeeping unit (SKU) for the finished good**: [!INCLUDE [prod_short](includes/prod_short.md)] looks up the SKU for the *parent item on the production order line* (not the component item) at the production order line's location. If the SKU's **Components at Location** field has a value, components use that location.
2. **Manufacturing Setup**: If the SKU doesn't exist or its **Components at Location** field is blank, [!INCLUDE [prod_short](includes/prod_short.md)] uses the **Components at Location** field from the **Manufacturing Setup** page.
3. **Production order line location**: If both the SKU and Manufacturing Setup fields are blank, components use the same location as the production order line.


When you change the subcontracting type, [!INCLUDE [prod_short](includes/prod_short.md)] adjusts the location accordingly.

### The Purchase subcontracting type

When you set a component's subcontracting type to **Purchase**:

- [!INCLUDE [prod_short](includes/prod_short.md)] changes the location to the **Subcontracting Location Code** specified on the vendor card.
- The location updates automatically when you change the subcontracting type.

### The Transfer subcontracting type

When you set a component's subcontracting type to **Transfer**:

- The component keeps the location that was assigned during the initial assignment (based on the SKU, Manufacturing Setup, or production order line priority described earlier).
- [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order later to move the component to the subcontractor.

## Set up transfer routes

For components with the **Transfer** subcontracting type, you can set up transfer routes between your locations and the subcontractor locations.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Routes**, and then choose the related link.
2. Create a new route with the following information:
   - **Transfer-from Code**: The location where the component is stored.
   - **Transfer-to Code**: The subcontracting location code from the vendor card.
   - **In-Transit Code**: A transit location for the transfer.

### When direct transfers are used

When [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order for subcontracting (both outbound to the subcontractor and return orders), it checks the transfer route between the two locations:

- If a transfer route exists and has an **In-Transit Code**, [!INCLUDE [prod_short](includes/prod_short.md)] creates a regular transfer order that uses the transit location.
- If no transfer route exists between the locations, or the route doesn't have an **In-Transit Code**, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates a **direct transfer** order instead.

## Validations and restrictions

[!INCLUDE [prod_short](includes/prod_short.md)] applies validations and restrictions to help ensure data consistency.

### Location changes after transfer orders

After [!INCLUDE [prod_short](includes/prod_short.md)] creates a transfer order for a production order component:

- You can't change the component location.
- You receive the error message: "The component has already been assigned to the subcontracting transfer order."

### Bin code management

[!INCLUDE [prod_short](includes/prod_short.md)] manages bin codes automatically:

- When it creates transfer orders, it saves the original bin code.
- When you delete the transfer order, it restores the location and bin code to the original values.

### Item tracking restrictions

When transfer orders exist for a component:

- You can't open item tracking lines.
- You receive the error message: "You cannot open Tracking Specification because this component is already specified in Transfer Order [Number]."

## Location assignment scenarios

The following scenarios show how [!INCLUDE [prod_short](includes/prod_short.md)] assigns locations in different situations.

### Purchase provision without existing data

- **Component location**: From the **Components at Location** field in the setup.
- **Subcontracting location**: From the **Subcontracting Location Code** field on the vendor card.

### Purchase provision with existing bill of materials

- **Component location**: From the **Components at Location** field on the **Manufacturing Setup** page.
- **Adjustment**: Based on the subcontracting type of the components.

### Planning components

During demand planning, [!INCLUDE [prod_short](includes/prod_short.md)] transfers locations automatically:

- **Purchase subcontracting type**: The location is set to the subcontracting location of the vendor.
- **Transfer subcontracting type**: The location remains at the standard location.

> [!IMPORTANT]
> Correct location configuration is important for subcontracting processes to work properly. Incorrect configurations can lead to posting errors and inconsistent inventories.

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Inventory](inventory-manage-inventory.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]