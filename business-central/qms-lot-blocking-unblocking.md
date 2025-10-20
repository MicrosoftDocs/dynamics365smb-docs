---
title: Lot blocking and unblocking
description: Learn how to block and unblock inventory lots using workflows and grade-specific controls to ensure quality compliance.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Lot blocking and unblocking

This article explains how to automatically block and unblock inventory lots based on quality inspection test results using workflows and grade-specific controls.

## Overview

Quality Management provides two main approaches for lot blocking:

- **Workflow-Based Blocking**: Complete lot blocking using Business Central workflows
- **Grade-Based Blocking**: Document-specific blocking based on test grades

Both approaches help ensure non-compliant inventory cannot be used inappropriately while allowing flexible quality control processes.

## Prerequisites

- **Workflow Integration**: Enable in Quality Inspection Setup
- **Quality Templates**: Configured with pass/fail criteria
- **Test Generation Rules**: Set up for automatic test creation
- **Items**: Configured with lot tracking

## Workflow-Based Lot Blocking

### Overview

Workflow-based blocking creates or modifies **Lot Number Information Cards** to completely block lots for all transactions (except warehouse operations when configured).

### Setting Up Block-on-Fail Workflow

**Scenario**: Block lots when quality tests fail

1. **Create Workflow**:
   - Navigate to **Workflows**
   - Create new workflow: "Block Lot Example"

2. **Configure When Event**:
   - **Event**: When a **Quality Inspection Test is Finished**
   - **Condition**: Grade Code equals **"Fail"**

3. **Configure Response**:
   - **Response**: Block the lot in the test
   - This creates a lot information card with blocked status

### Setting Up Block-on-Creation Workflow

**Scenario**: Block lots immediately when tests are created, unblock when tests pass

#### Workflow 1: Block on Test Creation
1. **Create Workflow**: "Block Lot on Creation"
2. **When Event**: When a **Quality Inspection Test is Created**
3. **Response**: Block the lot in the test
4. **Result**: All lots blocked immediately when tests are created

#### Workflow 2: Unblock on Pass
1. **Create Workflow**: "Unblock on Pass"  
2. **When Event**: When a **Quality Inspection Test is Finished**
3. **Condition**: Grade Code equals "**Pass**"
4. **Response**: Unblock the lot in the test
5. **Result**: Lots unblocked only when tests pass

### Workflow Configuration Requirements

**Enable Workflow Integration**:
1. Navigate to **Quality Inspection Setup**
2. Ensure **Enable Workflow Integration** is enabled
3. Without this setting, workflow events will not be available

## Grade-Based Document Blocking

### Overview

Grade-based blocking provides granular, document-specific controls based on the current grade of quality inspection tests. Unlike complete lot blocking, this approach allows you to block specific transaction types while permitting others, based on the test grade.

### How Grade-Based Blocking Works

**Grade Evaluation**:
- System evaluates current test grades for the lot/serial number
- Transaction permissions are determined by the grade configuration
- Multiple tests for the same lot may have different grades
- System can be configured to consider specific tests when evaluating restrictions

### Configuring Grade Transaction Controls

1. Navigate to **Quality Inspection Grades**
2. Select the grade to configure (e.g., INPROGRESS, FAIL, PASS)
3. Configure transaction permissions for each grade:

**Available Transaction Controls**:
- **Allow Sales**: Enable/disable sales document posting
- **Allow Purchase**: Enable/disable purchase document posting  
- **Allow Transfer**: Enable/disable transfer order posting
- **Allow Consumption**: Enable/disable material consumption in production
- **Allow Pick**: Enable/disable warehouse picks
- **Allow Put-away**: Enable/disable warehouse put-aways
- **Allow Movement**: Enable/disable warehouse movements
- **Allow Output**: Enable/disable production output posting

### Example Grade Configurations

#### INPROGRESS Grade (Priority 0)
**Use Case**: Testing in progress, restrict most transactions
**Business Logic**: Items can be stored and moved for testing but not used in business transactions

- **Allow Sales**: No (cannot sell unconfirmed quality)
- **Allow Transfer**: No (prevent distribution before testing complete)
- **Allow Consumption**: No (cannot use in production)
- **Allow Pick**: No (prevent picking for shipment)
- **Allow Put-away**: Yes (allow warehouse storage)
- **Allow Movement**: Yes (allow movement to testing areas)
- **Allow Output**: Yes (may be acceptable for work-in-progress)

#### FAIL Grade (Priority 1+)
**Use Case**: Failed quality test, quarantine required
**Business Logic**: Block all business use, allow only quarantine and disposition activities

- **Allow Sales**: No (cannot sell non-conforming items)
- **Allow Transfer**: No (prevent distribution of failed items)
- **Allow Consumption**: No (cannot use defective materials)
- **Allow Pick**: No (prevent accidental picking)
- **Allow Put-away**: Yes (allow quarantine storage)
- **Allow Movement**: Yes (allow movement for disposition)
- **Allow Output**: No (prevent use in production)

#### PASS Grade (Highest Priority)
**Use Case**: Quality test passed, normal business operations allowed
**Business Logic**: All transactions permitted for confirmed quality items

- **Allow Sales**: Yes (approved for customer shipment)
- **Allow Transfer**: Yes (approved for distribution)
- **Allow Consumption**: Yes (approved for production use)
- **Allow Pick**: Yes (approved for warehouse operations)
- **Allow Put-away**: Yes (normal warehouse operations)
- **Allow Movement**: Yes (normal warehouse operations)
- **Allow Output**: Yes (approved for production output)

#### Custom Grade Example: CONDITIONAL (Medium Priority)
**Use Case**: Conditionally acceptable with restrictions
**Business Logic**: Limited use with management approval

- **Allow Sales**: No (requires customer approval)
- **Allow Transfer**: Yes (can transfer with documentation)
- **Allow Consumption**: Yes (acceptable for non-critical applications)
- **Allow Pick**: Yes (with proper documentation)
- **Allow Put-away**: Yes (normal storage)
- **Allow Movement**: Yes (normal handling)
- **Allow Output**: No (not suitable for finished goods)

## Implementing Lot Blocking Scenarios

### Scenario 1: Block on Failure Only

**Business Rule**: Lots remain available until tests fail

**Implementation**:
1. **Workflow**: Block lot when test finishes with "FAIL" grade
2. **Grade Setup**: "In Progress" grade allows all transactions
3. **Result**: Normal operations continue until test failure

**Process Flow**:
1. Item received and put away normally
2. Quality test created  
3. Lot remains available for all operations
4. If test fails → lot becomes completely blocked
5. If test passes → no blocking occurs

### Scenario 2: Block During Testing

**Business Rule**: Block lots immediately when testing begins

**Implementation**:
1. **Workflow 1**: Block lot when test is created
2. **Workflow 2**: Unblock lot when test passes with "PASS" grade
3. **Grade Setup**: Configure document-specific controls if needed

**Process Flow**:
1. Item received
2. Quality test created → lot immediately blocked
3. Put-away may still be allowed (warehouse operations)
4. Test completion:
   - **Pass**: Lot unblocked, normal operations resume
   - **Fail**: Lot remains blocked

### Scenario 3: Document-Specific Controls

**Business Rule**: Prevent sales but allow warehouse operations during testing

**Implementation**:
1. **No Workflows**: Rely entirely on grade controls
2. **In Progress Grade**: 
   - Allow Put-away: Yes
   - Allow Movement: Yes
   - Allow Pick: No
   - Allow Sales: No

**Process Flow**:
1. Item received and test created
2. Put-away proceeds normally (allowed)
3. Sales orders cannot be posted (blocked)
4. Warehouse movements allowed for quality area
5. Test completion changes grade, updating permissions

## Working with Blocked Lots

### Identifying Blocked Lots

**Lot Information Cards**:
- Navigate to **Lot Number Information**
- Blocked lots show "Blocked" status
- View quality test references

**Quality Test Integration**:
- Tests show related lot blocking status
- Navigate from tests to lot information
- Review blocking history

### Managing Blocked Inventory

**Warehouse Operations**:
- Blocked lots may still allow warehouse movements
- Use for quarantine and disposition processes
- Configure grade controls for specific needs

**Disposition Actions**:
- Move to quarantine areas
- Process through rework procedures
- Create negative adjustments for disposal
- Return to vendors if appropriate

## Testing Lot Blocking Configuration

### Test Scenario: Purchase Receipt with Blocking

1. **Create Purchase Order**:
   - Item with lot tracking
   - Location with appropriate setup
   - Post warehouse receipt

2. **Verify Test Creation**:
   - Quality test created automatically
   - Check lot blocking status (depends on configuration)

3. **Test Sales Transaction**:
   - Create sales order for same lot
   - Attempt to post shipment
   - Verify blocking behavior

4. **Complete Quality Test**:
   - Enter measurement values
   - Finish test with pass or fail result
   - Verify lot status changes appropriately

### Validation Points

**Automatic Blocking**:
- Tests create and lots block as configured
- Blocking prevents inappropriate transactions
- Warehouse operations follow grade settings

**Test Completion**:
- Passing tests unblock lots (if configured)
- Failing tests maintain or create blocking
- Grade changes update transaction permissions

## Troubleshooting Lot Blocking

### Workflows Not Triggering

**Common Issues**:
- Workflow integration not enabled in Quality Inspection Setup
- Workflows not activated
- Incorrect event or condition configuration

**Solutions**:
- Enable workflow integration
- Activate required workflows  
- Review workflow configuration

### Unexpected Blocking Behavior

**Grade Control Issues**:
- Review grade configuration for transaction types
- Check test grade assignments
- Verify grade inheritance rules

**Workflow Conflicts**:
- Multiple workflows may conflict
- Review workflow priorities
- Consider disabling conflicting workflows

### Lots Not Unblocking

**Pass Condition Issues**:
- Verify test actually resulted in "PASS" grade
- Check workflow conditions for unblocking
- Review grade transition rules

**Manual Intervention**:
- Manually unblock lots through Lot Information Cards
- Review and correct workflow configuration
- Consider grade-based controls instead

## Related information

[Purchase Receipt Testing Without Warehouse Tracking](qms-purchase-receipt-testing-simple.md)  
[Purchase Receipt Testing With Warehouse Tracking](qms-purchase-receipt-testing-warehouse.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Processing Non-Compliant Items](qms-non-compliant-processing.md)  
[Quality Management Overview](qms-overview.md)