---
title: Set Up Business Central Data Mirroring to Microsoft Fabric
description: Prepare Microsoft Fabric, connect Business Central to an open mirrored database, and select the companies and tables to synchronize.
author: jswymer
ms.topic: how-to
ms.search.keywords: Fabric, OneLake, open mirroring, data mirroring, replication, synchronization
ms.search.form: Primary_48519, 48511
ms.date: 10/29/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Set up data mirroring from Business Central to Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Connect [!INCLUDE[prod_short](includes/prod_short.md)] online to an open mirrored database in Microsoft Fabric. Use the **Connect to Microsoft Fabric (Preview)** assisted setup guide or the **Microsoft Fabric Mirroring Setup (Preview)** page. Choose the companies and tables to synchronize, and make their data available in OneLake for use with Fabric IQ, Power BI, Data Factory, and other analytics experiences.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Prerequisites

Before you begin, make sure the following requirements are met.

Business Central requirements:

- Your Business Central online environment supports the **Microsoft Fabric Mirroring (Preview)** extension. Check the extension's compatibility requirements for your environment version.
- The **Microsoft Fabric Mirroring** extension is installed on the environment. Download the app from the [Microsoft Marketplace](https://go.microsoft.com/fwlink/?LinkId=2384210). Learn more in [Install extensions (apps) in Business Central](ui-extensions-install-uninstall.md).
- Your user account has the **MS Fabric Mirroring - Admin** permission set or equivalent permissions.

Microsoft Fabric requirements:

- The destination workspace is assigned to an active Microsoft Fabric capacity. A paused or deleted capacity stops Fabric replication.
- You have at least the **Member** role in the Fabric workspace, so that you can add the mirroring service principal and assign it the Contributor role.
- The Fabric workspace is in the same Microsoft Entra tenant as your Business Central environment.

Learn more in [Create a workspace](/fabric/fundamentals/create-workspaces) and [Roles in workspaces](/fabric/fundamentals/roles-workspaces).

## Prepare an open-mirrored database in Microsoft Fabric

Create the open mirrored database to receive your Business Central data.

1. Sign in to [Microsoft Fabric](https://app.fabric.microsoft.com/).
1. Open the workspace that will contain the Business Central data. If you don't have a workspace, learn more in [Create a workspace](/fabric/fundamentals/create-workspaces).
1. Open the **Create** hub, select **Mirrored Database**, and then select **Other** to create an open-mirrored database.
1. Enter a name for the database, and then select **Create**.
1. Wait until Fabric finishes provisioning it.

Learn more in [Open mirroring in Microsoft Fabric](/fabric/mirroring/open-mirroring) and [Tutorial: Configure Microsoft Fabric open mirrored databases](/fabric/mirroring/open-mirroring-tutorial).

## Set up authentication

To authenticate with Microsoft Fabric, Business Central uses the **Dynamics 365 Business Central Fabric Export** application in Microsoft Entra ID. To set up your Business Central tenant to use this app, complete these two tasks:

1. **Create a service principal** for the application in the Microsoft Entra tenant used by the Business Central environment. [Learn more](#create-a-service-principal).  
1. **Give the service principal access** to the Fabric workspace that receives the mirrored data. Grant at least **Contributor** access. Use the **Add to workspace** action during [connection setup in Business Central](#connect-the-business-central-environment-to-fabric), or [grant access directly in Fabric](#grant-workspace-access-directly-in-fabric-optional).

### Understand the Microsoft-provided application

Microsoft owns and manages the app registration for Dynamics 365 Business Central Fabric Export in its own Microsoft Entra ID tenant. The registration defines the application's identity and authentication settings. The *service principal* you create in the Microsoft Entra tenant for Business Central represents that application in your tenant and appears under **Enterprise applications** in the Microsoft Entra admin center.

Use these details during setup:

| Item | Value |
| --- | --- |
| App name | Dynamics 365 Business Central Fabric Export |
| Application (client) ID | `dcc80069-ba40-4ad9-ba8c-60001cea3497` |
| Service principal Object ID | Unique to your Microsoft Entra tenant. Needed only when you use **Add to workspace** in Business Central. |

Learn more in [Application and service principal objects in Microsoft Entra ID](/entra/identity-platform/app-objects-and-service-principals).

### Create a service principal

Use one of the following methods to create the service principal or find it if it already exists. The Cloud Shell, Azure CLI, and Microsoft Graph PowerShell methods reuse the service principal if it already exists. The Graph Explorer method includes a separate request to retrieve an existing service principal. Each method shows the service principal's Object ID, which you need to enter in Business Central only if you grant workspace access from Business Central.

Before you start, ensure that:

- You sign in to the Microsoft Entra tenant connected to Business Central.
- You have at least the **Application Administrator** or **Cloud Application Administrator** role in Microsoft Entra.

#### [Azure Cloud Shell (recommended)](#tab/cloudshell)

With this method, you don't need to install any tools.

1. Sign in to the [Azure portal](https://portal.azure.com) as an admin of the tenant connected to Business Central.
1. Select **Cloud Shell** (the `>_` icon at the top of the portal), and then select **Bash**.
1. Run the following commands:

   ```bash
   APP_ID="dcc80069-ba40-4ad9-ba8c-60001cea3497"
   SP_ID=$(az ad sp list --filter "appId eq '$APP_ID'" --query "[0].id" -o tsv)
   [ -z "$SP_ID" ] && SP_ID=$(az ad sp create --id "$APP_ID" --query id -o tsv)
   echo "Principal ID: $SP_ID"
   ```

1. Copy the value shown after `Principal ID:`.

#### [Azure CLI](#tab/cli)

This option requires that Azure CLI is installed on your computer. Run the following commands in PowerShell, and replace `<TenantIdOrDomain>` with your tenant ID or domain:

```powershell
az login --tenant <TenantIdOrDomain> --allow-no-subscriptions

$appId = 'dcc80069-ba40-4ad9-ba8c-60001cea3497'
$spId = az ad sp list --filter "appId eq '$appId'" --query "[0].id" -o tsv

if (-not $spId) {
    $spId = az ad sp create --id $appId --query id -o tsv
}

"Principal ID: $spId"
```

Copy the value shown after `Principal ID:`.

#### [Microsoft Graph PowerShell](#tab/graphps)

This option requires the Microsoft Graph Applications module is installed on your computer.

1. To install the module if you don't already have it, start Windows PowerShell and then run the following command:

   ```powershell
   Install-Module Microsoft.Graph.Applications -Scope CurrentUser
   ```

1. Run the following commands, replacing `<TenantIdOrDomain>` with your tenant ID or domain:

   ```powershell
   Connect-MgGraph -TenantId <TenantIdOrDomain> -Scopes 'Application.ReadWrite.All'
    
   $appId = 'dcc80069-ba40-4ad9-ba8c-60001cea3497'
   $sp = Get-MgServicePrincipal -Filter "appId eq '$appId'"
    
   if (-not $sp) {
      $sp = New-MgServicePrincipal -AppId $appId
   }
    
   "Principal ID: $($sp.Id)"
   ```

   > [!NOTE]
   > The first time you run `Connect-MgGraph`, you're asked to consent to **Microsoft Graph Command Line Tools**. This prompt is expected.

1. Copy the value shown after `Principal ID:`.

#### [Graph Explorer](#tab/graphexplorer)

Use this option if you want to use only a web browser.

1. Open [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer), and sign in as an admin of the tenant.
1. Select **Modify permissions**, and consent to `Application.ReadWrite.All`.
1. Send the following request:

   ```http
   POST https://graph.microsoft.com/v1.0/servicePrincipals
   ```

   Use this request body:

   ```json
   {
     "appId": "dcc80069-ba40-4ad9-ba8c-60001cea3497"
   }
   ```

1. Copy the `id` value from the response.

If you get an error saying that the service principal already exists, send this request instead:

```http
GET https://graph.microsoft.com/v1.0/servicePrincipals(appId='dcc80069-ba40-4ad9-ba8c-60001cea3497')?$select=id
```

Copy the `id` value from the response.

---

After you create or find the service principal, continue to [Connect the Business Central environment to Fabric](#connect-the-business-central-environment-to-fabric).

### Find the Object ID later

If the service principal already exists, you can find its Object ID in the Microsoft Entra admin center:

1. Go to **Microsoft Entra admin center** > **Enterprise applications**.
1. Clear the **Application type** filter.
1. Search for **Dynamics 365 Business Central Fabric Export** or `dcc80069-ba40-4ad9-ba8c-60001cea3497`.
1. Open the application, and copy its **Object ID**.

### Grant workspace access directly in Fabric (optional)

Use this procedure only if you want to grant workspace access in Fabric instead of using **Add to workspace** in Business Central. If the service principal already has **Contributor**, **Member**, or **Admin** access to the workspace, you don't need to grant access again.

To grant workspace access, you must have at least the **Member** role in the workspace:

1. In Microsoft Fabric, open the destination workspace.
1. Select **Manage access**, and then select **Add people or groups**.
1. Find and select **Dynamics 365 Business Central Fabric Export**.
1. Select the **Contributor** role, and then select **Add**.

If you grant access in Fabric, you can leave **Principal ID** blank and skip **Add to workspace** in Business Central.

Learn more in [Give users access to workspaces](/fabric/fundamentals/give-access-workspaces).

> [!NOTE]
> If **Add to workspace** in Business Central isn't available or doesn't succeed, use this procedure to grant access directly in Fabric.

## Connect the Business Central environment to Fabric

After you prepare the Microsoft-provided application's service principal and open mirrored database, configure the connection in Business Central. Use either the assisted setup guide or the setup page. Both methods use the following fields.

| Field | What to enter or select |
| --- | --- |
| **Principal ID** | Enter the service principal's Object ID from [Set up authentication](#set-up-authentication) only if you'll use **Add to workspace** in Business Central. If workspace access is already granted, leave the field blank. |
| **Fabric Workspace Name** | Use the lookup to select the destination workspace. Business Central saves its ID automatically. |
| **Fabric Open Mirroring Name** | Use the lookup to select the database that you prepared in the workspace. Business Central saves its ID automatically. |

### Connect with the assisted setup guide

1. Sign in to [Business Central](https://businesscentral.dynamics.com).
1. [!INCLUDE [open-search](includes/open-search.md)], enter **Assisted Setup**, and then select the related link.
1. Select **Connect to Microsoft Fabric (Preview)**, and then select **Next** on the welcome step.
1. On the **Authentication** step, enter the service principal's Object ID in **Principal ID** only if you'll use **Add to workspace**. If workspace access is already granted, leave the field blank. Select **Next**.
1. On the **Fabric Workspace** step, use the lookup to select the destination workspace. Select **Next**.
1. On the **Grant Workspace Access** step, select **Add to workspace** unless the service principal already has **Contributor**, **Member**, or **Admin** access. Select **Next**.
1. On the **Fabric Open Mirroring Database** step, use the lookup to select the database that you prepared. Select **Next**.
1. On the **Synchronization Options** step, select **Connect to Fabric** to start the background connection setup. Approve the privacy notice if prompted. Select **Next**.
1. Choose **Select companies**, and add at least one company to synchronize. Ensure the company is enabled. Return to the guide, and select **Next**.
1. Choose **Select tables**, and add at least one table to synchronize. Return to the guide, and select **Next**.
1. Select **Finish** to close the guide.

**Finish** doesn't start synchronization. Continue to [Confirm setup and start synchronization](#confirm-setup-and-start-synchronization).

### Connect from the setup page

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Microsoft Fabric Mirroring Setup (Preview)**, and then select the related link.
1. Enter the service principal's Object ID in **Principal ID** only if you'll use **Add to workspace**. If workspace access is already granted, leave the field blank.

   > [!IMPORTANT]
   > Enter the service principal's **Object ID**, not the application (client) ID. Fabric rejects the application (client) ID. You get the Object ID when you create the service principal. If workspace access is already granted, leave this field blank.
1. Use the lookup in **Fabric Workspace Name** to select the destination workspace.
1. Select **Add to workspace** unless the service principal already has Contributor, Member, or Admin access.
1. Use the lookup in **Fabric Open Mirroring Name** to select the database that you prepared.
1. Select **Connect to Fabric** to start the background connection setup. Approve the privacy notice if prompted.
1. Select **Configuration** > **Companies**, and add at least one company to synchronize. Ensure the company is enabled.
1. Return to the setup page. Select **Configuration** > **Tables**, and add at least one table to synchronize.

Continue to [Confirm setup and start synchronization](#confirm-setup-and-start-synchronization).

## Confirm setup and start synchronization

**Connect to Fabric** prepares Business Central to export data to the selected destination. The connection setup runs in the background. You can select companies and tables while setup is in progress.

1. Open the **Microsoft Fabric Mirroring Setup (Preview)** page.
1. Select **Refresh page** to check the latest status. Wait until **Setup Complete** is selected. If setup doesn't complete, check **Fabric Synchronization Overview** for progress and errors.
1. Select **Start synchronization** to request continuous exports of the selected companies and tables.
1. Open **Fabric Synchronization Overview** to check the first export run and its result.

> [!NOTE]
> If you skipped **Connect to Fabric** in the guide, select it on the setup page and wait for setup to complete before you start synchronization.

### Understand the setup and export status

Although **Export Enabled** looks like a switch, it's a read-only status. You don't turn it on manually or enter a value during setup. Business Central updates the status as background export operations run.

| Field | What it tells you |
| --- | --- |
| **Setup Complete** | Whether the background connection setup completed successfully. Use this field to confirm that the connection is ready before you start synchronization. |
| **Export Enabled** | Whether continuous export is enabled. This status doesn't confirm that connection setup succeeded or that a particular export run completed. |

Connection setup and synchronization requests run asynchronously. A status might not change immediately after you select an action. Select **Refresh page** to read the latest values. Use **Fabric Synchronization Overview** to confirm the progress and result of each operation.

Learn more in [Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md).

## Modify the mirroring setup

Use the **Microsoft Fabric Mirroring Setup (Preview)** page to review the connection and change synchronization options. Use the field tooltips for descriptions of optional settings, such as **Minutes Between Exports**.

The default data namespace is `BusinessCentral`. The default logging namespace is `BusinessCentral_log`. You can change the namespaces only before the connection setup completes.

Select **Test connection** to check whether Business Central can access the Fabric API. This action doesn't replace checking **Setup Complete** or verifying an export run.

Learn more in [Configure synchronization behavior](admin-manage-fabric-export.md#configure-synchronization-behavior).

## Secure the Fabric connection

Business Central shows a privacy notice before it accesses Microsoft Fabric. An administrator must approve the notice before the connection or synchronization can start.

## Related information

[Data mirroring to Microsoft Fabric from Business Central](admin-fabric.md)  
[Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md)  
[Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md)  
[Open mirroring in Microsoft Fabric](/fabric/mirroring/open-mirroring)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
