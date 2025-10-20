---
title: Purchase receipt testing with warehouse tracking
description: Learn how to set up and use automatic quality inspection tests for purchase receipts in warehouse-enabled locations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Purchase receipt testing with warehouse tracking

This article explains how to set up and use automatic quality inspection test creation for purchase receipts in locations with warehouse handling (like the White location in Contoso demo data).

## Overview

For locations with warehouse handling, quality tests are created when warehouse receipts are posted. This workflow integrates with Business Central's warehouse management system and supports:

- Locations requiring warehouse receipts
- Complex warehouse operations with put-aways
- Multiple lot numbers per receipt
- Warehouse tracking and traceability

## Prerequisites

- Quality inspection template configured
- Test generation rule set up for purchase receipts
- Location with warehouse receipt handling enabled
- Items with item tracking (recommended)

## Key Differences from Non-Warehouse Locations

| Feature       | Without Warehouse          | With Warehouse                                |
| ------------- | -------------------------- | --------------------------------------------- |
| Document Flow | Purchase Order → Receipt   | Purchase Order → Warehouse Receipt → Put-away |
| Test Trigger  | Purchase Receipt Posting   | Warehouse Receipt Posting                     |
| Configuration | Same test generation rules | Same test generation rules                    |
| Item Tracking | Direct on purchase order   | Can use lot warehouse tracking                |

## Setup Requirements

### 1. Verify Location Configuration

Ensure your location supports warehouse operations:

1. Navigate to **Locations**
2. Select warehouse-enabled location (e.g., White)
3. Verify **Require Receipt** is enabled
4. Check other warehouse settings as needed

### 2. Use Existing Test Generation Rules

The same test generation rules work for both warehouse and non-warehouse locations:

- **Source Type**: Purchase Line
- **Purchase Trigger**: "When Purchase Order is Received"
- **Template**: Assigned quality inspection template
- **Filters**: Item and location filters as needed

> [!NOTE]
> The "When Purchase Order is Received" trigger works for both direct posting and warehouse receipt posting.*

## Process Flow with Warehouse Handling

### Step 1: Create Purchase Order

1. Navigate to **Purchase Orders**
2. Create new purchase order
3. Configure:
   - **Vendor**: Select vendor
   - **Item**: Choose item in test generation rule
   - **Location**: Use warehouse-enabled location (e.g., White)
   - **Quantity**: Enter quantity to receive

### Step 2: Configure Item Tracking

For lot-tracked items:

1. Access **Item Tracking Lines** on purchase line
2. Enter lot information:
   - **Lot Number**: Create or select lot numbers
   - **Quantity**: Assign quantities to lots
   - **Expiration Date**: Set expiration dates
3. Multiple lots can be configured per line

**Example Configuration**:

- Total Quantity: 123
- Lot A: 23 pieces, expiration date
- Lot B: 100 pieces, expiration date

### Step 3: Create Warehouse Receipt

1. **Release** the purchase order
2. Choose **Create Warehouse Receipt**
3. The warehouse receipt is created with:
   - Total quantity from purchase order
   - Item tracking information transferred
   - Bins assigned based on location setup

### Step 4: Post Warehouse Receipt

1. Navigate to **Warehouse Receipts**
2. Open the created receipt
3. Verify quantities and item tracking
4. Post Receipt

### Result: Automatic Test Creation

When the warehouse receipt posts:

- Quality inspection tests are created automatically
- One test per lot number (if item tracking is used)
- Tests reference the original purchase order
- Put-away documents are created for warehouse operations

## Working with Multiple Lots

### Lot-Based Test Creation

When multiple lots are received:

- Each lot gets its own quality inspection test
- Tests are linked to specific lot numbers
- Quantities reflect lot-specific amounts

**Example**: Receipt with two lots creates two tests:

- Test 1: Lot A, 23 pieces
- Test 2: Lot B, 100 pieces

### Managing Lot Tests

Access lot-specific tests through:

1. **Show Tests for Item and Document** from purchase order
2. **Quality Inspection Tests** filtered by lot number
3. **Lot Number Information** if lot blocking is configured

## Integration with Warehouse Operations

### Put-away Processing

After warehouse receipt posting:

1. **Warehouse Put-aways** are created automatically
2. Put-away documents reference the same lot numbers
3. Quality tests can be completed during or after put-away
4. Lot blocking can prevent movement until tests pass

### Warehouse Tracking

The system maintains full traceability:

- Item tracking follows through warehouse documents
- Quality test results are linked to specific lots
- Warehouse entries reference quality inspection data

## Configuration Considerations

### Item Tracking vs. Lot Warehouse Tracking

**Standard Item Tracking** (Recommended):

- Item tracking defined on purchase order
- Lot numbers transfer to warehouse documents
- Quality tests use purchase order tracking information

**Lot Warehouse Tracking**:

- Lot numbers assigned during warehouse operations
- More complex setup and processing
- Supported but not required for quality testing

### Test Generation Rule Triggers

The same trigger works for both scenarios:

- **"When Purchase Order is Received"** triggers on warehouse receipt posting
- No separate configuration needed for warehouse vs. non-warehouse
- Rules apply consistently across location types

## Troubleshooting

### No Tests Created

- Verify location has **Require Receipt** enabled
- Check test generation rule applies to the item
- Ensure warehouse receipt is actually posted

### Wrong Number of Tests

- Review item tracking configuration
- Check for lot consolidation in warehouse receipt
- Verify test generation rule logic

### Tests Missing Lot Information

- Confirm item tracking is properly configured
- Check lot number transfer to warehouse documents
- Verify item tracking code setup

## Related information

[Purchase Receipt Testing Without Warehouse Tracking](qms-purchase-receipt-testing-simple.md)  
[Warehouse Put-away Testing](warehouse-putaway-testing.md)  
[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Setting Up Test Generation Rules](qms-test-generation-rules.md)  
[Quality Management Overview](qms-overview.md)