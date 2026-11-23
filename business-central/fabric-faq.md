---
title: Business Central Mirroring to Microsoft Fabric FAQ
description: Get answers about availability, setup, supported data, synchronization, capacity, and licensing for mirroring Business Central data to Fabric.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: faq
ms.date: 11/19/2026
ms.custom: bap-template
ai-usage: ai-assisted
---

# FAQ about mirroring Business Central data to Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article answers common questions about mirroring Business Central data to Microsoft Fabric.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## When should I use mirroring instead of API-based extraction?

Use mirroring when API-based report refreshes are slow or throttled, or when you want to combine Business Central data with data from other systems in Fabric. Mirroring makes an initial copy of selected data and then synchronizes changes without requiring you to build and maintain APIs for those tables.

Mirroring is optional. Learn more in [Choose when to use data mirroring](admin-fabric.md#choose-when-to-use-data-mirroring).

## Availability and prerequisites

### Is the feature in private preview, public preview, or generally available?

The feature is in public preview. Review the preview notice in this article and the prerequisites in [Set up data mirroring](admin-set-up-fabric-mirroring.md#prerequisites) before you begin.

### Which version of Business Central is required?

Use Business Central online version 29.1 or later with the Business Central Mirroring to Fabric extension installed. Check the compatibility requirements of the extension version that you install.

Learn more in [Prerequisites for data mirroring](admin-set-up-fabric-mirroring.md#prerequisites).

### Is mirroring available for Business Central on-premises?

No. Mirroring Business Central data to Microsoft Fabric is available for Business Central online only. It's not supported for Business Central on-premises environments.

For an on-premises database, consider [SQL Server mirroring in Microsoft Fabric](/fabric/mirroring/sql-server), subject to its prerequisites and limitations. This alternative mirrors the physical SQL tables, not the shared, multicompany schema provided by the Business Central mirroring extension.

### Can I use mirroring with a Business Central Docker container?

No. Docker-based Business Central environments are on-premises environments and don't support mirroring.

To test mirroring, use a Business Central online sandbox environment. You can copy a production environment to a sandbox in the Business Central admin center.

### Can I test mirroring in a sandbox environment?

Yes. You can configure mirroring from a Business Central online sandbox if the environment meets the requirements for mirroring and you have access to a supported Microsoft Fabric capacity.

## Fabric capacity, licensing, and costs

### Which Fabric capacity is required?

Use a workspace assigned to an active Microsoft Fabric capacity or a supported Fabric trial. A paused or deleted capacity stops Fabric replication. Size the capacity for your analytics workloads and storage needs.

Learn more in [Configure Microsoft Fabric open mirrored databases](/fabric/mirroring/open-mirroring-tutorial#prerequisites).

### What are the licensing and consumption costs?

Business Central doesn't charge an extra fee for mirroring. You need an active Fabric capacity. Fabric doesn't charge for the background compute used for mirroring replication, and that compute doesn't consume capacity units. Mirrored storage has a capacity-based free allowance, and querying through SQL, Power BI, or Spark incurs the usual charges.

Requests that directly access mirrored data in OneLake consume capacity as normal OneLake compute. Storage beyond the free allowance, or while capacity is paused, is charged separately. Review [Cost of mirroring](/fabric/mirroring/overview#cost-of-mirroring) and your licensing terms before you plan capacity.

## Connection setup and access permissions

### Does Business Central appear as a source in the Fabric mirroring experience?

No. First, create an open mirrored database in Fabric. Then, configure Business Central to replicate data to that database.

### Does configuration start in Business Central, Fabric, or both?

Configuration takes place in both products:

1. Create an open mirrored database in Fabric.
1. Create the service principal for the Microsoft-provided **Dynamics 365 Business Central Fabric Export** application, and grant it access to the Fabric workspace.
1. Configure Business Central to use the open mirrored database.
1. Choose the Business Central companies and tables to synchronize.
1. Start synchronization and monitor its results.

Learn more in [Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md).

### Which Business Central permissions do I need?

Use **MS Fabric Mirroring - Admin** to configure and manage mirroring. **MS Fabric Mirroring - Activate** lets users activate, deactivate, and reapply existing configuration packages. **MS Fabric Mirroring - Read** provides read access to synchronization monitoring information.

These permission sets don't grant access to Fabric. Learn more in [Assign permissions for data mirroring](admin-manage-fabric-export.md#assign-permissions-for-data-mirroring).

### Do I need my own app registration and client secret?

No. Business Central uses the Microsoft-provided **Dynamics 365 Business Central Fabric Export** application. Create its service principal in your tenant and grant it access to the destination workspace.

Learn more in [Set up authentication](admin-set-up-fabric-mirroring.md#set-up-authentication).

### When do I need to enter Principal ID?

Enter the enterprise application's Object ID only if you use **Add to workspace** during set up in Business Central. Don't enter its application (client) ID.

If access is already granted in Fabric, you can leave **Principal ID** blank and skip that action.

### What's the difference between Connect to Fabric and Start synchronization?

**Connect to Fabric** requests the background connection setup. Wait until **Setup Complete** is selected before you select **Start synchronization**. At least one company must be enabled and one table selected.

**Finish** only completes the assisted setup guide. It doesn't start synchronization.

## Multiple environments and tenants

### Can multiple Business Central environments mirror data to the same mirrored database?

No. Configure a separate mirrored database for each Business Central environment.

If you want to analyze data from multiple Business Central environments together, combine the data in Microsoft Fabric after you configure mirroring for each environment. For example, use an extract, transform, and load (ETL) process to consolidate the data in a warehouse or lakehouse. Mirroring doesn't require a particular warehouse design, such as a medallion architecture.

### Can I mirror data from Business Central environments in different Microsoft Entra tenants to the same Fabric workspace?

No. The Business Central environment and its destination Fabric workspace must be in the same Microsoft Entra tenant.

To work with data from Business Central environments in different tenants, configure mirroring within each tenant and combine the data afterward.

OneLake external data sharing can provide access across tenants through read-only shortcuts without copying the data again. Fabric administrators must enable external data sharing in both tenants, and the recipient accepts the share into a lakehouse. Review the required permissions and security considerations before sharing. Learn more in [External data sharing in Microsoft Fabric](/fabric/governance/external-data-sharing-overview).

## Data selection and supported fields

### How are environments, companies, and tables configured?

You configure mirroring separately for each Business Central environment. On the **Microsoft Fabric Mirroring Setup (Preview)** page, choose the companies and tables to synchronize.

### Does each company have a separate table in Fabric?

No. For tables that store data per company, the mirrored table combines records from the selected companies. A company column identifies the source company for each row, so you can analyze one company or compare several companies without combining separate company tables.

### Are standard and extension tables supported?

You can select eligible tables from the table lookup, including standard and extension tables that pass the app's export validation. Eligible fields added by extensions are also included. Not every AL table, field, or data type is eligible.

The app filters the lookup before you select tables.

### Can I choose which fields to mirror from a table?

No. The setup pages let you select tables, not a custom list of individual fields.

Field eligibility is part of the app's export validation, so don't assume that every AL field can be mirrored.

### Are FlowFields mirrored to Microsoft Fabric?

No. FlowFields are calculated at runtime in Business Central and aren't stored as ordinary table data. As a result, they aren't included in the mirrored data.

If you need equivalent calculated values in Fabric, recreate the calculations in your Fabric data or reporting layer.

### Are BLOB fields mirrored to Microsoft Fabric?

No. BLOB fields aren't included in the mirrored data.

### Can I filter which records are mirrored?

No. You select the companies and tables to mirror, but you can't apply filters to individual records in a selected table.

The initial synchronization includes all eligible records for the selected companies and tables. Subsequent synchronizations replicate changes to those records.

### Can I mirror only data from a specific time period?

No. You can't specify a historical date range for mirroring. When you select a table, the initial synchronization includes all eligible records in that table for the selected companies.

### Are there limits on tables, rows, or data volume?

The app supports up to 1,000 selected tables across manual selections and active configuration packages. Selecting the same table through multiple packages doesn't count it multiple times.

This table-selection limit isn't a guarantee of unlimited rows, data volume, or Fabric resources. Review the [open mirroring guidance](/fabric/mirroring/open-mirroring) and your capacity requirements.

## Synchronization timing and performance

### How does Business Central extract data for mirroring?

The app requests setup and export operations from the Business Central platform. Its configuration and monitoring APIs aren't endpoints for reading each selected business table.

Learn more in [Microsoft Fabric data mirroring](/dynamics365/business-central/dev-itpro/developer/devenv-extract-data#microsoft-fabric-data-mirroring).

### How long does the initial synchronization take?

There's no fixed duration for the initial synchronization. The time depends on factors such as the number and size of the selected tables, the number of selected companies, the amount of data, and the available Business Central and Fabric resources.

Large initial synchronizations can take several hours. Monitor synchronization in Business Central and the replication status in Fabric to follow its progress.

### What is the expected synchronization latency?

**Minutes Between Exports** controls the interval between continuous export runs. The default interval is five minutes. End-to-end latency also includes the export work and Fabric's ingestion of the data. The number of selected tables and companies, and the volume of changes, affect how long synchronization takes.

Use the run timestamps and Fabric replication monitor to measure progress for your environment rather than assuming a fixed completion time.

### Can I configure different synchronization intervals for different tables?

No. **Minutes Between Exports** applies to the mirroring configuration. You can't configure a different synchronization interval for individual tables.

### Are deleted records synchronized?

Yes. Mirroring supports deleted records. In Fabric open mirroring, a matching delete marks the row as deleted. This operation doesn't guarantee immediate physical removal of the underlying files.

Mirroring isn't a replacement for backups. Historical data availability depends on Fabric's retention settings. Learn more in [Retention for mirrored data](/fabric/mirroring/overview#retention-for-mirrored-data).

### Does mirroring affect Business Central performance?

Mirroring is designed to minimize its effect on Business Central workloads. However, the initial synchronization can generate more activity than subsequent incremental synchronizations, especially when you mirror large tables or many companies.

For large initial synchronizations, consider starting mirroring outside peak business hours.

### Does mirroring affect Business Central API limits?

The app doesn't expose the selected business tables through its configuration and monitoring APIs. Requests that your tools make to those APIs are still API calls and remain subject to the applicable Business Central limits.

## Mirrored data and analytics

### Why do table and field names contain underscores in Fabric?

When it generates default names, Business Central replaces each character other than a letter, digit, or underscore with an underscore. Default table names are also converted to lowercase. The setup pages don't provide an option to change this naming convention. If you need different display names, apply them in your reporting model or transformation layer.

### Can I use mirrored data for Power BI, data science, and machine learning?

Yes. The mirrored database provides a SQL analytics endpoint, and the data in OneLake is available to Fabric analytics experiences. You can build Power BI semantic models and reports, use notebooks, and work with Fabric Data Science.

Mirroring copies the data; it doesn't recreate Business Central calculations or reporting models for you. Include any required calculations, such as equivalents of FlowFields, in your analytics solution.

Learn more in [Use mirrored data in Fabric](admin-fabric.md#use-mirrored-data-in-fabric) and [Data science with mirrored data](/fabric/mirroring/overview#data-science-with-your-mirrored-database-data).

### Can I customize the Business Central Power BI apps?

Yes. Where source files are available, you can use the apps' reports and semantic models as a starting point for your own analytics solution. Check each app version's supported data source before you use it with mirrored data. Mirroring doesn't automatically switch an existing API-based app to Fabric.

Learn more in [Get the Power BI app source files](across-powerbi-apps-faq.md#can-i-get-a-copy-of-the-source-code-pbix-files-for-the-apps).

## Managing mirroring and environment changes

### Do I need to reconnect every time I resume synchronization?

No. **Stop synchronization** preserves the connection and synchronization state. Use **Start synchronization** to resume.

**Reset** removes the connection and synchronization state. Don't use **Reset** for a temporary pause.

### How do I stop mirroring and remove the mirrored data?

Use **Stop synchronization** if you want to temporarily stop synchronization while preserving the connection and synchronization state.

If you no longer want to use the connection, use **Reset** to remove the Business Central connection and synchronization state.

If you also want to remove the replicated data, delete the corresponding mirrored database or other Fabric artifacts in Microsoft Fabric. Business Central doesn't automatically delete Fabric artifacts when you stop or reset mirroring.

### Does Reapply remove tables that aren't in a package anymore?

No. **Reapply** adds missing selections from the current package definition.

To remove stale selections, deactivate and activate the package. Importing a definition with a new version can also release removed package tables. Tables remain selected if another package or a manual selection still claims them.

Learn more in [Use configuration packages](admin-manage-fabric-export.md#use-configuration-packages).

### What happens when I copy or restore a Business Central environment?

A copy or point-in-time restore creates a new database. Don't assume that an existing Fabric mirrored database synchronizes with the copied or restored database. Configure mirroring for the new environment before you use it.

Learn more in [Reconnect after environment configuration cleanup](admin-manage-fabric-export.md#reconnect-after-environment-configuration-cleanup).

### What happens to mirroring settings during environment configuration cleanup?

The app clears the Fabric destination and authentication values and resets the setup and export status fields. Company and table selections, package definitions, and logs remain.

Configure a new connection before you use mirroring in the cleaned environment.

Learn more in [Reconnect after environment configuration cleanup](admin-manage-fabric-export.md#reconnect-after-environment-configuration-cleanup).

### Do Business Central upgrades require a new mirror?

Database changes made by an upgrade flow through mirroring, subject to Fabric's schema compatibility rules. Review synchronization results after an upgrade, particularly if it changes the tables or extensions that you mirror.

Learn more in [How are schema changes handled?](#how-are-schema-changes-handled).

### How are schema changes handled?

Review synchronization results after changes to your source tables or extensions.

If you need a new full snapshot, use **Reset table**, as described in [Request a full snapshot for one table](admin-manage-fabric-export.md#request-a-full-snapshot-for-one-table). Investigate schema errors before resetting the entire connection.

Fabric has its own schema compatibility rules. Learn more in [Coordinate source schema changes](/fabric/mirroring/open-mirroring-best-practices#coordinate-source-schema-changes).

In Fabric open mirroring, adding a column is supported. Changing a column's data type stops replication for that table and requires rebuilding and reloading the destination table. Removing a column depends on its nullability and doesn't necessarily remove the destination column. Plan source changes together with any required Fabric schema changes. **Reset table** alone doesn't repair an incompatible destination schema.

### What happens when I remove a field from a mirrored Business Central table?

The corresponding column remains in Fabric, but its values are cleared.

### What happens to the mirrored data if I delete the Business Central environment?

Deleting a Business Central environment doesn't automatically delete its mirrored database or data in Microsoft Fabric.

If you no longer need the mirrored data, remove the corresponding Fabric artifacts separately.

## Monitoring, troubleshooting, and support

### How can I monitor synchronization?

Use **Fabric Synchronization Overview** to review runs and **Fabric Synchronization Details** to investigate company and table results. Use saved views to focus on errors, or analysis mode to explore the log data.

The app also provides read-only monitoring APIs. Synchronization logs can be mirrored to a separate logging schema in Fabric, so you can build monitoring reports there. The default logging schema is `BusinessCentral_log`.

Business Central export results and Fabric ingestion status are separate. Check **Monitor replication** in Fabric to confirm that exported data reached the mirrored tables. Learn more in [Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md).

### Why can't I turn on Export Enabled?

Business Central updates **Export Enabled** as a read-only status. It isn't a configuration switch. Background operations don't necessarily update the displayed value immediately.

Select **Refresh page** and check **Fabric Synchronization Overview** for the operation's result.

Use **Setup Complete** to confirm connection setup, and use the synchronization overview and details to verify exports.

Learn more in [Understand the setup and export status](admin-set-up-fabric-mirroring.md#understand-the-setup-and-export-status).

### How do I troubleshoot "Failed to acquire a Microsoft Fabric API token"?

If Business Central can't acquire a Microsoft Fabric API token, check the authentication and workspace configuration:

1. Verify that the **Dynamics 365 Business Central Fabric Export** enterprise application exists in your Microsoft Entra tenant.
1. Verify that its service principal has the required access to the Fabric workspace.
1. If you used **Add to workspace**, verify that you specified the Object ID of the enterprise application, not its application (client) ID.
1. Verify that the Business Central environment and Fabric workspace belong to the same Microsoft Entra tenant.
1. Check the synchronization details in Business Central for a more specific authorization error.

Learn more in [Set up authentication](admin-set-up-fabric-mirroring.md#set-up-authentication).

### Which support team should I contact if mirroring isn't working?

Where you start depends on where the issue occurs:

- For issues with Business Central configuration, synchronization, or data export, start with Business Central support.
- For issues with the mirrored database, Fabric capacity, or replication within Microsoft Fabric, start with Fabric support.

When troubleshooting, check the synchronization details in Business Central and the replication status in Fabric to help determine where the problem occurs.

## Related information

[Data mirroring to Microsoft Fabric from Business Central](admin-fabric.md)  
[Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md)  
[Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md)  
[Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]