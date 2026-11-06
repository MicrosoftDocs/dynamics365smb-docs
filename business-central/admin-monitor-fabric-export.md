---
title: Monitor and Troubleshoot Microsoft Fabric Synchronization
description: Monitor Business Central synchronization runs, review table-level changes and watermarks, and resolve common Microsoft Fabric connection problems.
author: jswymer
ms.topic: troubleshooting
ms.search.keywords: Fabric, data mirroring, monitoring, replication, troubleshooting, synchronization, watermark
ms.search.form: Primary_48510, 48509
ms.date: 10/29/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Monitor and troubleshoot Business Central synchronization with Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Data mirroring provides an overview of each synchronization run and detailed information for each company and table. Review the export results in [!INCLUDE[prod_short](includes/prod_short.md)] or through the app's monitoring APIs. Use Fabric's replication monitor to check the destination.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Monitor synchronization runs

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Monitoring** > **Fabric Synchronization Overview**.
1. Review the run type, state, start and end times, and error message.
1. Select a run, and then select **Details** to review its table-level results.

Use the **Errors** view to show only runs that contain an error message. This view filters on the error message, not the run state. Select **Refresh page** to get the latest state for asynchronous operations.

The overview includes setup and synchronization operations. A requested operation might remain in the running state while Business Central and Fabric prepare or synchronize the data.

**Details** filters the detail page to the selected run ID. Use the same run ID when you compare an overview entry with its company and table results.

### Distinguish setup status from synchronization results

On the setup page, **Setup Complete** confirms that the background connection setup succeeded. **Export Enabled** reports whether continuous export is enabled. Both fields are read-only.

Neither field confirms that a particular company or table finished synchronizing. Check the run state and its details to verify an export. If the displayed status doesn't reflect a recent action, select **Refresh page**.

## Review company and table details

The **Fabric Synchronization Details** page shows:

- The company and Business Central table.
- The destination entity name in Fabric.
- Whether the run was an initial or incremental synchronization.
- The number of inserted, updated, and deleted records.
- The start and end change-tracking watermarks.
- The state and error for the company and table.

By default, the page hides rows where the inserted, updated, and deleted record counts are all zero. Use **Show rows with no changes** when you need to inspect those rows. Use **Hide rows with no changes** to restore the filter.

Use the **Errors** view to focus on rows with an error message. The **Unchanged records** view focuses on rows where all three change counts are zero.

> [!IMPORTANT]
> A row with an error can also have zero change counts. Select **Show rows with no changes** when investigating missing or failed table results so that the default filter doesn't hide those rows.

Watermarks record synchronization progress for a company and table. To request a new full snapshot for a table, use **Reset table** rather than changing watermark values manually. Learn more in [Request a full snapshot for one table](admin-manage-fabric-export.md#request-a-full-snapshot-for-one-table).

## Monitor through APIs or Fabric

The Microsoft Fabric Mirroring app provides monitoring APIs under publisher `microsoft`, group `fabric`, and version `v1.0`:

| Entity set | Use |
|---|---|
| `fabricExportRuns` | Read run IDs, operation types, states, start and end times, and errors. |
| `fabricExportDetails` | Read company and table results, export types, change counts, watermarks, and errors. |

Both monitoring entity sets are read-only. They report synchronization results. They aren't the mechanism for exporting the selected business tables. The detail API doesn't expose the run ID, so use **Details** in the Business Central client when you need table results scoped to a specific run.

In Fabric, open the mirrored database and select **Monitor replication**. Check the database and table replication states, replicated row counts, and last completed times. This view reports Fabric's ingestion of the mirrored data. Learn more in [Monitor mirrored database replication](/fabric/mirroring/monitor).

## Troubleshoot common problems

| Problem | Resolution |
| --- | --- |
| No workspaces appear in the lookup | Confirm that the signed-in user can access the destination workspace and consent to the required Fabric API access. Check that the **Dynamics 365 Business Central Fabric Export** service principal exists in your Microsoft Entra tenant. |
| No open mirrored databases appear | Select a workspace first. Verify that the workspace contains an open mirrored database and that the user can access it. |
| Fabric rejects service principal access | Ask a Fabric administrator to check the tenant setting **Service principals can call Fabric public APIs** and any allowed security-group scope. Also check the service principal's workspace role. Learn more in [Developer admin settings](/fabric/admin/service-admin-portal-developer#service-principals-can-call-fabric-public-apis). |
| Principal ID is missing or workspace access can't be granted | Enter the enterprise application's Object ID, not its application (client) ID. Alternatively, grant access directly in Fabric and skip **Add to workspace** in Business Central. |
| Export requires privacy approval | Approve the **Microsoft Fabric Mirroring - Open Mirroring** privacy notice, and retry the operation. The notice also applies to workspace and database lookups. |
| The service principal is already a workspace member | **Add to workspace** accepts an existing Contributor, Member, or Admin assignment. If it has only Viewer access, ask a workspace administrator to change its role. |
| Connect to Fabric can't be selected | Check whether **Setup Complete** is already selected. You don't need to connect again to resume synchronization. Use **Reset** only if you intend to remove the existing connection and synchronization state. |
| A second connection request is rejected | Wait for the active setup request to finish. Business Central prevents duplicate enable requests for up to 15 minutes unless the previous setup run has finished. |
| Export Enabled is off or can't be changed | The field is read-only. Complete connection setup and use **Start synchronization** to request exports. Refresh the page and check the overview instead of trying to edit the status. |
| The wizard finished, but no data is synchronized | **Finish** only closes the guide. Confirm that **Setup Complete** is selected, at least one company is enabled, and at least one table is selected. Then select **Start synchronization** on the setup page. |
| Synchronization doesn't start | Check that connection setup succeeded and that at least one company is enabled and one table selected. If another synchronization run is active, wait for it to finish or select **Stop synchronization** before requesting a new run. |
| A table can't be removed manually | The table belongs to an active configuration package. Deactivate the package, or import an updated definition that omits the table. Another package or a manual selection can keep the table selected. |
| A table isn't available for export | The app excludes external, linked, virtual, and certain internal sensitive tables. Choose a table offered by the lookup. The same validation applies to packages and APIs. |
| Reset table is blocked | Stop synchronization, wait until the active run is no longer running, and retry **Reset table**. |
| A package import doesn't change its table list | The imported package has the same code and version as the installed definition. Update the version in the JSON file before importing a changed definition. |
| A configuration package can't be activated | Check whether adding its tables would exceed the 1,000-table limit. Remove unneeded tables or deactivate another package. |
| Synchronization stopped after failures | Review the overview and details for errors. Fix the cause, and then select **Start synchronization**. The **Max Consecutive Failed Runs** setting controls when synchronization stops. |
| Business Central reports an export, but the data isn't visible in Fabric | Check the mirrored database's replication monitor and the workspace capacity. A paused or deleted capacity stops Fabric replication. |

When a Fabric request fails, the detailed error can include an HTTP status code. Use the timestamp, run ID, company, table, and error message when you contact your administrator or Microsoft support.

**Test connection** checks access to the Fabric workspace-list API. A successful test doesn't confirm that background setup completed or that data reached the destination. Check the setup status, export results, and Fabric replication separately.

## Related information

[Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md)  
[Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md)  
[Data mirroring to Microsoft Fabric from Business Central](admin-fabric.md)  
[FAQ about mirroring Business Central data to Microsoft Fabric](fabric-faq.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
