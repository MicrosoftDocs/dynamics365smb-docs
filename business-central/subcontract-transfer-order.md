---
title: Create subcontracting transfer orders
description: Learn how to create and post transfer orders for subcontracting components, including direct transfers and returns from subcontractors.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.forms: 99000886,
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

# Create transfer orders for subcontracting

When you order subcontracting and add it to your purchase order, you can create transfer orders for the components associated with the subcontracting operation.

## Prerequisites

Before you create a transfer order, the following must be in place:

- A purchase order with subcontracting.
- Production order components with the **Transfer** subcontracting type.
- Transfer routes between locations.
- A **Subcontracting Location Code** on the vendor card.

## Create a transfer order

The following steps describe how to create a transfer order for subcontracting.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the purchase order.
3. On the lines, select the line.
4. Choose the **Create Transfer Order for Subcontracting** action.

[!INCLUDE [prod_short](includes/prod_short.md)] opens the **Transfer Order** page. On the **General** FastTab, you can see the location origin and the transfer location. The fields are automatically filled in, but you can change them. The settings and the process depend on the settings on the **Location Card** page.

To post the transfer order, you can use one of the following methods:

- Post from the **Transfer Order** page.
- Post through warehouse shipments.
- Post through picking.

After you post the transfer, [!INCLUDE [prod_short](includes/prod_short.md)] changes the status in the **Operation Status** field in the production order routing to **In Process**.

## Use the Subcontracting Details FactBox

On the transfer order, the **Subcontracting Details** FactBox shows the related purchase order, production order, routing operations, and components for the selected transfer line. Choose a value to open the related document or list.

## How locations are assigned

[!INCLUDE [prod_short](includes/prod_short.md)] automatically determines the locations for the transfer order:

### Transfer-from location

- **Standard** - The location of the production order component.
- **Upon change** - If you change the component location after creating the transfer order, [!INCLUDE [prod_short](includes/prod_short.md)] automatically uses the new location as the **Transfer-from** location.

### Transfer-to location

The **Subcontracting Location Code** from the vendor card of the assigned subcontractor.

## Use direct transfer

You can turn on direct transfer in the **Subcontracting Setup**.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Setup**, and then choose the related link.
2. Turn on the **Direct Transfer for Subcontracting** toggle.

When you use direct transfer:

- The transfer occurs without a transit location.
- The **Qty. to Receive** field is automatically filled with the same value as **Qty. to Ship**.

When the toggle is turned off, the transfer occurs through the transit location defined in the transfer route.

## How receipt dates are calculated

[!INCLUDE [prod_short](includes/prod_short.md)] automatically calculates the receipt date in the transfer order using the following formula:

**Receipt Date = Due date of the production order component - Subcontracting Inbound Whse. Handling Time**

The **Subcontracting Inbound Whse. Handling Time** is defined in the **Subcontracting Setup**.

## Access transfer entries

You can access posted subcontracting transfer entries in the production order.

1. On the production order, choose the **Subcontracting Transfer Entries** action.

[!INCLUDE [prod_short](includes/prod_short.md)] displays the **Item Ledger Entries** page, where you can view all processes and details of the transfer.

## Create a return from the subcontractor

If the subcontractor didn't completely consume the provided components, you can transfer the unused quantities back to your source location.

1. On the purchase order, choose the **Create Return from Subcontractor** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] opens the **Transfer Order** page. In the transfer order, the **Transfer-from** location code is the vendor's location code. Your source location code is used as the **Transfer-to** location code.

2. The components with the **Transfer** subcontracting type are available for transfer in the lines. In the lines, enter the quantities you want to post with this transfer order.
3. Post the transfer order from the **Transfer Order** page, through warehouse shipments, or through picking.

### How locations are reversed for returns

During return, [!INCLUDE [prod_short](includes/prod_short.md)] automatically reverses the locations:

- **Transfer-from** - Subcontracting location code of the vendor.
- **Transfer-to** - Original location of the component.

## Restrictions and validations

[!INCLUDE [prod_short](includes/prod_short.md)] applies the following restrictions and validations.

### Location changes

After you create a transfer order, you can't change the location of the assigned production order component. You receive the error message: "The component has already been assigned to subcontracting transfer order [Order Number]."

### Item tracking

If a transfer order exists for a production order component, you can't open the item tracking lines. You receive the error message: "You cannot open the tracking specification because the component is already specified in subcontracting transfer order [Order Number]."

### Bin code management

[!INCLUDE [prod_short](includes/prod_short.md)] manages bin codes automatically:

- When it creates the transfer order, it saves the original bin code.
- When you delete the transfer order, it resets the location and bin code of the component to the original values.

## Related information

[Set up subcontracting](subcontract-setup.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Transfer inventory between locations](inventory-how-transfer-between-locations.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]