---
title: Italian Subcontracting
description: Master Production Scheduling (MPS) and Material Requirements Planning (MRP) enable contractors to efficiently manage outsourced and subcontracted components.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: master production scheduling, MPS, material requirements planning, MRP, subcontracting, Italian version
ms.search.form: 12152, 12153, 12154, 12155, 12156, 35490, 35491
ms.date: 07/02/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Italian subcontracting

> [!NOTE]
> This Italy-specific subcontracting functionality is deprecated and will be removed in a future release. It's replaced by the **Subcontracting** app, which is available for all countries/regions and provides the same capabilities with additional features. To learn more, go to [Subcontracting overview](../../production-how-to-subcontract-manufacturing.md).

Starting with version 28.3, legacy Italian subcontracting is **hidden by default** for new environments. To re-enable the legacy functionality, go to the **Manufacturing Setup** page, choose **Actions** > **Legacy Subcontracting** > **Activate Legacy Subcontracting**.

Companies contracted for production often outsource the production of components to subcontractors. In order to know how many components to transfer to the subcontractor, there's a link between the subcontractors' operations and the BOM. This facilitates Master Production Scheduling (MPS) and Material Requirements Planning (MRP), and enables contractors to manage their outsourced and subcontracted components.  

Special unit prices are often negotiated between main contractors and subcontractors, so an extra subcontracting price list is available.  

## Work in progress

You can send an item to a subcontractor and have the subcontractor return it as a Work in Progress (WIP) to the main contractor. You can also send and receive groups of items without forced reference to the item card.  

## Migrate to the Subcontracting app

An **IT Subcontracting Migration** app is available to help you migrate open data from the legacy Italian subcontracting functionality to the Subcontracting app.

### Prerequisites

- The environment must be a **sandbox**. Production environment support is planned for a later release.
- Both the **Subcontracting** app and the **IT Subcontracting Migration** app must be installed.
- All open WIP transfer orders and related purchase orders must be completed before you run the migration.

### What gets migrated

The migration moves the following open data to the Subcontracting app:

- Vendors (subcontractor setup)
- Purchase headers and lines
- Transfer headers and lines
- Production order components
- Production order routing lines
- Routing lines (master data)
- Subcontractor prices (copied to the new pricing schema)

### Important limitations

- The migration is **irreversible**. There's no rollback once the migration runs.
- The affected tables are locked during execution.
- Historical and posted data isn't migrated. Only open documents and master data are moved.
- The legacy subcontracting objects are marked as `ObsoleteState = Pending` in version 27.0 and will be removed in a future version.


## Related information

- [Subcontracting overview](../../production-how-to-subcontract-manufacturing.md)
- [Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
