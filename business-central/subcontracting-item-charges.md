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
# Item Charges for Subcontracting

The Subcontracting Extension offers extended functionalities for handling item charges in subcontracting. This function enables assigning additional costs such as transport, packaging, or other incidental costs directly to subcontracting. Subsequent costs that should still be distributed to the receipts for subcontracting or purchase provisions can be recorded as a separate invoice with Type = "Charge (Item)". The additional costs must therefore be linked to the capacity ledger entries of the production order.


## Activating the Function

The item charge function for subcontracting must be activated in the "Subcontracting Setup":

1. Open the "Subcontracting Setup"
2. Navigate to the "Subcontracting" tab
3. Activate the field "Item Charge to Subcontracting Purch. Receipt Lines"

> [!NOTE]
> After activation, an additional option becomes visible in the charge assignment in purchasing, including the specialized "Get Receipt Lines for Subcontracting" action.

## Functionality

### Normal Item Charge Assignment

In standard charge assignment, item charges are normally assigned to item ledger entries, resulting in the following postings:

- Value entries with reference to item ledger entries
- Cost type: "Direct Cost"
- Inventory impact on items

### Subcontracting Item Charge Assignment

With activated subcontracting function and assignment to a subcontracting receipt line:

- Value entry is created **without** reference to item ledger entry
- Value entry is created **with** reference to capacity ledger entry
- Cost type: "Direct Cost"
- Order type: "Production"
- Invoiced quantity: 0 (as these are capacity costs)

## Application

### Prerequisites

- Subcontracting purchase order must be posted
- Purchase receipt with subcontracting reference must exist
- Item charge must be recorded in separate purchase order

### Step-by-Step Guide

1. **Create and post subcontracting purchase order**
   - Create a normal subcontracting purchase order
   - Post the order (receipt)

2. **Create item charge purchase order or invoice**
   - Create a new purchase order
   - Add a line with type "Charge (Item)"
   - Select the corresponding item charge
   - Enter quantity and unit cost

3. **Configure charge assignment**
   - Open the charge assignment for the item charge line
   - Use the **"Get Receipt Lines for Subcontracting"** action to automatically filter and select subcontracting receipt lines
   - Alternatively, manually select "Receipt" as document type and choose the subcontracting receipt
   - Select the corresponding subcontracting receipt line
   - Enter the quantity and amount to be assigned

4. **Post purchase order**
   - Post the item charge purchase order
   - The system automatically creates the corresponding value entries

## Get Receipt Lines for Subcontracting Action

The "Get Receipt Lines for Subcontracting" action is a specialized tool that simplifies the process of assigning item charges to subcontracting receipt lines.

### How It Works

When you use this action:

1. **Automatic Filtering**: The system automatically filters purchase receipt lines to show only those related to subcontracting operations
2. **Subcontracting Identification**: Only receipt lines with the following fields populated are displayed:
   - Production Order No.
   - Routing No.
   - Operation No.
3. **Simplified Selection**: You can directly select the appropriate subcontracting receipt line without manual filtering

> [!TIP]
> The "Get Receipt Lines for Subcontracting" action is only visible when the "Item Charge to Subcontracting Purch. Receipt Lines" setting is activated in the Subcontracting Setup.

## Impact on Posting

### Value Entry Creation

When posting an item charge assigned to a subcontracting receipt line:

**Standard Fields:**

- Item Ledger Entry No.: 0 (empty)
- Capacity Ledger Entry No.: [Reference to corresponding capacity ledger entry]
- Order Type: Production
- Order No.: [Production order number]
- Invoiced Quantity: 0
- Cost Type: Direct Cost

**Cost Distribution:**

- Item charge costs are directly assigned to the production order
- No impact on item inventories
- Direct assignment to capacity costs

### Difference to Standard Posting

| Aspect | Standard Item Charge | Subcontracting Item Charge |
|--------|---------------------|---------------------------|
| Item Ledger Entry No. | Filled | 0 (empty) |
| Capacity Ledger Entry No. | 0 (empty) | Filled |
| Order Type | Purchase | Production |
| Inventory Impact | Yes | No |
| Cost Distribution | Item | Capacity/Production Order |

## Benefits

### More Accurate Cost Assignment

- Incidental costs are directly assigned to the production order
- No distortion of item costs by subcontracting incidental costs
- Better separation between material and manufacturing costs

### Improved Calculation

- More precise manufacturing cost calculation
- Correct assignment of transport and processing costs
- Better traceability of total subcontracting costs

### Reporting and Analysis

- Separate evaluation of subcontracting incidental costs possible
- Better cost transparency for production orders
- More accurate profitability analysis

## Application Examples

### Example 1: Transport Costs
Subcontracting invoice: €1,000 processing + €50 transport. Transport costs are assigned as item charge to the subcontracting receipt line.

### Example 2: Packaging Costs
Special packaging for sensitive parts: €800 processing + €30 packaging. Packaging costs are assigned as item charge for direct assignment to manufacturing costs.

### Example 3: Testing Costs
Quality testing at subcontractor: €1,200 processing + €100 testing. Testing costs are recorded as item charge for better cost transparency.

## Important Notes

> [!IMPORTANT]
> The function must be activated in the setup before first use. Subsequent activation only affects new postings.

> [!NOTE]
> Item charges assigned to subcontracting receipt lines cannot be reversed once they are posted.

> [!WARNING]
> Ensure that the item charge is assigned to the correct subcontracting receipt line, as this affects cost assignment.

## Monitoring and Control

### Check Value Entries

To control correct posting, you can check the value entries:

1. Open the value entries of the corresponding production order
2. Filter by cost type "Direct Cost"
3. Check if capacity ledger entry no. is filled and item ledger entry no. is empty

### Production Order Costs

The item charge costs appear in the production order cost overview under capacity costs.