---
title: Set up Business Central data mirroring to Microsoft Fabric
description: Prepare Microsoft Fabric, connect Business Central to an open mirrored database, and select the companies and tables to synchronize.
author: jswymer
ms.topic: how-to
ms.search.keywords: Fabric, OneLake, open mirroring, data mirroring, replication, synchronization
ms.search.form: Primary_48519, 48511
ms.date: 10/08/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Set up data mirroring from Business Central to Microsoft Fabric

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Use the **Connect to Microsoft Fabric** assisted setup guide to connect [!INCLUDE[prod_short](includes/prod_short.md)] online to an open mirrored database in Microsoft Fabric. Choose the Business Central companies and tables to synchronize, and make their data available in OneLake for use with Fabric IQ, Power BI, Data Factory, and other analytics experiences.

<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

> [!IMPORTANT]
> - This feature is planned to become available as a production-ready preview in October 2026. Delivery timing and functionality might change.
> - Production-ready previews are subject to [supplemental terms of use](https://go.microsoft.com/fwlink/?linkid=2189520).

## Prerequisites

Before you begin, make sure the following requirements are met.

### Business Central requirements

- Your Business Central online environment is running 2026 release wave 2, version 29.0 or later.
- The **Microsoft Fabric Mirroring** extension is installed from [Microsoft Marketplace](https://go.microsoft.com/fwlink/?LinkId=2384210).
- Data encryption is enabled. Business Central stores the app's client secret in encrypted isolated storage.
- Your user has the **MS Fabric Mirroring - Admin** permission set or equivalent permissions.

For the current preview, you also need a dedicated app registration in Microsoft Entra ID. During setup, you enter its application (client) ID, client secret, and service-principal object ID, which Business Central labels Principal ID. Refer to [Register an application in Microsoft Entra ID for Business Central data mirroring](#register-an-application-in-microsoft-entra-id-for-business-central-data-mirroring)

### Microsoft Fabric requirements

- You have access to an active Microsoft Fabric capacity.
- You are a **Member** or **Admin** of the Fabric workspace so that you can add the mirroring service principal.
- The Fabric workspace is in the same Microsoft Entra tenant as your Business Central environment.

Learn more in [Create a workspace](/fabric/fundamentals/create-workspaces).

## Register an application in Microsoft Entra ID for Business Central data mirroring

For the preview, create a dedicated app registration in Microsoft Entra ID for Business Central data mirroring. By using a dedicated registration, you limit the permissions and credentials to this integration.

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com).
1. Create the app registration:

   1. Browse to **Microsoft Entra ID** > **App registrations** > **New registration**.
   1. In the **Name** field, enter a meaningful name for the app, such as *BC mirroring to Fabric*.
   1. Set the **Supported account types** field to **Single tenant only** unless you need **Multiple Entra ID tenants**. 
   1. Under **Redirect URI** set **Select a platform** box to **Single-Page application (SPA)**. Set the URL box to the Business Central web client base URL + /OAuthLanding.htm, like `https://businesscentral.dynamics.com/aaaabbbb-0000-cccc-1111-dddd2222eeee/Production/OAuthLanding.htm`.

      If token acquisition fails, the error shows the exact redirect URL that you must register.
   1. Select **Register**.

   The app's **Overview** page is displayed. Copy the **Application (client) ID** for later.

   Learn more in [Register an application in Microsoft Entra ID](/entra/identity-platform/quickstart-register-app) and [How to add a redirect URI to your application](/entra/identity-platform/how-to-add-redirect-uri).

1. Add the Fabric API permission:

   1. Select **API permissions** > **+ Add permission**.
   1. On the **Microsoft APIs** tab, select **Power BI Service** > **Delegated permissions**.
   1. Select the **Workspace.ReadWrite.All** checkbox, and then select **Add permissions**.
   1. Select **Grant admin consent for** your tenant.

   Learn more in [Configure app permissions for a web API](/entra/identity-platform/quickstart-configure-app-access-web-apis).

1. Add a client secret for the registered app.

   1. Select **Certificates & secrets** > **Client secrets** > **New client secret**.
   1. Fill in the description, select an expiration option, and then select **Add**.
   1. Before you leave the **Certificates & secrets** page, copy the secret's value to a temporary location. The value isn't accessible once you leave the page. You enter the secret value in the Business Central assisted setup.

       Learn more in [Add credentials to your web application](/entra/identity-platform/how-to-add-credentials?tabs=client-secret#add-a-credential-to-your-application).

1. Get service principal object ID:

   1. On the **Overview** page, select the link next to **Managed application in local directory**. This action opens the corresponding Enterprise application, which is the service principal for your app registration.
   1. On its **Overview** page, copy the **Object ID**.

## Prepare an open-mirrored database in Microsoft Fabric

Before you configure mirroring in Business Central, prepare the destination in Microsoft Fabric.

1. Sign in to [Microsoft Fabric](https://app.fabric.microsoft.com/).
1. Open the workspace that will contain the Business Central data. If you don't have a workspace, learn more in [Create a workspace](/fabric/fundamentals/create-workspaces).
1. Create a **Mirrored Database** item.
1. Enter a name for the database.
1. For the data source, select **Open Mirroring**.
1. Create the database and wait until Fabric finishes provisioning it.

Learn more in [Open mirroring in Microsoft Fabric](/fabric/mirroring/open-mirroring). For the complete Fabric procedure, see [Tutorial: Configure Microsoft Fabric open mirrored databases](/fabric/mirroring/open-mirroring-tutorial).

## Configure mirroring in Business Central

After Fabric provisions the open-mirrored database, return to Business Central and use the **Connect to Microsoft Fabric** assisted setup guide to select the workspace and database, grant the service principal access, and configure the companies and tables to synchronize.

1. Sign in to [Business Central](https://businesscentral.dynamics.com).
1. [!INCLUDE [open-search](includes/open-search.md)] **Assisted Setup**, and then choose the related link.
1. Select **Connect to Microsoft Fabric**.
1. On the **Workspace API Credentials** step, enter the **Client ID**, **Client Secret**, and **Principal ID**.
1. On the **Fabric Workspace** step, use the lookup to select the destination workspace.
1. On the **Grant Workspace Access** step, select **Add to workspace**.

   Business Central adds the service principal as a Contributor to the selected workspace. You only need to grant this access once for each workspace.

1. On the **Fabric Open Mirroring Database** step, select the database that you created.
1. On the **Synchronization Options** step, enter the interval between synchronization runs.
1. Select **Select companies**, and add each company whose data you want to synchronize.
1. Select **Select tables**, and add the tables to synchronize.
1. Select **Connect to Fabric**.

   Business Central starts the mirroring setup process asynchronously. You can continue with the guide while setup runs.

1. Finish the guide. Start synchronization when you're ready to replicate the selected data to OneLake.

## Verify the mirroring setup

Open the **Microsoft Fabric Mirroring Setup** page, and check the following fields:

- **Fabric Workspace Name**
- **Fabric Open Mirroring Name**
- **Fabric Data Namespace**
- **Fabric Logging Namespace**
- **Setup Complete**
- **Export Enabled**

Select **Test connection** to verify that Business Central can access the Fabric API with the stored credentials.

The default data namespace is `BusinessCentral`. The default logging namespace is `BusinessCentral_log`. You can change the namespaces before the mirroring setup finishes.

## Secure the Fabric connection

Business Central shows a privacy notice before it accesses Microsoft Fabric. An administrator must approve the notice before the connection or synchronization can start.

Treat the client secret as a credential. Don't share it or include it in screenshots, support requests, or exported configuration packages. To replace the secret, enter the new value on the **Microsoft Fabric Mirroring Setup** page.

## Related information

- [Data mirroring to Microsoft Fabric from Business Central](admin-fabric.md)
- [Manage Business Central data synchronization with Fabric](admin-manage-fabric-export.md)
- [Monitor and troubleshoot Fabric synchronization](admin-monitor-fabric-export.md)
- [Open mirroring in Microsoft Fabric](/fabric/mirroring/open-mirroring)

[!INCLUDE[footer-include](includes/footer-banner.md)]
