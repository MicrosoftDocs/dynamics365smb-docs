---
title: Configure quality inspection grades
description: Learn how to configure and manage quality inspection grades, including grade setup, priority rules, business process integration, and best practices for ensuring quality outcomes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Configure quality inspection grades

This guide explains how to configure and use quality inspection grades in Quality Management. Grades are configurable states that determine test results and control business processes based on quality outcomes.

## Overview

Quality inspection grades represent the possible outcomes of quality tests. Grades are effectively the incomplete/pass/fail state of a test. It is typical to have three grades (incomplete, fail, pass), however you can configure as many grades as you want, and in what circumstances. The grades with a lower number for the priority field are evaluated first. If you are not sure what to configure here then use the three defaults. The document specific lot blocking is for item+variant+lot+serial+package combinations, and can be used for serial-only tracking, or package-only tracking.

### Grade Concepts

**Default Grades**:
- **In Progress** (Priority 0): Test is incomplete or in progress
- **Fail** (Priority 1): Test has failed quality criteria  
- **Pass** (Priority 2): Test has met quality criteria

**Custom Grades**:
- Multiple pass grades (e.g., "Excellent", "Good", "Acceptable")
- Multiple fail grades (e.g., "Minor Defect", "Major Defect", "Critical Failure")
- Gray state grades (e.g., "Under Review", "Conditional Pass")


## Configuring Available Grades

### Step 1: Access Quality Inspection Grades

1. Navigate to **Quality Inspection Grades** in Business Central
2. Review existing grades and their priority order
3. Grades are displayed from lowest priority to highest priority

### Step 2: Understanding Default Grade Structure

**Configuration Example**:

| Grade Code | Description | Priority | Copy Behavior      | Allow Sales | Allow Purchase |
| ---------- | ----------- | -------- | ------------------ | ----------- | -------------- |
| INPROGRESS | In Progress | 0        | Automatically Copy | Block       | Allow          |
| FAIL       | Fail        | 1        | Automatically Copy | Block       | Allow          |
| PASS       | Pass        | 2        | Automatically Copy | Allow       | Allow          |
In this example, sales transactions for a lot are restricted until the quality test is completed and passes all criteria. If the test is incomplete or fails, sales are blocked. Purchase transactions, however, remain permitted at all times.	

### Step 3: Grade Priority Rules

**Priority 0 (Incomplete/In Progress)**:
- Represents incomplete or ongoing tests
- Default condition should be blank (matches any value including empty)
- Evaluated first in grade determination

**Priority 1+ (Failure States)**:
- Represents various failure conditions
- Must have priority higher than incomplete grades
- Must have priority lower than pass grades

**Highest Priority (Pass States)**:
- Represents successful test outcomes
- Evaluated last in grade determination
- Must have highest priority numbers

### Step 4: Copy Behavior Configuration

**Automatically Copy the Grade**:
- Grade is automatically added to new templates
- Default behavior for standard grades
- Ensures consistent grade availability

**Do Not Copy**:
- Grade must be manually added to templates
- Used for specialized or conditional grades
- Allows selective grade application

### Step 5: Available Transactions Control

- **Allow Sales**: Enable/disable sales document posting
- **Allow Purchase**: Enable/disable purchase document posting  
- **Allow Transfer**: Enable/disable transfer order posting
- **Allow Consumption**: Enable/disable material consumption in production
- **Allow Pick**: Enable/disable warehouse picks
- **Allow Put-away**: Enable/disable warehouse put-aways
- **Allow Movement**: Enable/disable warehouse movements
- **Allow Output**: Enable/disable production output posting

## Configuring Grade Conditions

### Field Level Grade Configuration

Configure default grade conditions for specific measurement fields:

1. Navigate to **Quality Inspector Fields**
2. Select the field to configure
3. Expand **Grade Conditions** section
4. Configure conditions for the "Pass" grade

### Template Level Grade Configuration

Override field defaults for specific template requirements:

1. Navigate to **Quality Inspection Templates**
2. Edit the template
3. Select the field to modify
4. Configure conditions for the "Pass" grade

**When to Use Template-Level Configuration**:
- Different acceptance criteria for same measurement
- Template-specific quality standards
- Customer-specific requirements

### Grade Condition Syntax

**Number Field Conditions**:
- `20..24`: Range from 20 to 24
- `>=20`: Greater than or equal to 20
- `<>0`: Not equal to zero
- `10|20|30`: Equals 10, 20, or 30

**Text Field Conditions**:
- `PASS|GOOD|OK`: Matches any of these values
- `<>""`: Not blank
- `A*`: Starts with "A"

**Date Field Conditions**:
- `TODAY..TODAY+30D`: Today through 30 days from today
- `>=01/01/2024`: On or after specific date

## Grade Visibility and Promotion

### Promoting Grades for Better Visibility

**Grade Promotion Benefits**:
- Highlighted in field configuration screens
- Visible inline during template configuration  
- Prominent display during test execution
- Featured in reports and certificates of analysis

### Configuring Grade Promotion

1. Navigate to **Quality Inspection Grades**
2. Select **Edit List**
3. Enable **Promoted** under **Grade Visibility** for important grades
4. First 10 promoted grades are shown in descending priority order

**Typically Promoted Grades**:
- **PASS**: Primary success indicator
- **FAIL**: Primary failure indicator
- Other customer-critical grades

### Effects of Grade Promotion

**Field Configuration**:
- Additional columns for promoted grade conditions
- Inline editing of promoted grade criteria
- Quick access to most important conditions

**Template Configuration**:
- Promoted grades editable inline
- Replaces traditional "Acceptable Values" field
- Streamlined template setup

**Test Execution**:
- Promoted grade conditions visible during testing
- Quick reference for inspectors
- Reduced errors in test completion

**Reporting**:
- Certificate of Analysis shows promoted grades
- Quality reports highlight promoted results
- Executive dashboards focus on key grades

## Advanced Grade Configuration

### Multiple Pass Grades

**Business Scenario**: Different levels of product quality

**Grade Configuration**:
- **EXCELLENT** (Priority 10): Premium quality standards
- **GOOD** (Priority 9): Standard quality standards  
- **ACCEPTABLE** (Priority 8): Minimum acceptable quality
- **FAIL** (Priority 1): Below minimum standards

**Example Conditions** (for dimension measurement):
- **EXCELLENT**: 99.9..100.1 (tight tolerance)
- **GOOD**: 99.5..100.5 (standard tolerance)
- **ACCEPTABLE**: 99.0..101.0 (loose tolerance)
- **FAIL**: <>0 (any value outside acceptable range)

### Multiple Fail Grades

**Business Scenario**: Different severity levels of defects

**Grade Configuration**:
- **CRITICAL** (Priority 1): Safety or regulatory failure
- **MAJOR** (Priority 2): Functional failure
- **MINOR** (Priority 3): Cosmetic or minor defect
- **PASS** (Priority 10): Acceptable quality

**Business Process Integration**:
- **CRITICAL**: Immediate recall, supplier notification
- **MAJOR**: Quarantine, rework evaluation
- **MINOR**: Conditional release, customer notification

### Conditional and Gray State Grades

**Business Scenario**: Items requiring additional evaluation

**Grade Configuration**:
- **UNDER_REVIEW** (Priority 5): Requires management decision
- **CONDITIONAL** (Priority 6): Passes with limitations
- **RETEST** (Priority 4): Requires additional testing

## Integration with Business Processes

### Workflow Integration

Grades can trigger different workflow responses:

**Grade-Specific Workflows**:
- **FAIL** grade → Block lot, create negative adjustment
- **CRITICAL** grade → Immediate notification, supplier alert
- **RETEST** grade → Create additional test, schedule inspection

### Document Control Integration

Grades control transaction permissions:

**Sales Integration**:
- **PASS** grades allow sales shipment
- **FAIL** grades block sales shipment
- **CONDITIONAL** grades require approval

**Production Integration**:
- **PASS** grades allow consumption
- **FAIL** grades block material usage
- **UNDER_REVIEW** grades require supervisor approval

### Reporting and Analytics

**Grade-Based Reporting**:
- Quality scorecards by grade distribution
- Trend analysis of grade patterns
- Vendor performance by grade outcomes
- Customer satisfaction correlation with grades

## Best Practices for Grade Configuration

### Grade Design Principles

**Keep It Simple**:
- Start with basic Pass/Fail/In Progress
- Add complexity only when business value is clear
- Ensure users understand grade meanings

**Business Alignment**:
- Align grades with business processes
- Match grades to decision points
- Consider customer and supplier perspectives

**Consistent Logic**:
- Use consistent condition syntax across fields
- Maintain logical priority ordering
- Document grade definitions and usage

### Change Management

**Grade Condition Updates**:
- Understand that changes don't affect existing tests
- Plan updates during low-activity periods
- Communicate changes to quality team

**Template Migration**:
- Test grade changes on non-critical templates first
- Provide training on new grade meanings
- Monitor impact on quality processes

### Performance Considerations

**Grade Complexity**:
- Complex conditions can impact test performance
- Limit number of active grades to business needs
- Regular cleanup of unused grades

## Troubleshooting Grades

### Common Issues

**Tests Not Calculating Expected Grades**:
- Review grade condition syntax
- Check priority ordering
- Verify condition inheritance from field to template

**Grades Not Available in Templates**:
- Check grade copy behavior settings
- Verify grade is not set to "Do Not Copy"
- Manually add grade to template if needed

**Workflow Not Triggering**:
- Confirm workflow condition matches grade code exactly
- Check grade code spelling and case sensitivity
- Review workflow activation status

### Grade Validation

**Testing Grade Logic**:
- Use "Value to Test" feature in grade configuration
- Test boundary conditions and edge cases
- Validate grade calculations with sample data

**Process Validation**:
- Create test scenarios for each grade outcome
- Verify business process responses to grades
- Confirm reporting displays grades correctly

## See Also

- [Creating Quality Inspection Templates](1.4-quality-templates.md)
- [Lot Blocking and Unblocking](3.1-lot-blocking-unblocking.md)
- [Configuring Workflows](1.6-quality-workflows.md)
- [Quality Management Setup and Configuration](1.1-quality-management-setup.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)