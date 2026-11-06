---
title: Manage Business Central Synchronization with Microsoft Fabric
description: Select Business Central companies and tables, use configuration packages, and control ongoing synchronization with Microsoft Fabric.
author: jswymer
ms.topic: how-to
ms.search.keywords: Fabric, data mirroring, replication, synchronization, configuration package, companies, tables
ms.search.form: Primary_48511, 48508, 48512, 48515, 48513
ms.date: 10/29/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Manage Business Central data synchronization with Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

After you [configure data mirroring](admin-set-up-fabric-mirroring.md) from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft Fabric, use the **Microsoft Fabric Mirroring Setup (Preview)** page to choose the data to synchronize and control synchronization.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Assign permissions for data mirroring

Assign permission sets according to each person's responsibilities.

| Permission set name | Display name | Use |
| --- | --- | --- |
| `Fabric Exp Admin` | **MS Fabric Mirroring - Admin** | Set up the connection, select companies and tables, manage configuration packages, control synchronization, and view monitoring information. |
| `Fabric Exp Activate` | **MS Fabric Mirroring - Activate** | Activate, deactivate, and reapply existing configuration packages. |
| `Fabric Exp Read` | **MS Fabric Mirroring - Read** | View synchronization overview and detail information without setup or synchronization actions. |

These permission sets control access in Business Central. Grant access to the Fabric workspace separately, as described in [Set up authentication](admin-set-up-fabric-mirroring.md#set-up-authentication).

## Select companies

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Configuration** > **Companies**.
1. Select **Add company**, and then select a company.
1. Repeat the previous step for each company to synchronize.

Newly added companies are enabled. Clear the **Enabled** field to temporarily skip a company without removing its configuration. At least one company must be enabled before you start synchronization.

For each enabled company, synchronize tables that store data per company. Synchronize tables that don't store data per company once.

## Select tables

You can select up to 1,000 tables for synchronization.

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Configuration** > **Tables**.
1. Select **Add table**.
1. Select one or more Business Central tables.

Business Central assigns a Fabric entity name and identifies whether each table stores data per company. Use the **Fabric Schema Type** field to choose whether the table belongs to the data or logging schema.

The lookup lists normal tables that are eligible for export. External, linked, and virtual tables aren't supported. Certain internal tables that contain sensitive data are also excluded. The same validation applies when a table is added through a package or API.

A table is selected when it appears on the tables page; there isn't a separate enabled switch for each table. Select at least one table before you start synchronization.

The 1,000-table limit applies to the combined selection from manual additions and active configuration packages. A table selected through more than one package counts once.

## Use configuration packages

Configuration packages let you add a curated set of tables instead of selecting tables individually. The app includes the **MS-STD** package, named **Microsoft Standard**. Its definition lists 256 standard table IDs for analytics scenarios. The available package entries depend on the tables installed in your environment.

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Configuration** > **Import/Export Configuration**.
1. Select a package, and then use one of the following actions:

   - **Activate**: Adds the package's tables to the synchronization list.
   - **Deactivate**: Removes the package's table selections. A table remains selected if you selected it manually or if it's included in another active package.
   - **Reapply**: Adds changes from a newer package version. Reapply doesn't remove stale selections. Deactivate and activate the package to fully align the selection with the latest package definition.

Existing table selections keep their current Fabric settings when you activate or reapply a package. A newly selected table takes its schema type from the package.

You can't remove a package-owned table with **Remove table** on the table configuration page. Deactivate the package, or import an updated definition that omits the table. A manual selection or another active package can keep the table selected.

You must deactivate a package before you delete it.

> [!NOTE]
> Activating or reapplying a package can't increase the total selection beyond the 1,000-table limit.

### Import or update a package definition

Use JSON to define the table IDs in a package. Include a distinct integer ID for each table. For example:

```json
{
    "code": "FINANCE",
    "description": "Finance tables",
    "version": "1.0",
    "tables": [15, 17, 18, 21]
}
```

1. Open **Configuration** > **Import/Export Configuration** from the setup page.
1. On **Fabric Configuration Packages**, select **Import/Export** > **Import package**.
1. Select the JSON file.
1. Review the imported package's table list and version.
1. Select **Activate** when you're ready to add its tables to the synchronization selection.

The package code identifies the package. When you import an existing code, change the version in the JSON file to apply a changed definition. An import with the same version as the installed package leaves the package unchanged. Table IDs that don't exist in the environment are skipped.

Importing a changed definition for an active package releases tables removed from that definition and attempts to add its new tables. A manual selection or another active package can keep a removed table selected. Review the selected tables after an update. If additions exceed the table limit, reduce the selection and select **Reapply** to add the missing tables.

Importing an updated definition differs from selecting **Reapply** on an unchanged package. Reapply only adds missing selections; it doesn't remove stale tables.

### Export a package definition

1. Open **Configuration** > **Import/Export Configuration** from the setup page.
1. Select the package to export.
1. Select **Import/Export** > **Export package**.
1. Save the downloaded JSON file.

The JSON file contains the package code, description, version, and table IDs. It doesn't contain connection credentials or per-table Fabric schema settings.

## Configure synchronization behavior

Use the following fields on the **Microsoft Fabric Mirroring Setup (Preview)** page:

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
| **Start synchronization** | Requests continuous export of the selected companies and tables. At least one company must be enabled and one table selected. If a synchronization run is already active, Business Central doesn't start another run. |
| **Stop synchronization** | Cancels an in-progress run and pauses recurring synchronization. The Fabric connection and synchronization state are preserved so that you can resume later. |
| **Reset** | Cancels in-progress work, removes the tenant's mirroring resources, resets all watermarks, and deletes the synchronization summary and detail records. |

Setup, start, stop, and reset requests run asynchronously. Use the monitoring pages to confirm that an operation finished.

You can't change the Fabric workspace or open mirrored database while the **Export Enabled** field is selected. Select **Reset** to clear the connection before you select a different destination.

### Start synchronization for the first time

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Refresh page**, and confirm that **Setup Complete** is selected. If setup isn't complete, follow [Connect the Business Central environment to Fabric](admin-set-up-fabric-mirroring.md#connect-the-business-central-environment-to-fabric).
1. Confirm that at least one company is enabled and at least one table is selected.
1. Select **Start synchronization**.
1. Open **Monitoring** > **Fabric Synchronization Overview** to check the run and its result.

**Export Enabled** is a read-only status, not a switch that you must turn on. It reports whether continuous export is enabled. It doesn't confirm that a particular run succeeded. Learn more in [Understand the setup and export status](admin-set-up-fabric-mirroring.md#understand-the-setup-and-export-status).

### Pause and resume synchronization

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Stop synchronization**.
1. Check **Fabric Synchronization Overview** to confirm that the active run is no longer running.
1. To resume, select **Start synchronization**.

Use **Stop synchronization** for a temporary pause. You don't need to reconnect to Fabric each time you resume.

### Reset the connection

Use **Reset** only when you intend to remove the connection and synchronization state, such as when you need to connect to a different destination.

> [!WARNING]
> Reset removes the Fabric connection, resets synchronization watermarks, and deletes synchronization overview and detail records. It isn't a pause operation. Record any diagnostic information that you need before you reset.

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Reset**, and review the confirmation message.
1. Confirm the reset.
1. Wait for the background reset to finish before you configure a new connection.
1. Follow [Set up data mirroring](admin-set-up-fabric-mirroring.md) to configure the connection again.

## Request a full snapshot for one table

Use **Reset table** when you need the next synchronization run to send a full snapshot for a selected table. This action differs from **Reset** on the setup page.

1. On the setup page, select **Stop synchronization** if a run is active. Check the overview to confirm that the run is no longer running.
1. Open **Configuration** > **Tables**, and select the table.
1. Select **Reset table**, and confirm the request.
1. Return to the setup page, and select **Start synchronization**.
1. Review the next run's details to confirm the snapshot result.

The reset clears the latest successful end watermark for the table in each company with a successful synchronization record. It doesn't remove the connection, clear credentials, or delete all synchronization history. If the table has no completed synchronization, the next run already requires a full snapshot.

Business Central blocks table resets while a synchronization run is active. A full snapshot can take longer than an incremental export. Resetting the watermark doesn't by itself repair an incompatible destination schema.

## Reconnect after environment configuration cleanup

When Business Central clears environment-specific configuration, the app clears the Fabric destination and authentication values and resets **Setup Complete** and **Export Enabled**. The cleanup doesn't disable the original environment's remote Fabric connection.

Company and table selections, package definitions, and synchronization logs remain. Don't assume that copied settings provide a usable connection. Follow [Set up data mirroring](admin-set-up-fabric-mirroring.md) to configure the destination and authentication again.

## Related information

[Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md)  
[Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md)  
[FAQ about mirroring Business Central data to Microsoft Fabric](fabric-faq.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
