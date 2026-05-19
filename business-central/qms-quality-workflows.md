---
title: Quality management workflows
description: Learn how to automate quality management processes using workflows.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 
ms.date: 03/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management workflows

This article explains how to set up and use workflows to automate quality management processes.

Quality Management integrates with workflows in [!INCLUDE [prod_short](includes/prod_short.md)] to automate responses to quality inspection events. Workflows can automatically run business actions when quality inspections are created, finished, or when specific conditions are met. For example, quality management workflows can:

- Block and unblock lots.
- Move inventory.
- Create negative adjustments.

## Typical quality workflow events

The following sections describe often-used workflow events and conditions.

### When events

**When a Quality Inspection is Created**:

- This event triggers automatically when inspection generation rules create new inspections.
- Use the event for immediate actions, such as blocking lots when you create inspections for them.
- The event is available for all inspection creation methods. For example, purchase receipts, production output, and manual creation.

**When a Quality Inspection is Finished**:

- This event triggers when inspections are completed and finalized.
- Use the event for disposal actions based on inspection results.
- This event is the most popular for quality workflows.

### Workflow conditions

**Result code conditions**:

- Result code equals "PASS" for successful inspection completion.
- Result code equals "FAIL" for failed inspection processing.
- Result code equals "INPROGRESS" for inspections in progress.
- Custom Result codes you configure.

**Additional conditions**:

- Location codes for site-specific workflows.
- Item numbers for product-specific processing.
- Inspection template codes for template-specific responses.

## Workflow response actions

The following sections describe the responses, or actions, that happen after an event.

### Lot, serial, and package number blocking actions

**Block the Lot (Serial, Package) in the Inspection**:

- Creates a **Lot No. Information Card** page with the status **Blocked**. The status prevents all transactions for the lot until you manually unblock it.
- The standard lot blocking functionality in [!INCLUDE [prod_short](includes/prod_short.md)] applies. To learn more, go to [Block items or item variants from use in sales, purchasing, service, and production](inventory-how-block-items.md).

**Unblock the Lot (Serial, Package) in the Inspection**:

- Removes lot blocking from previously blocked lots, and restores normal transaction abilities.
- This action is typically used with passing inspection results.

### Inventory movement actions

**Move Inventory to Different Bin**:

- Automatically relocates inventory based on inspection results.
- Uses movement worksheets, movement documents, or reclassification journals.
- Supports directed put-away and pick locations.

**Create Transfer Order**:

- Moves inventory between locations.
- Useful for quarantine or rework locations.
- You can configure the action for automatic or manual posting.

**Create Internal Put-away**:

- Generates a warehouse put-away for inventory staging.
- Supports quality inspection workflows in warehouse environments.

### Inventory adjustment actions

**Create Negative Adjustment**:

- Removes inventory for disposal or destructive testing.
- Uses item journals or warehouse item journals.
- Supports reason codes for audit trails.
- Can process full lots, specific quantities, or failed quantities only.

### Inspection creation actions

**Create Reinspection**:

- Automatically generates follow-up inspections.
- Useful for corrective action processes.
- Can use the same or different inspection templates.

> [!NOTE]
> Some workflows actions require that you configure journal and worksheet batches on the **Quality Management Setup** page:
>
> - Use **Item Journal Batch** for nonwarehouse location adjustments.
> - Use **Warehouse Item Journal Batch** for warehouse location adjustments.
> - Use **Warehouse Movement Worksheet** for directed put-away/pick movements.
> - Use **Warehouse Reclass Journal Batch** for warehouse reclassifications.
> - Use **Item Reclass Journal Batch** for nonwarehouse reclassifications.
> 
> When a disposition action creates multiple journal lines, for example, when the same lot exists in multiple bins, the system posts each line independently rather than as a single transaction. This means:
> - Lines that post successfully are committed immediately.
> - Lines that fail, for example, due to inventory shortages, locked records, or bin conflicts, remain in the journal for manual resolution.
> - The inspection status still transitions, for example, to **Finished**, even if some disposition lines fail. A single failing line doesn't block the entire operation.
>  
> This partial posting behavior preserves forward progress in high-volume or semi-automated environments and avoids rolling back successfully posted lines when an unrelated line fails. After a partial posting, check the relevant journal (warehouse journal or item journal) for unposted lines. These lines require manual attention before the disposition is fully complete.


## Examples of workflow configuration

The following sections provide examples of how to configure different workflows.

### Block a lot when an inspection fails

This sample configuration automatically quarantines lots that fail an inspection.

1. **Workflow Name**: **Block Lot on Failure**
2. **When Event**: **When a Quality Inspection is Finished**
3. **Condition**: **Result** equals **Fail**.
4. **Response**: Block the lot in the inspection.

The following are the outcomes of this example:

- Failed lots are immediately blocked from all transactions.
- Creates a **Lot No. Information Card** page for tracking.
- Prevents the accidental use of nonconforming materials.

### Preemptive lot blocking

These sample configurations block lots during inspections, and unblock them when they pass.

**Blocking workflow**:

1. **Workflow Name**: **Block Lot on Inspection Creation**
2. **When Event**: **When a Quality Inspection is Created**
3. **Condition**: None (applies to all tests)
4. **Response**: Block the lot in the inspection.

**Unblocking workflow**:

1. **Workflow Name**: **Unblock Lot on Pass**
2. **When Event**: **When a Quality Inspection is Finished**
3. **Condition**: **Result Code** equals **"Pass"**
4. **Response**: Unblock the lot in the inspection.

The following are the outcomes of this example:

- Lots are quarantined immediately when you create an inspection.
- Only passing inspections unblock lots for normal use.
- Prevents the use of materials you haven't inspected.

### Automatic movement between bins

This sample configuration moves failed items to the quarantine bin.

1. **Workflow Name**: **Move Failed Items to Quarantine**
2. **When Event**: **When a Quality Inspection is Finished**
3. **Condition**: **Result Code** equals **"Fail"**
4. **Response**: Move inventory to a different bin.
5. **Details**:
   - **Method**: Reclassification Journal
   - **Quantity**: Entire Lot
   - **Destination**: Quarantine bin
   - **Post Immediately**: No (requires manual review)

The following are outcomes of this example:

- Failed items are automatically staged for quarantine.
- Physical separation of conforming and nonconformant items.
- Maintain an audit trail of disposals.

### Negative adjustment for disposal

This sample configuration automatically disposes of failed or destructively inspected items.

1. **Workflow Name**: **Dispose Failed Items**
2. **When Event**: **When a Quality Inspection is Finished**
3. **Condition**: **Result Code** equals **"Fail"**
4. **Response**: Create a negative adjustment.
5. **Details**:
   - **Quantity**: Failed quantity (or entire lot)
   - **Reason Code**: **Quality Assurance**
   - **Post Immediately**: No (review required)

The following are outcomes of this example:

- An automatic inventory reduction for the unrecoverable items.
- Accurate cost accounting for quality losses.
- An audit trail for the disposed materials.




## Related information

[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Processing Non-Compliant Items](qms-non-compliant-processing.md)  
[Configuring Results](qms-configuring-grades.md)  
[Quality Management Setup](qms-setup.md)  
[Quality Management Overview](qms-overview.md)
