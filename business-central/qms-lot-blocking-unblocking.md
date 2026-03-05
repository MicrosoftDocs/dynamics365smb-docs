---
title: Block or unblock lots
description: Learn how to block and unblock inventory lots using workflows and grade-specific controls to ensure quality compliance.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Block or unblock lots

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to automatically block and unblock inventory lots based on quality inspection results using workflows and result-specific controls. There are two main approaches for lot blocking:

- **Workflow-Based Blocking**: Block lots using workflows.
- **Grade-Based Blocking**: Document-specific blocking based on inspection results.

Both approaches help ensure that noncompliant inventory isn't used inappropriately, while allowing flexible quality control processes.

<!--### Enable workflow integration

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Management Setup**, and then choose the related link.
2. On the **Defaults** FastTab, turn on the **Workflow Integration Enabled** toggle.

   > [!TIP]
   > By default, the toggle is hidden. To access it, you might have to choose **Show more**.

> [!NOTE]
> If you don't turn on the **Enable Workflow Integration** toggle, the quality management events for workflows aren't available. -->

## Workflow-based lot blocking

Workflow-based blocking creates or modifies **Lot No. Information Card** pages to completely block lots for all transactions (except warehouse operations when configured). You access **Lot No. Information Card** pages from the **Lot No. Information List** page.

### Set up a block-on-fail workflow

The following procedure describes the key settings for a workflow that blocks lots when quality inspections fail.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Workflows**, and then choose the related link.
1. Create a new workflow. For example, name it "Block Lot Example."
1. Configure a workflow step, as follows:

   1. In the **When Event** field, choose **A Quality Inspection is Finished**.
   1. In the **On Condition** field, add a filter for the **Result Code** field, and then set **FAIL** as the filter value.
   1. In the **Then Response** field, choose **Block Lot in the Inspection**. This setting creates a lot information card with the status **Blocked**.

### Set up block-on-creation, and unblock on pass workflows

The following procedures describe the key settings for workflows that block lots immediately when inspections are created, and unblock them when inspections pass.

#### Block on inspection creation

1. Create a new workflow. For example, name it "Block Lot on Creation."
1. In the **When Event** field, choose **A Quality Inspection is Created**.
1. In the **Then Response** field, choose **Block lot in the inspection**.

   The result is that all lots are blocked immediately when inspections are created.

#### Unblock on pass

1. Create a new workflow. For example, name it "Unblock on Pass."  
1. In the **When Event** field, choose **A Quality Inspection is Finished**.
1. In the **On Condition** field, add a filter for the **Result Code** field, and then set **Pass** as the filter value.
1. In the **Then Response** field, choose **Unblock Lot in the Inspection**.

## Result-based document blocking

Result-based blocking provides granular, document-specific controls based on the current grade of quality inspection. Unlike complete lot blocking, this approach lets you block specific transaction types while permitting others, based on the inspection result.

The following list describes how [!INCLUDE [prod_short](includes/prod_short.md)] evaluates results:

- The system evaluates current inspection results for the lot/serial number.
- The result configuration determines transaction permissions.
- Multiple inspections for the same lot might have different results.
- The system can consider specific inspections when it evaluates restrictions.

To learn more about quality inspection results, go to [Configure quality inspection results](qms-configuring-grades.md).

### Examples of result configurations

#### INPROGRESS result (priority 0)

Use this result configuration to restrict most transactions when inspections are in progress. The business logic is that you can store and move items for inspections, but not use them in business transactions.

- **Allow Sales**: No (can't sell unconfirmed quality)
- **Allow Transfer**: No (prevent distribution before inspection is complete)
- **Allow Consumption**: No (can't use in production)
- **Allow Pick**: No (prevent picking for shipments)
- **Allow Put-away**: Yes (allow warehouse storage)
- **Allow Movement**: Yes (allow movement to inspection areas)
- **Allow Output**: Yes (might be acceptable for work-in-progress)

#### FAIL result (priority 1+)

Use this result configuration to require quarantine when a quality inspection fails. The business logic is to block all use and allow only quarantine and disposal activities.

- **Allow Sales**: No (can't sell nonconforming items)
- **Allow Transfer**: No (prevent distribution of failed items)
- **Allow Consumption**: No (can't use defective materials)
- **Allow Pick**: No (prevent accidental picking)
- **Allow Put-away**: Yes (allow quarantine storage)
- **Allow Movement**: Yes (allow movement for disposal)
- **Allow Output**: No (prevent use in production)

#### PASS result (highest priority, evaluated last)

Use this result configuration to allow normal business operations when a quality inspection passes. The business logic is to allow transactions for items with confirmed quality.

- **Allow Sales**: Yes (approved for customer shipment)
- **Allow Transfer**: Yes (approved for distribution)
- **Allow Consumption**: Yes (approved for production use)
- **Allow Pick**: Yes (approved for warehouse operations)
- **Allow Put-away**: Yes (normal warehouse operations)
- **Allow Movement**: Yes (normal warehouse operations)
- **Allow Output**: Yes (approved for production output)

#### Example of a CONDITIONAL (medium priority) custom result

Use this result configuration when a grade is conditionally acceptable with restrictions. The business logic is to allow limited use, and perhaps require management approval.

- **Allow Sales**: No (requires customer approval)
- **Allow Transfer**: Yes (can transfer with documentation)
- **Allow Consumption**: Yes (acceptable for noncritical applications)
- **Allow Pick**: Yes (with proper documentation)
- **Allow Put-away**: Yes (normal storage)
- **Allow Movement**: Yes (normal handling)
- **Allow Output**: No (not suitable for finished goods)

## Implement lot blocking scenarios

This section describes some typical scenarios for lot blocking.

### Block on failure only

**Business Rule**: Lots remain available until inspections fail.

**Implementation**:

1. **Workflow**: Block lot when an inspection finishes with "FAIL" result.
2. **Result Setup**: The **INPROGRESS** result allows all transactions.

The following process is a sample flow for this implementation:

1. You receive the item and put it away normally.
2. You create and run a quality inspection.  
3. The lot remains available for all operations.
4. If the inspection fails, the lot becomes blocked. If it passes, no blocking happens.

### Block during inspection

**Business Rule**: Block lots immediately when an inspection begins.

**Implementation**:

1. **Workflow 1**: Block lot when an inspection is created.
2. **Workflow 2**: Unblock lot when an inspection passes with "PASS" result.
3. **Result Setup**: Configure document-specific controls if needed.

The following process is a sample flow for this implementation:

1. You receive the item.
2. You create and run a quality inspections, and the lot is immediately blocked.
3. Put-away might still be allowed (warehouse operations).
4. If the inspection fails, the lot remains blocked. If it passes, normal operations resume.

### Document-specific controls

**Business Rule**: Prevent sales, but allow warehouse operations during inspections.

**Implementation**:

1. **No Workflows**: Rely entirely on result controls.
2. **In Progress Result**:
   - Allow Put-away: Yes
   - Allow Movement: Yes
   - Allow Pick: No
   - Allow Sales: No

The following is a sample process flow for this implementation:

1. You receive the item and create an inspection.
2. Put-away proceeds normally (allowed).
3. Sales orders can't be posted (blocked).
4. Warehouse movements are allowed for the quality area.
5. Inspection completion changes the result, updating permissions.

## Work with blocked lots

The following sections describe some actions you can take while a lot is blocked.

### Identify blocked lots

It't easy to find out whether a lot is blocked. Open the **Lot No. Information List** page, and check the **Blocked** field. You can also use quality inspection references.

For **Quality Inspection Integration**, inspections show related lot blocking status. You can go from inspections to lot information and review blocking history.

### Manage blocked inventory

You can do the following for warehouse operations:

- Blocked lots might still allow warehouse movements.
- Use for quarantine and disposal processes.
- Configure result controls for specific needs.

For disposal, you can take the following actions:

- Move to quarantine areas.
- Process through rework procedures.
- Create negative adjustments for disposal.
- Return to vendors if appropriate.

<!--## Test lot blocking configuration

### Test Scenario: Purchase receipt with blocking

1. **Create a purchase order**:
   - Item with lot tracking.
   - Location with appropriate setup.
   - Post warehouse receipt.

2. **Verify test creation**:
   - Quality inspection is created automatically.
   - Check the lot blocking status (depends on configuration).

3. **Test a sales transaction**:
   - Create a sales order for the same lot.
   - Try to post a shipment.
   - Verify the blocking behavior.

4. **Complete a quality test**:
   - Enter the measurement values.
   - Finish the inspection with a pass or fail result.
   - Verify that the lot status changes appropriately.

### Validation points

**Automatic Blocking**:

- Inspections are created and lots are blocked as configured.
- Blocking prevents inappropriate transactions.
- Warehouse operations follow result settings.

**Test Completion**:

- Passing inspections unblock lots (if configured).
- Failing inspections maintain or create blocking.
- Result changes update transaction permissions. -->

## Related information

[Purchase Receipt Inspections without Warehouse Handling](qms-purchase-receipt-testing-simple.md)  
[Purchase Receipt Inspections with Warehouse Handling](qms-purchase-receipt-testing-warehouse.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Processing Non-Compliant Items](qms-non-compliant-processing.md)  
[Quality Management Overview](qms-overview.md)