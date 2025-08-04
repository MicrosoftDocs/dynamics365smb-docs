---
title: Configuring OneDrive integration with Business Central on-premises
description: Learn about how to set up Business Central on-premises to integrate with OneDrive for work or school (formerly known as OneDrive for Business).
author: jswymer
ms.topic: how-to
ms.search.keywords: OneDrive, share, browser
ms.date: 09/01/2024
ms.author: jswymer
ms.service: dynamics-365-op
ms.reviewer: jswymer
---
# Configuring OneDrive integration with Business Central on-premises

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

This article explains how to configure OneDrive for work or school (formerly known as OneDrive for Business) integration with Business Central on-premises. Unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, the connection between Business Central and OneDrive isn't set up automatically. If the connection isn't configured, users can't use the features for OneDrive.

There are two tasks that need to be done to configure the OneDrive integration.

- The first task involves registering an application (app) on your Microsoft Entra tenant of your Microsoft 365 plan. The registered app is used for authentication purposes. This task is typically done in the Azure portal and in Business Central web client.
- The second task involves setting up the connection to the OneDrive URL and turning on the OneDrive features in the Business Central. This task in done in the Business Central web client. It's done differently for version 21 than for versions 19 and 20. Version 21 introduces a new **OneDrive Setup** that replaces the **SharePoint Connections Setup**.  

> [!IMPORTANT]
> [!INCLUDE[prod_short](includes/prod_short.md)] on-premises can only be connected to OneDrive hosted by Microsoft in the cloud. Connecting [!INCLUDE[prod_short](includes/prod_short.md)] on premises to the My Sites repository of SharePoint Server isn't supported.

## <a name="registerapp"></a>Register an app in Microsoft Entra ID for OneDrive integration

In this task, you add a registered app for Business Central in the Microsoft Entra tenant of your Microsoft 365 plan. Like other Azure services that work with Business Central, OneDrive requires a registered app in Microsoft Entra ID. The registered app provides authentication and authorization services between Business Central and SharePoint, which is used by OneDrive.

For detailed steps for completing this step, see [Register an application in Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory) in the developer and IT pro help.

As you register the application, consider the following points:

- If you've already registered an application as part of an integration with another Microsoft product, such as Power BI, then you reuse that registered app. In this case, you'll just have to set the SharePoint permissions for the existing registered app.

- Be sure to configure the registered app with the following delegated permissions to the SharePoint API:

    - AllSites.FullControl
    - User.ReadWrite.All
    
    For Business Central 2021 release wave 2 (version 19), set these permissions instead:
    
    - AllSites.Write
    - MyFiles.Write
    - User.Read.All 

- If you're using Business Central version 19 or 20, copy the **Application (client) ID** and **client secret** used by the registered app. You'll need this information in the next task.

## <a name="url"></a>Get your OneDrive URL

[!INCLUDE[onedrive-url](includes/onedrive-url.md)]

## Set up the OneDrive connection in version 21 and later

Use this procedure if you're using Business Central 2022 release wave 2 (version 21) or later.

### Prerequisites

- Indirect, modify, and delete (imd) permission on table **Document Service Scenario** as a minimum

### Run OneDrive setup

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **OneDrive Setup**, and then choose the related link.
2. The first time you run the assisted setup, you see the **Your privacy**. Read the information on the page, and if you agree to the terms choose **Agree** to continue.
3. On the **Configure file handling** page, you have the following options to choose from:

   [!INCLUDE[onedrive-feature-options](includes/onedrive-feature-options.md)]

4. On the **Configure Business Central** page, enter OneDrive's URL in the **OneDrive URL** field.

   [How do I find my OneDrive URL?](#url)
5. Choose **Test Connection** and wait for the results.
   - If the test succeeds, choose **Done**, then you're ready to go.
   - If the test fails, you get a message that describes the problem. Typically the problem has to do with the URL that you provided. Choose **OK** to return to the **Configure Business Central** page, verify the URL, and try again.
   - If you haven't already set up the Microsoft Entra ID registered app, the **Set Up Microsoft Entra ID** guide opens.
6. When completed, the privacy notice for OneDrive integration is agreed for all users. If you want to change it so users must agree or disagree for themselves, then go the **Privacy Notices Status** page and select **Let User Decide** for the OneDrive integration. Users will then be prompted to agree or disagree with the privacy notice the first time they use the OneDrive features. Learn more in [Privacy Notices](privacy-notices-status.md).

## Set up the connection in [!INCLUDE[prod_short](includes/prod_short.md)] version 19 and 20

Use this procedure if you're using Business Central 2022 release wave 1 (version 20) or 2021 release wave 2 (version 19).
> [!IMPORTANT]
> By configuring this feature, you also enable legacy features that send files to OneDrive.  
>
>* The Open in Excel feature will automatically copy the Excel file to OneDrive, then open it in Excel Online. 
>* Exporting any report to a file will automatically copy the file to OneDrive, then open it in Excel Online, Word Online or OneDrive. 
>* Other features may also automatically open in OneDrive.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft SharePoint Connection Setup**, and then choose the related link.
2. In the **Description** field, enter a description for the connection, like **OneDrive**.
3. In the **Folder** field, enter **Business Central**.
4. In the **Location** field, enter the URL for your OneDrive.

   [How do I find my OneDrive URL?](#url)
5. In the **Client ID** field, enter the client ID from your registered app.
6. In the **Client Secret** field, enter the secret from your registered app. 

> [!IMPORTANT]
> The **SharePoint Connection Setup** page is used to configure multiple legacy features. The **General** section configures the connection to OneDrive, and the **Shared Documents** section redirects files to SharePoint instead. The  **SharePoint Connection Setup** has been deprecated and will be removed in coming release. We recommend that you do not configure the **Shared Documents** section. Learn more in [Deprecated Features in the Base App ](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#microsoft-sharepoint-connection-setup).

## After upgrade to version 21

When you upgrade to version 21 or later, the existing connection to OneDrive that's configured on the **SharePoint Connection Setup** page will still work. But because the **SharePoint Connection Setup** page will be removed in version 23, we recommend that you switch to the new OneDrive integration, as described in the next section. Making this switch now make it easier when the **SharePoint Connection Setup** is eventually removed. Plus, it enables you to use the **OneDrive Setup** assisted setup guide to manage the OneDrive features that are accessible to users.

## Switching from legacy SharePoint to new OneDrive integration 

To switch to the new OneDrive integration, you run the **OneDrive Setup** assisted setup guide, which you can open directly or from the legacy **SharePoint Connection Setup** page. The **OneDrive Setup** assisted setup leads you through the transition, providing information about the changes being made along the way.

Before you get started with the switch or as you're doing it, refer to the next section to learn about some aspects and considerations about the process. 

### <a name="onedrivesetupmigration"></a>About switching to the new OneDrive integration

In addition to OneDrive integration, Business Central can also integrate with other services, like Power BI and Universal print. Integration with these other services also requires a registered Microsoft Entra app for authentication. The Microsoft Entra app used by these other services is configured in the **Set up your Microsoft Entra accounts** assisted setup. When you switch from the legacy SharePoint connection setup, the new **OneDrive Setup** assisted setup changes your OneDrive integration to also use the **Set up your Microsoft Entra accounts** assisted setup&mdash;so all integrations use the same Microsoft Entra app.

This change has implications when switching to the new OneDrive integration, depending on whether there's already a Microsoft app configured in the **Set up your Microsoft Entra accounts** assisted setup. 

> [!IMPORTANT]
> After you switch to the new OneDrive setup, you can no longer use the **SharePoint Connection Setup** page to configure OneDrive integration.

#### How the changes affect the integration

The **OneDrive Setup** assisted setup will always use the app that's configured in the **Set up your Microsoft Entra accounts** assisted setup, if there's one. When you run the **OneDrive Setup** assisted setup, it compares the app configured in **Set up your Microsoft Entra accounts** with your current app configured in **SharePoint Connection Setup**.

> [!TIP]
> In the **SharePoint Connection Setup** page and **Set up your Microsoft Entra accounts** assisted setup, the Microsoft Entra app is identified by the **client ID**.

- If the app in **Set up your Microsoft Entra accounts** is different than the app in **SharePoint Connection Setup**, the OneDrive integration changes to use the app in **Set up your Microsoft Entra accounts**.

   In **OneDrive Setup** while making the switch, you get a message similar to the following text: 

   **The Microsoft Entra application used for authentication will be configured for all Business Central integrations. This means the client id will change to NNNNNNNNN-NNNN-NNNN-NNNN-NNNNNNNNNNNN, you may want to test it has the correct permissions.**

  `NNNNNNNNN-NNNN-NNNN-NNNN-NNNNNNNNNNNN` represents the client ID of the app in **Set up your Microsoft Entra accounts** that OneDrive integration has been switched to. 

  > [!IMPORTANT]
  > For new OneDrive integration to work after you make the switch, you have to grant the app permission to the SharePoint API in Azure portal. You can do this step before or after you switch to the new OneDrive setup. Learn more in the section [Register an app in Microsoft Entra ID for OneDrive integration](#registerapp).

- If the app in **Set up your Microsoft Entra accounts** is the same as the app in **SharePoint Connection Setup**, the OneDrive integration uses the same app as before, except from the configuration in the **Set up your Microsoft Entra accounts** setup.

   In **OneDrive Setup** while making the switch, you get a message similar to the following text:

   **The Microsoft Entra application used for authentication will be configured for all Business Central integrations. This has already been configured with the same client id (aaaabbbb-0000-cccc-1111-dddd2222eeee).**

- If there's no app configured in the **Set up your Microsoft Entra accounts** setup, the OneDrive integration uses the same app as before.

   The **OneDrive Setup** assisted setup copies app configuration to the **Set up your Microsoft Entra accounts** setup, so it's used for other integrations in that might set up later.

   In **OneDrive Setup** while making the switch, you get a message similar to the following text:

   **The Microsoft Entra application used for authentication will be configured for all Business Central integrations.**

### Run OneDrive setup to switch to the new OneDrive integration

1. Open either the **OneDrive Setup** page or the **SharePoint Connection Setup** page.
2. If you're using the **SharePoint Connection Setup** page, choose **Go to new OneDrive setup** in the notification at the top of the page.
3. Follow the **OneDrive Setup** assisted setup guide.
4. When you get to the **Configure file handling** page, choose one of the following options for turning on features:

   [!INCLUDE[onedrive-feature-options](includes/onedrive-feature-options.md)]

5. The **Configure Business Central** page shows the same URL that's used by the existing OneDrive integration. You can change the URL as needed.
6. Select **Test Connection** and follow the instructions.

   If the test succeeds, select **done**, and you're ready to go. Otherwise, use the messages on the page to help you fix the problem.

## Related information

[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  
[OneDrive FAQ](admin-onedrive-faq.md)  
