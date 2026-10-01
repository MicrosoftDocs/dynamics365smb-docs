---
title: Process items that failed a quality inspection
description: Learn how to handle noncompliant items, including workflows, inventory movements, and actions for failed quality inspections.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20408,
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Process items that failed a quality inspection

This article explains how to deal with items that don't pass a quality inspection. When goods fail a quality inspection, you can manually or automatically handle them by using the following options:

- Block items to prevent the use of failed lots (serial and package numbers).
- Move items to quarantine areas.
- Remove unusable inventory.
- Transfer items to different locations.
- Return defective items to suppliers.

These options can be triggered automatically using workflows. Learn more in [Quality management workflows](qms-quality-workflows.md).

> [!NOTE]
> For items with lot, serial, or package tracking, you can specify how quality inspection results affect specific document transactions. For example, you can block purchase documents while inspections are in progress and block sales documents for failed inspections. Learn more in [Lot blocking and unblocking](qms-lot-blocking-unblocking.md).

The following sections describe some actions you can take when an item fails an inspection.

## Use actions on quality inspections

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection**, and then choose the related link.
1. Open the failed inspection.
1. Use the actions on the inspection to choose how to handle the affected inventory.

The available actions depend on the source, item tracking, inventory, location, and warehouse setup of the inspection.

### Choose the quantity to handle

Actions that move or remove inventory let you choose which quantity to handle:

- **Entire Lot/Serial/Package** uses positive posted inventory that matches the lot, serial number, or package number on the inspection and any source filters. Use this option only when the inspection specifies item tracking. It doesn't use the full inspection quantity for an item that isn't tracked.
- **Specific Quantity** uses the value in **Quantity to Handle**. If you enter `0`, the action uses the source **Quantity (Base)** from the inspection. You can use this behavior to handle the full inspection quantity for an item that isn't tracked.
- **Sample Quantity** uses the **Sample Size** from the inspection. The sample size must be greater than zero.
- **Passed Quantity** or **Failed Quantity** uses the respective quantity calculated from the inspection results.

The specified source location or bin must contain enough matching inventory for the requested quantity.

### Move inventory

Choose the **Move Inventory** action to move affected inventory to another location or bin, such as a quarantine area. The action uses an item reclassification journal for inventory locations or warehouse movement documents for locations that require warehouse handling.

You can move the entire tracked quantity, a specific quantity, the sample quantity, or the passed or failed quantity. Specify source and destination location and bin filters, and then post the movement immediately or create entries for later review.

### Create an internal put-away

Choose the **Create Internal Put-away** action to create an internal put-away for inventory at a warehouse location. Use the resulting warehouse document to move the items into the appropriate bin.

This action is available for locations that use directed put-away and pick with warehouse item tracking. You can keep the document open, release it, or release it and create the put-away.

### Transfer items

Choose the **Create Transfer Order** action to move affected inventory to another location for quarantine, external analysis, rework, or disposal. Complete the transfer order by using the normal transfer process.

Specify whether to use direct transfer or an in-transit location. If you leave the in-transit code blank, the transfer route can supply it.

### Remove items from inventory

Choose the **Create Negative Adjustment** action to reduce inventory for disposal, destructive testing, or write-off. Review and post the resulting item journal or warehouse item journal according to the location setup.

Choose the quantity to remove, add a reason code if needed, and then post immediately or create journal entries for later review. Configure the journal batches on the **Quality Management Setup** page.

### Return items to a vendor

Choose the **Create Purchase Return Order** action for an inspection related to a purchase. Review the vendor, item, quantity, item tracking, and return reason on the resulting document before you post it.

The received quantity that you didn't already return must be sufficient. You can specify a return reason and vendor credit memo number.

### Change item tracking information

Choose the **Change Item Tracking** action to reclassify lot, serial, or package information for affected inventory. Review and post the resulting journal according to the location setup.

Specify at least one new lot, serial, package, or expiration-date value. You can post the change immediately or create entries for later review.

## Related information

[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Quality Management Overview](qms-overview.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
