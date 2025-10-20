---
title: Manual test creation
description: Learn how to manually create quality inspection tests for reactive testing, investigations, and spot checks.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Manual test creation

This article explains the various methods for manually creating quality inspection tests. Manual test creation is essential for reactive testing scenarios and quality investigations.

## Overview

Manual test creation provides flexibility for:

- **Reactive Testing**: Creating tests in response to quality issues
- **Investigation**: Testing specific lots or items due to concerns  
- **Spot Checking**: Random quality verification
- **Customer Complaints**: Testing related to external feedback

Manual tests use the same templates and configurations as automatic tests but are created on-demand by users.

## Prerequisites

- Quality inspection templates configured
- Test generation rules set up (with manual triggers)
- Items available for testing
- Appropriate user permissions

## Test Generation Rule Configuration

### Manual-Only Rules

Create rules specifically for manual test creation:

1. Navigate to **Test Generation Rules**
2. Create or modify rules with:
   - **Purchase Trigger**: "Manual Only"
   - **Production Trigger**: "Manual Only"  
   - **Template Assignment**: Appropriate template
   - **Source Type**: Purchase Line, Production Order Routing Line, etc.

### Manual vs. Automatic Rules

**Manual Only Rules**:
- Tests created only when users click "Create Test" buttons
- No automatic test creation during posting
- Ideal for reactive testing scenarios

**Manual and Automatic Rules**:
- Tests can be created both automatically and manually
- Provides flexibility for both proactive and reactive testing
- Most comprehensive approach

## Methods of Manual Test Creation

### Method 1: From Item Tracking Lines

**Best for**: Lot-specific testing when item tracking is already configured

**Process**:
1. Navigate to source document (Purchase Order, Production Order, etc.)
2. Access **Item Tracking Lines**
3. Select specific lot/serial number lines
4. Click **Create Test**
5. Test is created with pre-filled item tracking information

**Advantages**:
- Lot numbers automatically populated
- Quantities automatically assigned
- Direct connection to source document

### Method 2: From Purchase/Production Lines

**Best for**: Testing items without specific lot requirements

**Process**:
1. Navigate to source document line
2. Click **Create Test** from the line
3. Select appropriate template if prompted
4. Manually specify lot number if required

**Characteristics**:
- Source document information pre-filled
- Lot number may need manual entry
- Useful for non-tracked items

### Method 3: From Quality Inspection Templates

**Best for**: Creating tests independent of specific documents

**Process**:
1. Navigate to **Quality Inspection Templates**
2. Select appropriate template
3. Click **Create Test**
4. Configure test parameters:
   - **Template**: Pre-selected
   - **Source**: Optional document reference
   - **Item Number**: Select item to test
   - **Lot/Serial Number**: Enter if applicable
   - **Quantity**: Specify test quantity

**Advantages**:
- Complete flexibility in test configuration
- Not tied to specific business transactions
- Ideal for investigation and spot-checking

## Manual Test Creation Scenarios

### Scenario 1: Reactive Testing from Purchase

**Situation**: Quality issue discovered after receipt
**Method**: From Item Tracking Lines

1. **Locate Purchase Order**: Find original purchase receipt
2. **Access Item Tracking**: Open item tracking lines
3. **Select Problematic Lots**: Choose specific lots with issues
4. **Create Test**: Generate test for investigation
5. **Complete Testing**: Perform detailed quality evaluation

### Scenario 2: Production Quality Investigation

**Situation**: Customer complaint about finished goods
**Method**: From Quality Templates

1. **Select Template**: Choose appropriate quality template
2. **Create Test**: Use template "Create Test" function
3. **Configure Details**:
   - Item: Finished goods item
   - Lot: Customer-reported lot number
   - Quantity: Representative sample
4. **Complete Investigation**: Perform detailed testing

### Scenario 3: Spot Check Inspection

**Situation**: Random quality verification
**Method**: From Purchase Lines

1. **Identify Items**: Select items for spot checking
2. **Access Document**: Navigate to relevant purchase order
3. **Create Test**: Use line-level "Create Test" function
4. **Specify Parameters**: Add lot information if needed
5. **Execute Test**: Complete quality evaluation

## Test Configuration Options

### Template Selection

When creating manual tests:
- **Automatic**: Template determined by test generation rules
- **Manual Selection**: Choose specific template for situation
- **Multiple Templates**: Create multiple tests with different templates

### Source Document Linking

**With Source Document**:
- Test linked to originating transaction
- Traceability maintained
- Source information pre-populated

**Without Source Document**:
- Independent quality test
- Manual configuration required
- Useful for investigation testing

### Item Tracking Specifications

**Lot-Tracked Items**:
- Specify lot number during test creation
- System validates lot existence
- Lot information displayed in test

**Serial-Tracked Items**:
- Enter specific serial numbers
- Individual test per serial number
- Detailed traceability

**Non-Tracked Items**:
- Test created without tracking information
- Quantity-based testing
- Suitable for bulk materials

## Best Practices for Manual Testing

### Documentation Requirements

**Test Justification**:
- Record reason for manual test creation
- Document quality concerns or triggers
- Maintain audit trail

**Results Documentation**:
- Complete all template fields
- Add notes for unusual findings
- Link to corrective actions if needed

### Process Integration

**Reactive Testing Workflow**:
1. Quality issue identification
2. Manual test creation
3. Investigation and analysis
4. Corrective action implementation
5. Verification testing

**Investigation Protocol**:
- Consistent testing methods
- Appropriate sample sizes
- Proper documentation
- Follow-up procedures

## Troubleshooting Manual Test Creation

### "Create Test" Button Not Available

**Possible Causes**:
- No test generation rules configured for manual creation
- Rules set to "Automatic Only" or "Never"
- Missing template assignments

**Solutions**:
- Configure manual-enabled test generation rules
- Verify template assignments
- Check user permissions

### Test Creation Dialog Issues

**Missing Template Options**:
- Verify templates exist and are properly configured
- Check test generation rule filters
- Ensure templates have required fields

**Item Selection Problems**:
- Confirm item exists and is properly configured
- Check item tracking setup if using lots/serials
- Verify item permissions

### Incomplete Test Information

**Missing Source Details**:
- Create test from appropriate source document
- Manually enter source information if needed
- Verify document posting status

**Item Tracking Issues**:
- Confirm lot/serial numbers exist in system
- Check item tracking code configuration
- Verify quantity allocations

## Integration with Automated Testing

### Complementary Approaches

**Automatic Testing**: Proactive quality control
- Routine inspections
- Process compliance
- Prevention-focused

**Manual Testing**: Reactive quality investigation
- Problem investigation
- Customer complaint resolution
- Corrective action verification

### Unified Results Management

Both manual and automatic tests:
- Use same templates and measurement criteria
- Generate comparable results
- Integrate with lot blocking and workflows
- Support comprehensive quality reporting

## See Also

- [Purchase Receipt Testing Without Warehouse Tracking](2.1-purchase-receipt-testing-simple.md)
- [Production Output Quality Testing](2.3-production-output-testing.md)
- [Creating Quality Inspection Templates](1.4-quality-templates.md)
- [Setting Up Test Generation Rules](1.5-test-generation-rules.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)