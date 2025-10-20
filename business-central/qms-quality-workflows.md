---
title: Quality management workflows
description: Learn how to automate quality management processes using workflows.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management workflows

This article explains how to configure and use Business Central workflows to automate quality management processes, including lot blocking, inventory movement, negative adjustments, and other responses to quality test results.

## Overview

Quality Management integrates with Business Central's workflow system to automate responses to quality inspection events. Workflows can automatically execute business actions when quality tests are created, finished, or when specific conditions are met.

## Prerequisites

- Workflow integration enabled in Quality Inspection Setup
- Business Central workflows feature activated
- Appropriate permissions for workflow configuration
- Required journal batches and templates configured

## Enabling Workflow Integration

Before creating quality workflows, ensure workflow integration is enabled:

1. Navigate to **Quality Inspection Setup**
2. Set **Workflow Integration** to **Enable Workflow Integration**
3. Configure required journal batches for automated processes

**Important**: Without workflow integration enabled, quality inspection events will not be available in workflow configuration.

## Common Quality Workflow Events

### When Events

**When a Quality Inspection Test is Created**:

- Triggered automatically when test generation rules create new tests
- Use for immediate actions like lot blocking upon test creation
- Available for all test creation methods (purchase receipts, production output, manual creation)

**When a Quality Inspection Test is Finished**:

- Triggered when tests are completed and finalized
- Use for disposition actions based on test results
- Most common event for quality workflows

### Workflow Conditions

**Grade Code Conditions**:

- Grade Code equals "PASS" - for successful test completion
- Grade Code equals "FAIL" - for failed test processing
- Grade Code equals "INPROGRESS" - for tests in progress
- Custom grade codes as configured in your system

**Additional Conditions**:

- Location codes for site-specific workflows
- Item numbers for product-specific processing
- Test template codes for template-specific responses

## Workflow Response Actions

### Lot (Serial, Package) Blocking Actions

**Block the Lot (Serial, Package) in the Test**:

- Creates lot number information card with blocked status
- Prevents all transactions for the lot until manually unblocked
- Standard Business Central lot blocking functionality applies

**Unblock the Lot (Serial, Package) in the Test**:

- Removes lot blocking from previously blocked lots
- Restores normal transaction capabilities
- Typically used with passing test results

### Inventory Movement Actions

**Move Inventory to Different Bin**:

- Automatically relocates inventory based on test results
- Uses movement worksheets, movement documents, or reclassification journals
- Supports directed put-away and pick locations

**Create Transfer Order**:

- Moves inventory between locations
- Useful for quarantine or rework locations
- Can be configured for automatic or manual posting

### Inventory Adjustment Actions

**Create Negative Adjustment**:

- Removes inventory for disposal or destructive testing
- Uses item journals or warehouse item journals
- Supports reason codes for audit trails
- Can process full lots, specific quantities, or failed quantities only

### Test Creation Actions

**Create Retest**:

- Automatically generates follow-up tests
- Useful for corrective action processes
- Can use same or different test templates

**Create Internal Put-away**:

- Generates warehouse put-away for inventory staging
- Supports quality inspection workflows in warehouse environments

## Workflow Configuration Examples

### Example 1: Block Lot on Test Failure

**Business Scenario**: Automatically quarantine failed lots

**Configuration**:

1. **Workflow Name**: "Block Lot on Failure"
2. **When Event**: When a **Quality Inspection Test is Finished**
3. **Condition**: Grade equals "Fail"
4. **Response**: Block the lot in the test

**Business Impact**:

- Failed lots immediately blocked from all transactions
- Creates lot number information card for tracking
- Prevents accidental use of non-conforming materials

### Example 2: Preemptive Lot Blocking

**Business Scenario**: Block lots during testing, unblock on pass

**Blocking Workflow**:

1. **Workflow Name**: "Block Lot on Test Creation"
2. **When Event**: When a **Quality Inspection Test is Created**
3. **Condition**: None (applies to all tests)
4. **Response**: Block the lot in the test

**Unblocking Workflow**:

1. **Workflow Name**: "Unblock Lot on Pass"
2. **When Event**: When a **Quality Inspection Test is Finished**
3. **Condition**: Grade Code equals **"Pass"**
4. **Response**: Unblock the lot in the test

**Business Impact**:

- Lots quarantined immediately upon test creation
- Only passing tests release lots for normal use
- Prevents use of untested materials

### Example 3: Automatic Bin Movement

**Business Scenario**: Move failed items to quarantine bin

**Configuration**:

1. **Workflow Name**: "Move Failed Items to Quarantine"
2. **When Event**: When a **Quality Inspection Test is Finished**
3. **Condition**: Grade Code equals **"Fail"**
4. **Response**: Move inventory to different bin
5. **Details**:
   - **Method**: Reclassification Journal
   - **Quantity**: Entire Lot
   - **Destination**: Quarantine bin (e.g., W-02-02)
   - **Post Immediately**: No (requires manual review)

**Business Impact**:

- Failed items automatically staged for quarantine
- Physical separation of conforming and non-conforming items
- Maintains audit trail of quality dispositions

### Example 4: Negative Adjustment for Disposal

**Business Scenario**: Automatically dispose of failed or destructively tested items

**Configuration**:

1. **Workflow Name**: "Dispose Failed Items"
2. **When Event**: When a **Quality Inspection Test is Finished**
3. **Condition**: Grade Code equals **"Fail"**
4. **Response**: Create negative adjustment
5. **Details**:
   - **Quantity**: Failed Quantity (or Entire Lot)
   - **Reason Code**: Quality Assurance
   - **Post Immediately**: No (review required)

**Business Impact**:

- Automatic inventory reduction for non-recoverable items
- Proper cost accounting for quality losses
- Audit trail for disposed materials

## Advanced Workflow Scenarios

### Conditional Grade-Based Processing

**Multiple Failure Types**:

- Create separate workflows for different failure grades
- Different responses based on failure severity
- Escalation procedures for critical failures

**Location-Specific Processing**:

- Different workflows for different locations
- Site-specific quarantine procedures
- Regional compliance requirements

### Integration with Other Business Central Features

**Purchase Returns**:

- Automatically create purchase returns for vendor defects
- Link to vendor quality performance tracking
- Streamline vendor corrective action processes

**Production Integration**:

- Automatic rework orders for repairable items
- Production output quality control
- Work center quality tracking

### Batch Configuration Requirements

Workflows require configured journal batches in Quality Inspection Setup:

**Item Journal Batch**: For non-warehouse location adjustments
**Warehouse Item Journal Batch**: For warehouse location adjustments  
**Warehouse Movement Worksheet**: For directed put-away/pick movements
**Warehouse Reclass Journal Batch**: For warehouse reclassifications
**Item Reclass Journal Batch**: For non-warehouse reclassifications

## Testing Workflow Configuration

### Validation Steps

1. **Create Test Scenario**:
   - Generate quality test through normal business process
   - Verify workflow events trigger correctly
   - Confirm conditions evaluate properly

2. **Check Response Actions**:
   - Verify intended actions occur
   - Review journal entries created
   - Confirm blocking/unblocking behavior

3. **Business Process Integration**:
   - Test with actual business transactions
   - Verify document posting behavior
   - Confirm user experience meets expectations

### Common Configuration Issues

**Workflow Events Not Available**:

- Check workflow integration enabled in Quality Inspection Setup
- Verify workflows are activated
- Confirm user permissions

**Actions Not Executing**:

- Review workflow conditions
- Check journal batch configuration
- Verify grade code matching

**Unexpected Blocking Behavior**:

- Review multiple workflow interactions
- Check grade-based transaction controls
- Verify workflow priority and sequence

## Best Practices

### Workflow Design

**Start Simple**: Begin with basic scenarios and add complexity gradually
**Test Thoroughly**: Validate workflows in development environment before production
**Document Processes**: Maintain clear documentation of workflow business rules
**Monitor Performance**: Review workflow execution and business impact regularly

### Business Impact Considerations

**User Training**: Ensure users understand automated processes
**Override Procedures**: Maintain manual override capabilities for exceptions
**Audit Requirements**: Configure proper audit trails and approval processes
**System Performance**: Monitor impact of automated processes on system performance

### Maintenance and Updates

**Regular Review**: Periodically assess workflow effectiveness
**Business Rule Changes**: Update workflows when business processes change
**System Updates**: Verify workflow compatibility with system updates
**User Feedback**: Incorporate user suggestions for process improvements

## Troubleshooting

### Workflow Not Triggering

1. Check workflow integration enabled
2. Verify workflow is activated
3. Review event conditions
4. Confirm user permissions

### Incorrect Actions Executed

1. Review workflow conditions and logic
2. Check for multiple conflicting workflows
3. Verify grade code configuration
4. Review workflow execution order

### Performance Issues

1. Monitor workflow execution frequency
2. Review batch processing configuration
3. Consider timing of automated actions
4. Evaluate system resource impact

## Related information

[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Processing Non-Compliant Items](qms-non-compliant-processing.md)  
[Configuring Grades](qms-configuring-grades.md)  
[Quality Management Setup](qms-setup.md)  
[Quality Management Overview](qms-overview.md)