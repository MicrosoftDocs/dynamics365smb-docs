---
title: Set up test generation rules
description: Learn how to configure test generation rules to automate quality inspections based on business transactions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up test generation rules

Test generation rules define when and how quality inspection tests are automatically created in response to business transactions. These rules connect your quality templates to specific business processes.

A Quality Inspection Test generation rule defines when you want to ask a set of questions or other data that you want to collect that is defined in a template. You connect a template to a source table, and set the criteria to use that template with the table filter. When these filter criteria is met, then it will choose that template. When there are multiple matches, it will use the first template that it finds, based on the sort order.

## Overview

Test generation rules control:
- **When** tests are created (triggers)
- **What** templates are used for testing
- **Which** items, locations, or documents create tests
- **How** tests are created (automatic vs. manual)

## Rule Components

### Source Types

Test generation rules can be created for various source document types:

**Purchase**:
- Creates tests based on purchase order transactions
- Triggers on purchase receipt posting
- Supports vendor and item filtering

**Production Order Routing**:
- Creates tests based on production output
- Triggers on output posting  
- Supports routing, work center, and operation filtering

**Warehouse Journal**:
- Creates tests for warehouse-specific operations
- Supports put-away and movement testing
- Integrates with warehouse workflows

also for **Sales Return**, **Warehouse Receive**, **Warehouse Movement**, **Transfer**, and **Assembly**

### Trigger Configuration

**Activation Trigger**:
- **Disabled**: No automatic test creation
- **Automatic Only**: Automatic on receipt posting
- **Manual Only**: Only manual test creation allowed
- **Both Manual and Automatic**: Both methods enabled

**Purchase Trigger**:
- **Never**: No automatic test creation
- **When Purchase Order is Received**: Automatic on receipt posting
- **When Purchase Order is Released**: Automatic on purchase order release

**Production Trigger**:
- **Never**: No automatic test creation
- **When Output is Posted**: Automatic on output posting
- **When Order is Released**: Automatic on changing the status of production order to "Released"
- **When a Released Order is Refreshed**: Automatic on refreshing a released production order

## Creating Test Generation Rules

### Method 1: Create Receiving Rule (Purchase)

**Best for**: Purchase receipt testing

1. Navigate to **Quality Inspection Test Generation Rules**
2. Choose **Create Receiving Rule**
3. Configure:
   - **Template Code**: Select quality template
   - **Receiving Rule**: Purchase Line (automatically set)
   - **Location, Vendor No., Purchasing Code, Specific Item, Category, Inventory Posting Group**: Specify which items, groups of items, locations, etc. create tests.
   - **Automatically Create Test**: Specify a trigger to automatically create a test when product is received via a purchase order.

### Method 2: Create Production Rule

**Best for**: Production output testing

1. Navigate to **Quality Inspection Test Generation Rules**
2. Choose **Create Production Rule**
3. Configure:
   - **Template Code**: Select quality template
   - **Source Type**: Production Orders (automatically set)
   - **Filters**: Configure as needed
   - **Automatically Create Test**: Select trigger type.

### Method 3: Manual Rule Creation

**Best for**: Custom or complex filtering requirements

1. Navigate to **Test Generation Rules**
2. Create **New** rule
3. Configure all fields manually

## Filter Configuration

### Common Filter Fields

**Item Filters**:
- **Item No. Filter**: Specific items requiring testing
- **Item Category Filter**: Groups of related items
- **Inventory Posting Group Filter**: Items with similar characteristics

**Location Filters**:
- **Location Code Filter**: Specific locations requiring testing

**Vendor/Customer Filters**:
- **Vendor No. Filter**: Vendor-specific quality requirements
- **Customer No. Filter**: Customer-specific testing needs

**Production Filters**:
- **Routing No. Filter**: Specific production processes
- **Work Center No. Filter**: Specific work centers
- **Machine Center No. Filter**: Specific machines

### Filter Examples

#### Simple Item-Based Rule
**Purpose**: Test all receipts of a specific item
- **Source Type**: Purchase Line
- **Item No. Filter**: WRB-1002
- **Purchase Trigger**: When Purchase Order is Received
- **Other Filters**: (blank for universal application)

#### Location-Specific Rule
**Purpose**: Test all items at a specific location
- **Source Type**: Purchase Line
- **Location Code Filter**: WHITE
- **Purchase Trigger**: When Purchase Order is Received
- **Item Filter**: (blank for all items)

#### Vendor-Specific Rule
**Purpose**: Enhanced testing for specific vendor
- **Source Type**: Purchase Line
- **Vendor No. Filter**: V001
- **Purchase Trigger**: When Purchase Order is Received
- **Template**: Enhanced inspection template

## Rule Priority and Ordering

### Multiple Rule Interaction

When multiple rules could apply to the same transaction:
- **All matching rules execute**: Multiple tests may be created
- **Rule ordering**: Managed through rule list sequence
- **Template assignment**: Each rule uses its assigned template

### Best Practices for Multiple Rules

**Avoid Overlap**: Design rules to minimize unintended multiple test creation
**Use Specific Filters**: More specific rules for special cases
**Document Logic**: Maintain documentation of rule interactions

## Trigger Configuration Strategy

### Business Process Alignment

**Proactive Testing** (Automatic Triggers):
- Quality requirements are predictable
- Testing is part of standard process
- Resources available for immediate testing

**Reactive Testing** (Manual Triggers):
- Testing based on risk assessment
- Limited quality resources
- Investigation-driven testing

**Hybrid Approach** (Both Methods):
- Automatic for routine quality control
- Manual for special investigations
- Maximum flexibility

### Organizational Considerations

**Role Separation**:
- Automatic triggers when different people post vs. test
- Manual triggers when same person does both
- Consider workflow and responsibility assignment

**Resource Management**:
- Automatic triggers require dedicated quality resources
- Manual triggers allow resource optimization
- Balance coverage with capacity

## Testing Rule Configuration

### Validation Process

1. **Create Test Scenario**:
   - Configure rule with specific filters
   - Create matching business transaction
   - Verify test creation behavior

2. **Check Rule Logic**:
   - Confirm filters work as expected
   - Verify template assignment
   - Test trigger behavior

3. **Review Results**:
   - Validate test content and structure
   - Check source document linking
   - Confirm item tracking integration

### Common Validation Issues

**No Tests Created**:
- Check filter configuration
- Verify trigger settings
- Confirm template assignment

**Too Many Tests Created**:
- Review overlapping rules
- Refine filter specificity
- Check rule ordering

**Wrong Template Applied**:
- Verify template assignment in rule
- Check rule priority and ordering
- Review filter logic

## Maintenance and Updates

### Rule Modification

**Updating Existing Rules**:
- Modify filters to expand or restrict scope
- Change templates for improved testing
- Adjust triggers based on process changes

**Version Control**:
- Document rule changes
- Test modifications before implementation
- Maintain backup of working configurations

### Performance Considerations

**Filter Efficiency**:
- Use specific filters to improve performance
- Avoid overly broad rules if not needed
- Monitor system performance with complex rules

**Rule Quantity**:
- Balance comprehensive coverage with system performance
- Consolidate similar rules where possible
- Regular review and cleanup of unused rules

## See Also

- [Creating Quality Inspection Templates](1.4-quality-templates.md)
- [Purchase Receipt Testing Without Warehouse Tracking](2.1-purchase-receipt-testing-simple.md)
- [Production Output Quality Testing](2.3-production-output-testing.md)
- [Manual Test Creation](2.4-manual-test-creation.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)