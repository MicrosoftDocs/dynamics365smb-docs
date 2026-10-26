---
title: Italian Subcontracting and Migration
description: Learn about legacy Italian subcontracting in Business Central, check migration prerequisites, and move applicable data to the Subcontracting app.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: master production scheduling, MPS, material requirements planning, MRP, subcontracting, Italian version
ms.search.form: 12152, 12153, 12154, 12155, 12156, 35490, 35491
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Italian subcontracting

> [!NOTE]
> This Italy-specific subcontracting functionality is deprecated and will be removed in a future release. It's replaced by the **Subcontracting** app, which is available for all countries/regions and provides the same capabilities with additional features. To learn more, go to [Subcontracting overview](../../production-how-to-subcontract-manufacturing.md).

Starting with version 28.3, legacy Italian subcontracting is **hidden by default** for new environments. To re-enable the legacy functionality, go to the **Manufacturing Setup** page, choose **Actions** > **Legacy Subcontracting** > **Activate Legacy Subcontracting**.

You can't activate legacy subcontracting while the **Subcontracting** app is installed. Activating or disabling the legacy feature requires a session restart.

Companies contracted for production often outsource the production of components to subcontractors. In order to know how many components to transfer to the subcontractor, there's a link between the subcontractors' operations and the BOM. This facilitates Master Production Scheduling (MPS) and Material Requirements Planning (MRP), and enables contractors to manage their outsourced and subcontracted components.  

Special unit prices are often negotiated between main contractors and subcontractors, so an extra subcontracting price list is available.  

## Work in progress

You can send an item to a subcontractor and have the subcontractor return it as a Work in Progress (WIP) to the main contractor. You can also send and receive groups of items without forced reference to the item card.  

## Migrate to the Subcontracting app

An **IT Subcontracting Migration** app is available to help you migrate open data from the legacy Italian subcontracting functionality to the Subcontracting app.

### Prerequisites

- The environment must be a **sandbox**. Production environment support is planned for a later release.
- The **Subcontracting** app must be installed. If legacy data exists, the **IT Subcontracting Migration** app is also required.
- Complete transfer lines with outstanding WIP quantities and purchase order lines with outstanding WIP items before you disable legacy subcontracting.

### Run the migration

1. Open **Manufacturing Setup**, and choose **Legacy Subcontracting** > **Disable Legacy Subcontracting**.
1. If prompted, install the required app. After installation and the session reload, run **Disable Legacy Subcontracting** again. You might need to repeat this step to install both apps.
1. Resolve any WIP or location errors, and confirm the migration when prompted.

Disabling the legacy feature migrates the applicable data when legacy data exists. After migration completes, the feature is disabled and the session restarts.

### Check subcontracting locations

Legacy Italian subcontracting allows locations that the Subcontracting app doesn't accept. The migration checks locations referenced by both vendor cards and purchase headers:

- For a vendor's subcontracting location, **Bin Mandatory**, **Require Pick**, **Require Put-away**, **Require Receive**, and **Require Shipment** must be cleared.
- For a location referenced only by a purchase header, **Bin Mandatory** must be cleared.
- For either use, **Use As In-Transit** must be cleared, and the location must exist.

> [!IMPORTANT]
> Resolve incompatible location settings or replace the location references on vendor cards and purchase headers before migration. The stricter vendor rules apply when the same location is used on both.

### What gets migrated

The migration moves the following open data to the Subcontracting app:

- Vendors (subcontractor setup)
- Purchase headers and lines
- Transfer headers and lines
- Production BOM component supply methods that can be determined from their usage
- Production order components
- Production order routing lines
- Routing lines (master data)
- Subcontractor prices (copied to the new pricing schema)

### Important limitations

- There's no automatic rollback after a completed migration. Test the results and your recovery approach in a sandbox.
- The affected tables are locked during execution.
- Historical and posted data isn't migrated. Only open documents and master data are moved.
- Legacy subcontracting objects are marked as obsolete and are scheduled for removal. Use the Subcontracting app for new setups.


## Related information

- [Subcontracting overview](../../production-how-to-subcontract-manufacturing.md)
- [Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
