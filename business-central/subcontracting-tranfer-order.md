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
# Create and Post Transfer Order

If you have ordered subcontracting and thus added it to your purchase order, you can create a transfer order for it. With the transfer order, you transfer the components associated with the subcontracting operation.

## Prerequisites

Before you can create a transfer order, the following prerequisites must be met:

- A purchase order with subcontracting must be created
- The production order components must have the subcontracting type "Transfer"
- Transfer routes between locations must be set up
- The vendor must have a "Subcontracting Location Code" in the vendor card

## Create Transfer Order

1. Open the purchase order and mark the desired line.

1. Select "Actions", "Functions" and "Create Transfer Order for Subcontracting" in the ribbon.

1. Subsequently, the "Transfer Order" card opens. From the "General" tab, you can see the location origin and the transfer location based on the code. The field contents are automatically predefined, but you can still override them. The settings, as well as the further process procedure, depend on the settings in the "Location Card".

1. Post the transfer order from the "Transfer Order" card, via warehouse shipments or picking.

1. In the associated production order, or in its routing, the status in the "Operation Status" column was changed to "In Process".

## Location Assignment

The system automatically determines the locations for the transfer order:

### Transfer-from Location
- **Standard:** Location of the production order component
- **Upon Change:** If the component location is changed after creating the transfer order, the new location is automatically used as "Transfer-from"

### Transfer-to Location
- **Subcontracting Location Code** from the vendor card of the assigned subcontractor

## Direct Transfer

In the "Subcontracting Setup", you can activate the "Direct Transfer for Subcontracting" option:

- **Activated:** The transfer occurs without transit location
- **Deactivated:** The transfer occurs via the transit location defined in the transfer route

> [!NOTE]
> With direct transfer, the "Qty. to Receive" field is automatically filled with the same value as "Qty. to Ship".

## Receipt Date Calculation

The receipt date in the transfer order is automatically calculated:

**Formula:** Due date of the production order component - "Subcontracting Inbound Whse. Handling Time"

The "Subcontracting Inbound Whse. Handling Time" is defined in the "Subcontracting Setup".

## View Transfer Entries

To view the posted "Subcontracting Transfer Entries" in the production order, navigate in the production order card via "Related", "Order", "Entries" to "Subcontracting Transfer Entries".

This opens the "Item Ledger Entries" list, where you can view all processes and details of the transfer process.

## Return from Subcontractor

If the provided components were not completely consumed, you have the option to transfer the unused quantities back to your source location with the "Create Return from Subcontractor" action.

1. Select "Actions", "Functions" and "Create Return from Subcontractor" in the ribbon.

1. Subsequently, the "Transfer Order" card opens. In the generated transfer order, the "Transfer-from" location code corresponds to the vendor's location code. Your source location code is used as the "Transfer-to" location code.

1. The components with subcontracting type "Transfer" are offered for transfer in the transfer lines. Enter the quantities in the lines that you want to post with this transfer order.

1. Post the transfer order from the "Transfer Order" card, via warehouse shipments or picking.

### Automatic Location Reversal

During return, the locations are automatically reversed:
- **Transfer-from:** Subcontracting location code of the vendor
- **Transfer-to:** Original location of the component

## Restrictions and Validations

### Location Changes

After creating a transfer order, you can no longer change the location of the assigned production order component. The system shows the error message:\
*"The component has already been assigned to subcontracting transfer order [Order Number]."*

### Item Tracking

If a transfer order has already been created for a production order component, you can no longer open the item tracking lines. The system shows the error message:\
*"You cannot open the tracking specification because the component is already specified in subcontracting transfer order [Order Number]."*

### Bin Code Management

- **Original Bin Code:** Is saved when creating the transfer order
- **After Deletion:** If the transfer order is deleted, the location and bin code of the component are reset to the original values