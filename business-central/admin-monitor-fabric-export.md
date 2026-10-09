---
title: Monitor and Troubleshoot Microsoft Fabric Synchronization
description: Monitor Business Central synchronization runs, review table-level changes and watermarks, and resolve common Microsoft Fabric connection problems.
author: jswymer
ms.topic: troubleshooting
ms.search.keywords: Fabric, data mirroring, monitoring, replication, troubleshooting, synchronization, watermark
ms.search.form: Primary_48510, 48509
ms.date: 10/08/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Monitor and troubleshoot Business Central synchronization with Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Data mirroring provides an overview of each synchronization run and detailed information for each company and table. You can get the monitoring data from pages in [!INCLUDE[prod_short](includes/prod_short.md)], APIs, or the logging tables in Fabric.

<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

> [!IMPORTANT]
> - This feature is planned to become available as a production-ready preview in October 2026. Delivery timing and functionality might change.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520).

## Monitor synchronization runs

1. Open the **Microsoft Fabric Mirroring Setup** page.
1. Select **Monitoring** > **Fabric Synchronization Overview**.
1. Review the run type, state, start and end times, and error message.
1. Select a run, and then select **Details** to review its table-level results.

Use the **Errors** view to show only runs that contain an error message. Select **Refresh page** to get the latest state for asynchronous operations.

The overview includes setup and synchronization operations. A requested operation might remain in the running state while Business Central and Fabric prepare or synchronize the data.

## Review company and table details

The **Fabric Synchronization Details** page shows:

- The company and Business Central table.
- The destination entity name in Fabric.
- Whether the run was an initial or incremental synchronization.
- The number of inserted, updated, and deleted records.
- The start and end change-tracking watermarks.
- The state and error for the company and table.

By default, the page hides rows where no records changed. Use **Show rows with no changes** when you need to confirm that a table was included in a run. Use the **Errors** view to focus on failures.

## Monitor through APIs or Fabric

The Microsoft Fabric Mirroring app provides APIs for the synchronization overview and details. For more information, see [Microsoft Fabric Export APIs](/dynamics365/business-central/dev-itpro/developer/devenv-fabric-export-apis).

The same operational data is synchronized to the logging namespace in Fabric. The default logging namespace is `BusinessCentral_log`. You can query the logging tables with Fabric tools when you want to combine operational monitoring with other data or build monitoring reports.

## Troubleshoot common problems

| Problem | Resolution |
| --- | --- |
| No workspaces appear in the lookup | Verify the client ID and client secret. Confirm that the signed-in user and Entra application can access the Fabric APIs and the workspace. |
| No open mirrored databases appear | Select a workspace first. Verify that the workspace contains an open mirrored database and that the user can access it. |
| Business Central can't store the client secret | Enable data encryption for the environment, and then enter the secret again. |
| Export requires privacy approval | Approve the **Microsoft Fabric Mirroring - Open Mirroring** privacy notice, and retry the operation. |
| The service principal is already a workspace member | Check its existing workspace role. The **Add to workspace** action expects to add it as a Contributor. |
| Connect to Fabric can't be selected | Check whether the mirroring setup is already complete. Use **Test connection**, or reset the integration if you need to configure a different destination. |
| A second connection request is rejected | Wait for the active setup request to finish. Business Central prevents duplicate enable requests for up to 15 minutes unless the previous setup run has finished. |
| Synchronization doesn't start | Check whether another synchronization run is already running. Stop that run before starting another one. |
| A configuration package can't be activated | Check whether adding its tables would exceed the 1,000-table limit. Remove unneeded tables or deactivate another package. |
| Synchronization stopped after failures | Review the overview and details for errors. Fix the cause, and then select **Start synchronization**. The **Max Consecutive Failed Runs** setting controls when synchronization stops. |

When a Fabric request fails, the detailed error can include an HTTP status code. Use the timestamp, run ID, company, table, and error message when you contact your administrator or Microsoft support.

## Related information

- [Set up data mirroring from Business Central to Microsoft Fabric](admin-set-up-fabric-mirroring.md)
- [Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md)
- [Data mirroring to Microsoft Fabric from Business Central](admin-fabric.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
