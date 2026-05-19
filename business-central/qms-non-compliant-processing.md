---
title: Handle items that failed a quality test
description: Learn how to handle noncompliant items, including workflows, inventory movements, and actions for failed quality inspections.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 20408,
ms.date: 03/11/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Process items that failed a quality inspection

This article explains how to deal with items that don't pass quality inspection. When goods fail a quality inspection, there are options to manually or automatically handle the noncompliant items:

- Block items to prevent the use of failed lots (serial and package numbers).
- Move items to quarantine areas.
- Remove unusable inventory.
- Transfer items to different locations.
- Return defective items to suppliers.

These options can be triggered automatically using workflows. To learn more, go to [Quality management workflows](qms-quality-workflows.md).

> [!Note]
> For items with lot, serial, or package tracking, you can specify how quality inspection results affect specific document transactions. For example, you can block purchase documents while inspections are in progress and block sales documents for failed inspections. Learn more at [Lot blocking and unblocking](qms-lot-blocking-unblocking.md)


The following sections describe some actions you can take when an item fails an inspection.

## Use manual actions on quality inspections

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection**, and then choose the related link.
1. Open the failed inspection.
1. Use the options on the **Actions** menu to run actions directly from the inspection results.

### Moving items after inspection failures

**Move Inventory**:

Run an inventory movement directly from the inspection results. The movement is prefilled with details about the failed lot, and maintains the connection between movement and quality failure.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Movement Methods**: Reclassification journal or movement worksheet/internal movement.
- **Source Filters**: Optional location and bin filters to limit movement source.
- **Destination**: Specify a target location and bin for quarantine or disposal.
- **Posting Options**: Post immediately, or create entries for later processing.

**Create Internal Put-away**:

Create internal put-away documents for warehouse locations.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Source Filters**: Optional location and bin filters.
- **Release Options**: Release immediately, create warehouse put-away, or keep open for review.
- **Usage**: Ideal for directed put-away and pick locations.

**Create Transfer items**

The action transfers items to another location for external processing, lab analysis, or disposal.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Source Filters**: Optional location and bin filters to limit transfer source
- **Destination**: Target location for transfer
- **Transfer Details**: Support for direct transfer or in-transit locations

### Removing items from inventory

The manual removal process involves using the **Create Negative Adjustment** option from the **Actions** menu on the **Quality Inspection** page.

The action decreases inventory quantity for disposal, destructive testing, or write-offs.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Source Filters**: Optional location and bin filters to limit adjustment source
- **Reason Codes**: Optional reason code for audit trail
- **Posting Options**: Post immediately, or create entries for later processing.

### Return items to vendors

The manual return process involves using the **Create Purchase Return** option from the **Actions** menu on the **Quality Inspection** page.

The action creates purchase return orders for vendor-related defects.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Return Reason**: Optional return reason code for vendor communication
- **Source Filters**: Optional location and bin filters
- **Credit Memo**: Optional vendor credit memo number field



### Change item tracking information

This section describes how to manually update information about items. Updating item information involves using the **Change Item Tracking** option from the **Actions** menu on the **Quality Inspection** page.

The action updates item tracking information such as lot numbers, serial numbers, package numbers, or expiration dates.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Tracking Changes**: Update the lot, serial, or package numbers, and the expiration date.
- **Source Filters**: Optional filters for locations and bins.
- **Posting Options**: Post immediately, or create entries for later processing.



## Related information

[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Purchase Receipt Inspections without Warehouse Handling](qms-purchase-receipt-testing-simple.md)  
[Quality Management Overview](qms-overview.md)
