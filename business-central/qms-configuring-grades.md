---
title: Configure quality inspection results
description: Learn how to configure and manage quality inspection results, including grade setup, priority rules, and business process integration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Configure quality inspection results

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This guide explains how to configure and use quality inspection results in quality management. Results are configurable states and control business processes based on quality outcomes.

## Overview

Quality inspection results represent the possible outcomes of quality inspections. Typical results are Incomplete, Fail, and Pass. However, you can configure as many grades as you want, and in what circumstances. Results with a lower number in the **Priority** field are evaluated first. If you're unsure what to configure, use the three defaults. To learn more about the defaults, go to [Result concepts](#result-concepts). Document-specific lot blocking is for combinations of items, variants, lots, serial numbers, and package numbers, and you can use it for serial-only tracking, or package-only tracking.

### Result concepts

**Default results**:

- **In Progress** (Priority 0): The inspection is incomplete or in progress.
- **Fail** (Priority 1): The inspection failed to meet quality criteria.  
- **Pass** (Priority 2): The inspection met quality criteria.

**Custom results**:

- Create multiple passing results. For example, Excellent, Good, and Acceptable.
- Create multiple failing results. For example, Minor Defect, Major Defect, and Critical Failure.
- Create gray state results. For example, Under Review and Conditional Pass.

## Configuring results

### Access quality inspection results

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Results**, and then choose the related link.
2. Review the existing results and their order of priority. Results display from lowest to highest priority.

### Understand the default result structure

The following table shows an example of a configuration.

| Result Code | Description | Priority | Copy Behavior      | Allow Sales | Allow Purchase |
| ---------- | ----------- | -------- | ------------------ | ----------- | -------------- |
| INPROGRESS | In Progress | 0        | Automatically Copy | Block       | Allow          |
| FAIL       | Fail        | 1        | Automatically Copy | Block       | Allow          |
| PASS       | Pass        | 2        | Automatically Copy | Allow       | Allow          |

In this example, sales transactions for a lot are restricted until the quality inspection is complete and passes all criteria. If the inspection is incomplete or fails, sales are blocked. Purchase transactions, however, are always allowed.

### Result priority rules

**Priority 0 (incomplete or in progress)**:

- Represents incomplete or ongoing inspections.
- Default condition should be blank (matches any value including empty).
- Evaluated first in result determination.

**Priority 1+ (failure states)**:

- Represents various failure conditions.
- Must have a higher priority than incomplete results.
- Must have a lower priority than pass results.

**Highest priority (pass states)**:

- Represents successful inspection outcomes.
- Evaluated last in result determination.
- Must have the highest priority numbers.

### Copy behavior configuration

**Automatically Copy the Result**:

- Result is automatically added to new inspection templates.
- Default behavior for standard results.
- Ensures consistent result availability.

**Do Not Copy**:

- You must manually add the result to inspection templates.
- Use for specialized or conditional results.
- Allows selective result application.

### Available transactions control

- **Allow Sales**: Enable or disable sales document posting.
- **Allow Purchase**: Enable or disable purchase document posting.
- **Allow Transfer**: Enable or disable transfer order posting.
- **Allow Consumption**: Enable or disable material consumption in production.
- **Allow Pick**: Enable or disable warehouse picks.
- **Allow Put-away**: Enable or disable warehouse put-aways.
- **Allow Movement**: Enable or disable warehouse movements.
- **Allow Output**: Enable or disable production output posting.

## Configure result conditions

You can configure results at the field and template levels. Configure results at the template-level when you have:

- Different acceptance criteria for same measurement.
- Template-specific quality standards.
- Customer-specific requirements.

### Field-level result configuration

You can configure default result conditions for specific measurement fields.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspector Fields**, and then choose the related link.
2. Select the field to configure.
3. On the **Result Conditions** FastTab, configure conditions for the passing grade. To learn more about grade conditions, go to [Result condition syntax](#result-condition-syntax).

### Result condition syntax

The following are examples of number field conditions:

- `20..24`: Range from 20 to 24
- `>=20`: Greater than or equal to 20
- `<>0`: Not equal to zero
- `10|20|30`: Equals 10, 20, or 30

The following are examples of text field conditions:

- `PASS|GOOD|OK`: Matches any of these values
- `<>""`: Not blank
- `A*`: Starts with "A"

The following are examples of date field conditions:

- `TODAY..TODAY+30D`: Today through 30 days from today
- `>=01/01/2024`: On or after specific date

### Template-level result configuration

Override field defaults for specific inspection template requirements:

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and then choose the related link.
2. Edit the template.
3. Select the field to modify.
4. Configure conditions for the passing result.

## Promote results for better visibility

Promoting results have the following benefits:

- They stand out in field configuration screens.
- They display inline when you configure templates.
- They display prominently when you run tests.
- They're featured in reports and certificates of analysis.

The following are examples of results that are often promoted:

- **PASS**: Primary success indicator
- **FAIL**: Primary failure indicator
- Other customer-critical grades

### Effects of result promotion

**Field configuration**:

- Extra columns for promoted result conditions.
- Inline editing of promoted result criteria.
- Quick access to most important conditions.

**Template configuration**:

- Promoted results are editable inline.
- Replaces the traditional **Acceptable Values** field.
- Streamlines template set-up.

**Test execution**:

- Promoted result conditions are visible during testing.
- Quick reference for inspectors.
- Reduced errors in test completion.

**Reporting**:

- **Certificate of Analysis** shows promoted results.
- Quality reports highlight promoted results.
- Executive dashboards focus on key results.

### Configure result promotion

1. [!INCLUDE [prod_short](includes/prod_short.md)], enter **Quality Inspection Results**, and then select the related link.
2. Choose the **Edit List** action.
3. Under **Result Visibility**, turn on the **Promoted** toggle for important results.
4. The first 10 promoted results show in a descending order of priority.

## Advanced result configurations

Quality management lets you add nuance to your quality inspection results.

### Set up multiple passing results

To allow for different levels of product quality, you can set up more than one result that you consider as passing for your inspections. The following are some examples:

- **EXCELLENT** (Priority 10): Premium quality standards
- **GOOD** (Priority 9): Standard quality standards  
- **ACCEPTABLE** (Priority 8): Minimum acceptable quality
- **FAIL** (Priority 1): Below minimum standards

The following are some examples of result conditions for dimension measurement:

- **EXCELLENT**: 99.9..100.1 (tight tolerance)
- **GOOD**: 99.5..100.5 (standard tolerance)
- **ACCEPTABLE**: 99.0..101.0 (loose tolerance)
- **FAIL**: <>0 (any value outside acceptable range)

### Set up multiple failing results

To allow for different severity levels of defects, you can set up more than one result that you consider as failing for your inspections. The following are some examples:

- **CRITICAL** (Priority 1): Safety or regulatory failure
- **MAJOR** (Priority 2): Functional failure
- **MINOR** (Priority 3): Cosmetic or minor defect
- **PASS** (Priority 10): Acceptable quality

The following are some examples for business process integration. To learn more about business process integration, go to [Integrate with workflows](#integrate-with-workflows).

- **CRITICAL**: Immediate recall, supplier notification
- **MAJOR**: Quarantine, rework evaluation
- **MINOR**: Conditional release, customer notification

### Set up conditional and gray state results

You can set up conditional, or gray state, results for items that require extra evaluation. The following are some examples:

- **UNDER_REVIEW** (Priority 5): Requires management decision.
- **CONDITIONAL** (Priority 6): Passes with limitations.
- **RETEST** (Priority 4): Requires more testing.

## Integrate with workflows

You can integrate grates with workflows so that results trigger different workflow responses. The following examples are workflow responses that specific results might trigger:

- **FAIL** result blocks the lot and creates a negative adjustment.
- **CRITICAL** result immediately notifies the supplier.
- **RETEST** result creates and schedules another inspection.

### Document control integration

Results control transaction permissions:

**Sales integration**:

- **PASS** results allow sales shipments.
- **FAIL** results block sales shipments.
- **CONDITIONAL** results require approval.

**Production integration**:

- **PASS** results allow consumption.
- **FAIL** results block material usage.
- **UNDER_REVIEW** results require supervisor approval.

### Reporting and analytics

**Result-based reporting**:

- Quality scorecards by result distribution
- Trend analysis of result patterns
- Vendor performance by result outcomes
- Customer satisfaction correlation with results

## Best practices for result configuration

This section describes good design principles to consider when you set up your results.

**Keep it simple**:

- Start with basic pass, fail, and in progress results.
- Add complexity only when the business value is clear.
- Ensure that users understand the meanings of your results.

**Business alignment**:

- Align results with business processes.
- Match results to decision points.
- Consider customer and supplier perspectives.

**Consistent logic**:

- Use consistent condition syntax across fields.
- Maintain logical orders of priority.
- Document your result definitions and how to use them.

### Change management

**Grade condition updates**:

- Understand that changes don't affect existing tests.
- Plan updates to happen during periods of low-activity.
- Communicate your changes to the quality team.

**Template migration**:

- Inspection result changes on noncritical templates first.
- Provide training on the meanings of new results.
- Monitor effect on quality processes.

### Performance considerations

The following are things to consider related to result complexity:

- Complex conditions can affect test performance.
- Limit the number of active results to business needs.
- Regularly clean up unused results.

## Troubleshooting results

The following sections describe typical issues and suggest solutions.

### Inspections don't calculate the expected results

- Review result condition syntax.
- Check the order of priority.
- Verify the condition inheritance from fields to the template.

### Results aren't available in inspection templates

- Check your settings for result copy behavior.
- Verify that the result isn't set to **Do Not Copy**.
- Manually add the result to the template, if needed.

### My workflow doesn't start

- Confirm that the workflow condition matches the result code.
- Check the result code spelling and case sensitivity.
- Review the workflow activation status.

## Validate results

The following are ways to test your result logic:

- Use the **Value to Inspect** feature in result configuration.
- Validate your boundary conditions and edge cases.
- Validate result calculations with sample data.

The following are ways to validate your process:

- Create validation scenarios for each result outcome.
- Verify business process responses to results.
- Confirm that your reports display results correctly.

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)