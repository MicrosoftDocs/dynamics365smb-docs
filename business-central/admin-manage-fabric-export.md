---
title: Manage Business Central Synchronization with Microsoft Fabric
description: Select Business Central companies and tables, use configuration packages, and control ongoing synchronization with Microsoft Fabric.
author: jswymer
ms.topic: how-to
ms.search.keywords: Fabric, data mirroring, replication, synchronization, configuration package, companies, tables
ms.search.form: Primary_48511, 48508, 48512, 48515, 48513
ms.date: 10/08/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Manage Business Central data synchronization with Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After you configure data mirroring from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft Fabric, use the **Microsoft Fabric Mirroring Setup** page to choose the data to synchronize and control synchronization.

<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

> [!IMPORTANT]
> - This feature is planned to become available as a production-ready preview in October 2026. Delivery timing and functionality might change.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520).

## Assign permissions for data mirroring

Assign permission sets according to each person's responsibilities.

| Permission set | Use |
| --- | --- |
| **MS Fabric Mirroring - Admin** | Set up the connection, select companies and tables, manage configuration packages, control synchronization, and view monitoring information. |
| **MS Fabric Mirroring - Activate** | Activate, deactivate, and reapply configuration packages. |
| **MS Fabric Mirroring - Read** | View synchronization overview and detail information. |

## Select companies

1. Open the **Microsoft Fabric Mirroring Setup** page.
1. Select **Configuration** > **Companies**.
1. Select **Add company**, and then select a company.
1. Repeat the previous step for each company to synchronize.

Clear the **Enabled** field to temporarily skip a company without removing its configuration.

For each enabled company, synchronize tables that store data per company. Synchronize tables that don't store data per company once.

## Select tables

You can select up to 1,000 tables for synchronization.

1. Open the **Microsoft Fabric Mirroring Setup** page.
1. Select **Configuration** > **Tables**.
1. Select **Add table**.
1. Select one or more Business Central tables.

Business Central assigns a Fabric entity name and identifies whether each table stores data per company. Use the **Fabric Schema Type** field to choose whether the table belongs to the data or logging schema.

## Use configuration packages

Configuration packages let you add a curated set of tables instead of selecting tables individually. The Microsoft Fabric Mirroring app includes the **MS-STD** package, which contains 256 standard Business Central tables for analytics scenarios.

1. Open the **Microsoft Fabric Mirroring Setup** page.
1. Select **Configuration** > **Import/Export Configuration**.
1. Select a package, and then use one of the following actions:

   - **Activate**: Adds the package's tables to the synchronization list.
   - **Deactivate**: Removes the package's table selections. A table remains selected if you selected it manually or if it's included in another active package.
   - **Reapply**: Adds changes from a newer package version. Reapply doesn't remove stale selections. Deactivate and activate the package to fully align the selection with the latest package definition.

You can also import or export package definitions as JSON files. You must deactivate a package before you delete it.

> [!NOTE]
> Activating or reapplying a package can't increase the total selection beyond the 1,000-table limit.

## Configure synchronization behavior

Use the following fields on the **Microsoft Fabric Mirroring Setup** page:

| Field | Description |
| --- | --- |
| **Minutes Between Exports** | Specifies the interval between continuous synchronization runs. A change takes effect with the next run. |
| **Max Consecutive Failed Runs** | Specifies how many consecutive failures are allowed before synchronization stops. Enter a value from 1 through 5. The default is 2. |
| **Fabric Data Namespace** | Specifies the Fabric schema for synchronized business data. The default is `BusinessCentral`. |
| **Fabric Logging Namespace** | Specifies the Fabric schema for synchronization logs. The default is `BusinessCentral_log`. |

You can change the namespace fields only before the mirroring setup is complete.

## Start, stop, or reset synchronization

| Action | Result |
| --- | --- |
| **Start synchronization** | Enables change tracking on the selected tables and starts recurring synchronization. If a synchronization run is already active, Business Central doesn't start another run. |
| **Stop synchronization** | Cancels an in-progress run and pauses recurring synchronization. The Fabric connection and synchronization state are preserved so that you can resume later. |
| **Reset** | Cancels in-progress work, removes the tenant's mirroring resources, resets all watermarks, and deletes the synchronization summary and detail records. |

Setup, start, stop, and reset requests run asynchronously. Use the monitoring pages to confirm that an operation finished.

You can't change the Fabric workspace or open mirrored database while the **Export Enabled** field is selected. Select **Reset** to clear the connection before you select a different destination.

## Related information

- [Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md)
- [Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md)
- [Microsoft Fabric Export APIs](/dynamics365/business-central/dev-itpro/developer/devenv-fabric-export-apis)

[!INCLUDE[footer-include](includes/footer-banner.md)]
