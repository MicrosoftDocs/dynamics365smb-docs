---
title: Manage locations in subcontracting
description: Learn how to configure component locations and transfer routes for subcontracting operations between your warehouse and subcontractor locations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Location Management in Subcontracting

Location management is a central component of the Subcontracting Extension. It regulates from which locations components are provided for subcontracting and how they are transferred between different sites.

## Component Location Configuration

In the "Subcontracting Setup" under "Purchase Provisions", you can specify from which location components are provided by default:

### Field "Components at Location"

|Option|Description|Source|
|:--|:--|:--|
|**Purchase**|Components are provided from the standard purchase location|Automatically determined|
|**Company**|Components are provided from the company location|Company Information → Location Code|
|**Manufacturing**|Components are provided from the manufacturing location|Manufacturing Setup → Components at Location|

> [!NOTE]
> When selecting "Company" or "Manufacturing", the corresponding location code must be maintained in the respective setups.

## Subcontracting Location at Vendor

Each subcontractor (vendor) must have a specific location for subcontracting:

### Configure Vendor Card

1. Open the vendor card of the subcontractor
2. Navigate to the "Shipping" tab
3. Fill in the "Subcontracting Location Code" field

**Recommendation:** Create a separate location for each subcontractor to ensure clear separation of inventories.

### Link with Work Center Group

The field "Linked to Work Center Group No." shows whether a vendor is connected to a work center group. This link is automatically created via the "Subcontractor No." field in the work center group.

## Location Assignment for Production Order Components

### Automatic Assignment

When creating production orders, the locations of components are automatically assigned:

**Standard Behavior:**

- Components initially receive the configured standard location
- When changing the subcontracting type, the location is adjusted accordingly

### Subcontracting Type "Purchase"

When a component receives the subcontracting type "Purchase":

- **Location is changed** to the "Subcontracting Location Code" of the assigned vendor
- **Automatic update** when changing the subcontracting type

### Subcontracting Type "Transfer"

When a component receives the subcontracting type "Transfer":

- **Location remains** at the originally configured location
- **Transfer order** is created later to transport the component to the subcontractor

## Transfer Routes

For components with subcontracting type "Transfer", transfer routes must be set up:

### Create Route

1. Open "Transfer Routes"
2. Create a route between:
   - **Transfer-from Code:** Component location
   - **Transfer-to Code:** Subcontracting location code of the vendor
   - **In-Transit Code:** Transit location (optional, depending on "Direct Transfer")

### Direct Transfer

In the setup, you can activate "Direct Transfer for Subcontracting":

- **Activated:** No use of transit locations
- **Deactivated:** Use of the transit location defined in the route

## Location Validations and Restrictions

### Change Protection for Transfer Orders

Once a transfer order has been created for a production order component:

- **Location change blocked:** The component location can no longer be changed
- **Error message:** "The component has already been assigned to the subcontracting transfer order"

### Bin Code Management

The system manages bin codes automatically:

- **Original Bin Code:** Is saved when creating transfer orders
- **Restoration:** When deleting the transfer order, location and bin code are reset to the original values

### Item Tracking Restrictions

With existing transfer orders:

- **Item tracking blocked:** Item tracking lines cannot be opened
- **Error message:** "You cannot open Tracking Specification because this component is already specified in Transfer Order [Number]"

## Location Transfer in Different Scenarios

### Scenario 1: Purchase Provision without Existing Data

- **Component Location:** From setup configuration ("Components at Location")
- **Subcontracting Location:** From vendor ("Subcontracting Location Code")

### Scenario 2: Purchase Provision with Existing BOM

- **Component Location:** From manufacturing setup ("Components at Location")
- **Adjustment:** Depending on subcontracting type of components

### Scenario 3: Planning Components

During demand planning, locations are automatically transferred:

- **Subcontracting Type "Purchase":** Location is set to subcontracting location of vendor
- **Subcontracting Type "Transfer":** Location remains at standard location

> [!IMPORTANT]
> Correct location configuration is essential for the proper functioning of subcontracting processes. Incorrect configurations can lead to posting errors and inconsistent inventories.