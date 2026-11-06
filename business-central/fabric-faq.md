---
title: Business Central Mirroring to Microsoft Fabric FAQ
description: Get answers about availability, setup, supported data, synchronization, capacity, and licensing for mirroring Business Central data to Fabric.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: faq
ms.date: 10/29/2026
ms.custom: bap-template
ai-usage: ai-assisted
---
# FAQ about mirroring Business Central data to Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article answers common questions about mirroring Business Central data to Microsoft Fabric.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Availability and requirements

### Is the feature in private preview, public preview, or generally available?

The feature is in preview. Review the preview notice in this article and the prerequisites in [Set up data mirroring](admin-set-up-fabric-mirroring.md#prerequisites) before you begin.

### Which version of Business Central is required?

Use a Business Central online environment that supports the Microsoft Fabric Mirroring (Preview) extension. Check the compatibility requirements of the extension version that you install.

Learn more in [Prerequisites for data mirroring](admin-set-up-fabric-mirroring.md#prerequisites).

### Which Fabric capacity is required?

Use a workspace assigned to an active Microsoft Fabric capacity. A paused or deleted capacity stops Fabric replication. For current capacity requirements, see [Configure Microsoft Fabric open mirrored databases](/fabric/mirroring/open-mirroring-tutorial#prerequisites).

### What are the licensing and consumption costs?

An active Fabric capacity is required. Fabric doesn't charge for the background compute used for mirroring replication. Mirrored storage has a capacity-based free allowance, and querying through SQL, Power BI, or Spark incurs the usual charges. Review [Cost of mirroring](/fabric/mirroring/overview#cost-of-mirroring) and your licensing terms before you plan capacity.

### Where is the feature available?

The setup described in these articles applies to Business Central online. The Fabric workspace must be in the same Microsoft Entra tenant as the Business Central environment. Check that the feature and a compatible app version are available in your environment before you configure the connection.

## Setup and configuration

### Does Business Central appear as a source in the Fabric mirroring experience?

No. First, create an open mirrored database in Fabric. Then, configure Business Central to replicate data to that database.

### Does configuration start in Business Central, Fabric, or both?

Configuration takes place in both products:

1. Create an open mirrored database in Fabric.
1. Create the service principal for the Microsoft-provided **Dynamics 365 Business Central Fabric Export** application, and grant it access to the Fabric workspace.
1. Configure Business Central to use the open mirrored database.
1. Choose the Business Central companies and tables to synchronize.
1. Start synchronization and monitor its results.

### Do I need my own app registration and client secret?

No. Business Central uses the Microsoft-provided **Dynamics 365 Business Central Fabric Export** application. Create its service principal in your tenant and grant it access to the destination workspace. Learn more in [Set up authentication](admin-set-up-fabric-mirroring.md#set-up-authentication).

### When do I need to enter Principal ID?

Enter the enterprise application's Object ID only if you use **Add to workspace** in Business Central. Don't enter its application (client) ID. If access is already granted in Fabric, you can leave **Principal ID** blank and skip that action.

### What's the difference between Connect to Fabric and Start synchronization?

**Connect to Fabric** requests the background connection setup. Wait until **Setup Complete** is selected before you select **Start synchronization**. At least one company must be enabled and one table selected.

**Finish** only completes the assisted setup guide. It doesn't start synchronization.

### Why can't I turn on Export Enabled?

**Export Enabled** is a read-only status that Business Central updates. It isn't a configuration switch. Background operations don't necessarily update the displayed value immediately. Select **Refresh page** and check **Fabric Synchronization Overview** for the operation's result.

Use **Setup Complete** to confirm connection setup, and the synchronization overview and details to verify exports. Learn more in [Understand the setup and export status](admin-set-up-fabric-mirroring.md#understand-the-setup-and-export-status).

### How are environments, companies, and tables configured?

You configure mirroring separately for each Business Central environment. On the **Microsoft Fabric Mirroring Setup (Preview)** page, choose the companies and tables to synchronize.

### Are standard and extension tables supported?

You can select eligible tables from the table lookup, including standard and extension tables that pass the app's export validation. Not every AL table is eligible. The app filters the lookup before you select tables.

### Can I choose which fields to mirror from a table?

The setup pages let you select tables, not a custom list of individual fields. Field eligibility is part of the app's export validation, so don't assume that every AL field can be mirrored.

### How are schema changes handled?

Review synchronization results after changes to your source tables or extensions. If you need a new full snapshot, use **Reset table**, as described in [Request a full snapshot for one table](admin-manage-fabric-export.md#request-a-full-snapshot-for-one-table). Investigate schema errors before resetting the entire connection.

Fabric has its own schema compatibility rules. Learn more in [Coordinate source schema changes](/fabric/mirroring/open-mirroring-best-practices#coordinate-source-schema-changes).

## Synchronization behavior

### How does Business Central extract data for mirroring?

The app requests setup and export operations from the Business Central platform. Its configuration and monitoring APIs aren't endpoints for reading each selected business table.

### What is the expected synchronization latency?

**Minutes Between Exports** controls the interval between continuous export runs. End-to-end latency also includes the export work and Fabric's ingestion of the data. Use the run timestamps and Fabric replication monitor to measure progress for your environment rather than assuming a fixed completion time.

### Are deleted records synchronized?

Yes. Mirroring supports deleted records.

### Does mirroring affect Business Central API limits?

The app doesn't expose the selected business tables through its configuration and monitoring APIs. Requests that your tools make to those APIs are still API calls and remain subject to the applicable Business Central limits.

### Do I need to reconnect every time I resume synchronization?

No. **Stop synchronization** preserves the connection and synchronization state. Use **Start synchronization** to resume. **Reset** removes the connection and synchronization state. Don't use Reset for a temporary pause.

### What happens to mirroring settings during environment configuration cleanup?

The app clears the Fabric destination and authentication values and resets the setup and export status fields. Company and table selections, package definitions, and logs remain. Configure a new connection before you use mirroring in the cleaned environment. Learn more in [Reconnect after environment configuration cleanup](admin-manage-fabric-export.md#reconnect-after-environment-configuration-cleanup).

### Does Reapply remove tables that aren't in a package anymore?

No. **Reapply** adds missing selections from the current package definition. To remove stale selections, deactivate and activate the package. Importing a definition with a new version can also release removed package tables. Tables remain selected if another package or a manual selection still claims them. Learn more in [Use configuration packages](admin-manage-fabric-export.md#use-configuration-packages).

## Limits

### Are there limits on tables, rows, or data volume?

The app supports up to 1,000 selected tables across manual selections and active configuration packages. Selecting the same table through multiple packages doesn't count it multiple times.

This table-selection limit isn't a guarantee of unlimited rows, data volume, or Fabric resources. Review the [open mirroring guidance](/fabric/mirroring/open-mirroring) and your capacity requirements.

## Related information

[Data mirroring to Microsoft Fabric from Business Central](admin-fabric.md)  
[Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md)  
[Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md)  
[Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
