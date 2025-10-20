---
title: Production output quality testing
description: Learn how to set up and use automatic quality inspection tests for production output.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Production output quality testing

This article explains how to set up and use automatic quality inspection test creation for production output when posting manufacturing operations.

## Overview

Production output testing creates quality inspection tests automatically when production output is posted. This enables quality control for:
- Finished goods inspection
- In-process quality gates
- Work center-specific testing
- Routing operation validation

## Prerequisites

- Quality inspection template configured
- Production orders with routing operations
- Items with item tracking codes (recommended)
- Production trigger configured in Quality Inspection Setup

## Setup Requirements

### 1. Configure Production Items

Prepare items for production output testing:

**Item Setup**:
   - Configure **Item Tracking Code** (e.g., "LOT ALL")
   - Set **Lot Nos.** series for automatic lot assignment
   - Ensure item has routing assigned

### 2. Configure Production Trigger

Set up global trigger for production output:

1. Navigate to **Quality Inspection Setup**
2. Set **Production Trigger** to:
   - **When Output is Posted**: Create tests automatically

### 3. Create Test Generation Rule

Set up rules for production output testing:
#### Method 1: Create Production Rule (Recommended)
1. From **Quality Inspection Templates** or **Test Generation Rules**
2. Choose **Create Production Rule**
3. Configure:
   - **Template Code**: Select quality template
   - **Source Type**: Production Order Routing Line
   - **Production Trigger**: **"When Output is Posted"**

#### Method 2: Manual Rule Creation
1. Navigate to **Test Generation Rules**
2. Create new rule with:
   - **Source Type**: Production Order Routing Line
   - **Template Code**: Assign template
   - **Production Trigger**: **"When Output is Posted"**
   - **Filters**: Configure as needed

### 4. Configure Rule Filters (Optional)

Add filters to control when tests are created:

**Common Filter Options**:
- **Location Code**: Specific production locations
- **Routing No.**: Specific routing operations
- **Work Center No.**: Specific work centers
- **Item No.**: Specific production items

**Example Filter**:
- **Location Code**: WHITE (for White location only)
- Leave other filters blank for broader application

## Creating Production Output Tests

### Step 1: Create Production Order

1. Navigate to **Production Orders**
2. Create new production order:
   - **Item**: Use lot-tracked production item
   - **Quantity**: Production quantity
   - **Location**: Match test generation rule filters
   - **Routing**: Verify routing operations exist

### Step 2: Review Production Order

Verify production order setup:
1. Check **Routing** has operations configured
2. Confirm **Location Code** is set appropriately
3. Review expected output operations

### Step 3: Post Production Output

#### Option 1: Using Production Journal
1. Navigate to **Production Journal**
2. Enter output posting:
   - **Item No.**: Production item
   - **Output Quantity**: Quantity being output
   - **Operation No.**: Final routing operation
3. Configure **Item Tracking** (assign lot number)
4. **Post** the journal

#### Option 2: Using Output Journal
1. Navigate to **Output Journal**
2. Similar process to production journal
3. Post output for specific operations

### Result: Automatic Test Creation

When production output is posted:
- Quality inspection test is created automatically
- Test includes:
  - **Item Number**: Production item
  - **Lot Number**: Assigned lot number
  - **Quantity**: Output quantity
  - **Source**: Production order and operation reference

## Working with Production Tests

### Test Information

Production output tests contain:
- **Control Information**: Source production order details
- **Item Tracking**: Lot/serial number information
- **Template Fields**: Quality measurements to complete
- **Quantity**: Specific to output posting

### Navigation and Traceability

Access related information through:
1. **Navigate** function in test to find:
   - Item ledger entries
   - Production order details
   - Warehouse entries
   - Related documents

2. **Control Information** shows:
   - Source production order
   - Operation details
   - Posting information

### Completing Production Tests

1. Open quality inspection test
2. Enter measurement values
3. Review calculated grade (determined by template configuration and measurement results)
4. **Finish** test when complete

## Advanced Configuration

### Location-Specific Rules

Create multiple rules for different locations:

**Rule 1: White Location**
- **Location Filter**: WHITE
- **Template**: White Location Template

**Rule 2: Silver Location**
- **Location Filter**: SILVER  
- **Template**: Silver Location Template

### Operation-Specific Testing

Configure testing for specific routing operations:
- **Routing No. Filter**: Specific routing
- **Work Center Filter**: Specific work center
- **Operation Filter**: Specific operation number

### Multi-Stage Testing

Set up testing at different production stages:
- **Assembly Operation**: Basic assembly checks
- **Wiring Operation**: Electrical verification
- **Testing Operation**: Final quality validation

## Production Setup Considerations

### Posting Setup Requirements

Ensure proper posting setup exists:
- **Inventory Posting Setup**: For item transactions
- **Manufacturing Posting Setup**: For production costs
- **Work Center Posting**: For operation posting

### Item Tracking Integration

Production output with item tracking:
- **Lot Numbers**: Automatically assigned or manually entered
- **Serial Numbers**: Supported for serialized items
- **Package Numbers**: Supported for package tracking

### Backflushing Considerations

When using backflushing:
- Material consumption posts automatically
- Component lot tracking may affect test creation
- Review backflushing setup for quality integration

## Troubleshooting

### Tests Not Creating
- Verify production trigger is set to "When Output is Posted"
- Check test generation rule filters
- Ensure template is properly assigned
- Confirm output posting actually occurred

### Missing Item Tracking
- Verify item tracking code is configured
- Check lot number assignment during output
- Ensure item tracking is posted with output

### Posting Setup Errors
- Configure required posting setups
- Check inventory posting groups
- Verify manufacturing posting setup

## See Also

- [Creating Quality Inspection Templates](1.4-quality-templates.md)
- [Setting Up Test Generation Rules](1.5-test-generation-rules.md)
- [Manual Test Creation](2.4-manual-test-creation.md)
- [Lot Blocking and Unblocking](3.1-lot-blocking-unblocking.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)