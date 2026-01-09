---
title: Configure quality inspection results
description: Learn how to configure and manage quality inspection results, including result setup, priority rules, and business process integration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 01/08/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Configure quality inspection results

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to configure and use quality inspection results in quality management.

Quality inspection results represent the possible outcomes of quality inspections. Examples of typical results are Incomplete, Fail, and Pass. However, you can configure as many results as you want, and in what circumstances. Results with a lower number in the **Priority** field are evaluated first. If you're unsure what to configure, use the three defaults. To learn more about the defaults, go to [Result concepts](#result-concepts). Document-specific lot blocking is for combinations of items, variants, lots, serial numbers, and package numbers, and you can use it for serial-only tracking, or package-only tracking. Learn more at [Lot blocking and unblocking](qms-lot-blocking-unblocking.md)

## Result concepts

The following are the default results for quality inspections:

- **In Progress** (Priority 0): The inspection is incomplete or in progress.
- **Fail** (Priority 1): The inspection failed to meet quality criteria.  
- **Pass** (Priority 2): The inspection met quality criteria.

However, you can also create custom results:

- Create multiple passing results. For example, Excellent, Good, and Acceptable.
- Create multiple failing results. For example, Minor Defect, Major Defect, and Critical Failure.
- Create gray state results. For example, Under Review and Conditional Pass.

### Understand the default result structure

The following table shows an example of a configuration.

| Result Code | Description | Priority | Copy Behavior      | Allow Sales | Allow Purchase |
| ---------- | ----------- | -------- | ------------------ | ----------- | -------------- |
| INPROGRESS | In Progress | 0        | Automatically Copy | Block       | Allow          |
| FAIL       | Fail        | 1        | Automatically Copy | Block       | Allow          |
| PASS       | Pass        | 2        | Automatically Copy | Allow       | Allow          |

In this example, sales transactions for a lot are restricted until the quality inspection is complete and passes all criteria. If the inspection is incomplete or fails, sales are blocked. Purchase transactions, however, are always allowed.

### Evaluation sequence values

- Evaluation sequence 0 represents incomplete or ongoing inspections, and is evaluated first in result determination.
- Evaluation sequence 1 represents various failure conditions, and must have a higher number than incomplete results, but a lower number than pass results.
- Evaluation sequence 2 represents successful inspection outcomes, and is evaluated last in result determination. This must be the highest number in the sequence.

## Integrate with workflows

You can integrate grates with workflows so that results trigger different workflow responses. The following examples are workflow responses that specific results might trigger:

- **FAIL** result blocks the lot and creates a negative adjustment.
- **CRITICAL** result immediately notifies the supplier.
- **RETEST** result creates and schedules another inspection.

Learn more at [Quality management workflows](qms-quality-workflows.md).

## Configure quality inspection results

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Results**, and then choose the related link.
1. Choose **New** to create a new result.
1. In the **Code** field, enter a short name that indicates the state of the result. For example, Pass or Fail.
1. In the **Description** field, enter a short description of the result.
1. In the **Evaluation Sequence** field, enter a number that corresponds to the result. Learn more at [Evaluation sequence values](#evaluation-sequence-values).
1. In the **Copy Behavior** field, specify whether to automatically copy the result to new inspection templates.

   > [!TIP]
   > Automatically copying the result to new templates helps ensure that it's easily available for inspections. Choose not to copy the result means you must manually add the result, which is useful for specialized or conditional results.

1. In the **Result Visibility** field, specify whether to promote the result, which emphasizes it on various pages and reports. For example, **Certificate of Analysis** report shows promoted results.

   > [!TIP]
   > Promoting results display inline and are editable when you configure templates. They also display prominently when you run tests, and are featured in reports.

1. In the **Result Category** field, specify whether the result represents something good, or bad. For inconclusive results, leave the field blank.
1. In the **Finish Allowed** field, specify whether to allow inspections to be completed if they contain the result.
1. In the remaining fields, specify the transactions to allow when an inspection has the result.
1. In the **Override Style** field, specify how to emphasize the result.

<!--

I DON'T SEE ANY OF THIS

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
4. Configure conditions for the passing result. -->

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