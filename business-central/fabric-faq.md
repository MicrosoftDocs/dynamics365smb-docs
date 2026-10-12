---
title: FAQ About Mirroring Business Central Data to Microsoft Fabric
description: Get answers about availability, setup, supported data, synchronization, capacity, and licensing for mirroring Business Central data to Fabric.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: faq
ms.collection:
ms.date: 10/08/2026
ms.custom: bap-template
ai-usage: ai-assisted
---
# FAQ about mirroring Business Central data to Microsoft Fabric

This article answers common questions about mirroring Business Central data to Microsoft Fabric.

> [!IMPORTANT]
> This feature is in development. Availability, requirements, and limits might change before public preview or general availability.

## Availability and requirements

### Is the feature in private preview, public preview, or generally available?

The feature is currently in private preview. Public preview is expected within the next few weeks.

### Which version of Business Central is required?

The feature requires Business Central 2026 release wave 2. The final minimum update isn't confirmed. The expected minimum version is 29.0.

### Which Fabric capacity is required?

Mirroring requires Microsoft Fabric capacity. Currently, you need an F SKU, commonly F2 or higher, or an existing P SKU capacity.

### What are the licensing and consumption costs?

Business Central doesn't add a licensing or consumption charge for mirroring. A Microsoft Fabric capacity is required, and the associated Fabric capacity charges apply.

### Where is the feature available?

The feature is available globally. Geographic and tenant restrictions haven't been identified.

## Setup and configuration

### Does Business Central appear as a source in the Fabric mirroring experience?

No. First, create an open mirrored database in Fabric. Then, configure Business Central to replicate data to that database.

### Does configuration start in Business Central, Fabric, or both?

Configuration takes place in both products:

1. Create an open mirrored database in Fabric.
1. Configure Business Central to use the open mirrored database.
1. Choose the Business Central companies and tables to synchronize.

### How are environments, companies, and tables configured?

You configure mirroring separately for each Business Central environment. On the **Microsoft Fabric Mirroring Setup** page, choose the companies and tables to synchronize.

### Are standard and extension tables supported?

Yes. You can mirror any AL table that is stored in the Business Central SQL database, including standard and extension tables.

### Can I choose which fields to mirror from a table?

No. Mirroring includes all fields in a selected table. The mirrored table is a near real-time replica of the Business Central data.

### How are schema changes handled?

Specific behavior and limitations for schema changes aren't documented yet.

## Synchronization behavior

### How does Business Central extract data for mirroring?

Business Central uses an internal replication service. Mirroring doesn't use Business Central APIs.

### What is the expected synchronization latency?

Incremental changes typically synchronize within minutes. Latency depends on how frequently the data changes in Business Central. The initial synchronization of historical data takes longer than subsequent incremental synchronizations.

### Are deleted records synchronized?

Yes. Mirroring supports deleted records.

### Does mirroring affect Business Central API limits?

No. Mirroring doesn't use Business Central APIs and therefore doesn't consume their limits.

## Limits

### Are there limits on tables, rows, or data volume?

You can select up to 1,000 tables per tenant for synchronization. No limits on row counts or data volume were identified during the private preview. Additional limits might be introduced or documented before public preview or general availability.
