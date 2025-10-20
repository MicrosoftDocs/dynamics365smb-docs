---
title: Purchase receipt testing without warehouse tracking
description: Learn how to set up and use automatic quality inspection test creation for purchase receipts in locations without warehouse handling.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Purchase receipt testing without warehouse tracking

This article explains how to set up and use automatic quality inspection test creation for purchase receipts in locations without warehouse handling (like the Silver location in Contoso demo data).

## Overview

For locations without warehouse handling, quality tests are created automatically when purchase receipts are posted directly. This simpler workflow is ideal for:

- Smaller operations without complex warehouse management
- Locations with bin management but no warehouse documents
- Quick receipt and inspection processes

## Prerequisites

- Quality inspection template configured
- Test generation rule set up for purchase receipts
- Item with lot tracking (recommended)
- Location without warehouse receipt handling

## Setup Requirements

### 1. Create Quality Inspection Template

If not already created, set up a template for incoming inspections:

1. Navigate to **Quality Inspection Templates**
2. Create new template (e.g., "EXAMPLE")
3. Add measurement fields with pass/fail criteria

**Example Configuration**:

- **Field Name**: "Example Measurement"
- **Allowed Values**: 5 to 90
- **Pass Values**: 10 to 20

### 2. Configure Test Generation Rule

Set up a rule to automatically create tests for purchase receipts:

#### Method 1: Manual Rule Creation

1. Navigate to **Test Generation Rules**
2. Create new rule
3. Configure:
   - **Source Type**: Purchase Line
   - **Template Code**: Select your template
   - **Purchase Trigger**: "When Purchase Order is Received"
   - **Item Filter**: Specify items requiring testing

#### Method 2: Using Create Receiving Rule

1. From template or test generation rules, choose **Create Receiving Rule**
2. Select your template
3. Configure filters:
	**Item Number Filter**: Specify items (e.g., "WRB-1002")
    **Location Filter**: Leave blank or specify location
4. Set **Purchase Trigger**: "When Purchase Order is Received"

### 3. Verify Location Configuration

Ensure your location is properly configured:

- Location should not require warehouse receipts
- Location may have bins configured
- Verify location supports item tracking if needed

## Creating Tests Through Purchase Receipt

### Step 1: Create Purchase Order

1. Navigate to **Purchase Orders**
2. Create new purchase order
3. Configure:
   - **Vendor**: Select appropriate vendor
   - **Item**: Choose item configured in test generation rule
   - **Location**: Use location without warehouse handling (e.g., Silver)
   - **Quantity**: Enter quantity to receive

### Step 2: Configure Item Tracking (If Applicable)

For lot-tracked items:

1. Access **Item Tracking Lines**
2. Enter lot numbers:
   - Use existing lot numbers or create new ones
   - Assign quantities to each lot
   - Set expiration dates as needed
3. Specify bin codes if location uses bins

### Step 3: Post Purchase Receipt

1. **Release** the purchase order if needed
2. Choose **Post** from the purchase order
3. Select **Receive** (or **Receive and Invoice**)
4. Confirm posting

### Result: Automatic Test Creation

When the purchase receipt posts:

- Quality inspection tests are created automatically
- One test per lot number (if item tracking is used)
- Tests may open automatically (depending on setup configuration)

## Working with Created Tests

### Accessing Tests

Tests can be accessed through:

1. **Quality Inspection Tests** page (view all tests)
2. **Show Tests for Item and Document** from the purchase order
3. Automatic popup (if configured in **Quality Inspection Setup**)

### Test Information

Each created test contains:

- **Item Number**: The purchased item
- **Lot Number**: Specific lot being tested (if applicable)
- **Quantity**: Quantity from item tracking line
- **Source Document**: Reference to originating purchase order
- **Template Fields**: Measurements to be completed

### Completing the Test

1. Open the quality inspection test
2. Enter measurement values in template fields
3. Review calculated grade (determined by template configuration and measurement results)
4. **Finish** the test when complete

## Configuration Options

### Test Display Behavior

In **Quality Inspection Setup**, configure **Show Test Behavior**:

- **Automatically and Manually Created Tests**: Tests open immediately when created
  - Good for demonstrations and training
  - Convenient for immediate inspection workflow

- **Only Manually Created Tests**: Tests create in background
  - Recommended for production environments
  - Separates receipt posting from inspection roles

### Trigger Configuration

Configure when tests are created:

- **Automatic Only**: Tests always create on receipt posting
- **Manual or Automatic**: Tests can be created automatically or manually
- **Manual Only**: Tests must be created manually using buttons

## Troubleshooting

### Tests Not Creating Automatically

- Verify test generation rule is properly configured
- Check item filter matches purchased item
- Ensure purchase trigger is set correctly
- Confirm template is assigned to rule

### Tests Creating for Wrong Items

- Review item filters in test generation rules
- Check for overlapping rules
- Verify rule priority and ordering

### Test Data Missing

- Confirm item tracking is properly configured
- Verify lot numbers are assigned before posting
- Check bin assignments if location requires bins

## Related information

[Purchase Receipt Testing With Warehouse Tracking](qms-purchase-receipt-testing-warehouse.md)  
[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Test Generation Rules](qms-test-generation-rules.md)  
[Manual Test Creation](qms-manual-test-creation.md)  
[Quality Management Overview](qms-overview.md)