---
title: Managing OneDrive Integration with Business Central
description: Learn about things you can do to manage an integration between Business Central and OneDrive for Business.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: OneDrive, share, browser
ms.date: 02/28/2022
ms.author: jswymer
---
# Managing OneDrive Integration with Business Central

This article provides an overview of what an administrator can do to control OneDrive for Business integration with [!INCLUDE[prod_short](includes/prod_short.md)]. [!INCLUDE[prod_short](includes/prod_short.md)] online customers benefit from automatic integration, with no additional setup required to use these features. 

## Minimum Requirements

* Each user must have a license for [!INCLUDE[prod_short](includes/prod_short.md)] and OneDrive as part of a Microsoft 365 plan.
* OneDrive must be set up for each user.

## Governance

The SharePoint admin center provides extensive control over policies that govern the use of OneDrive throughout the organization. Global Admins, or users who have the SharePoint Admin role, can set up policies that determine who can access OneDrive, where data resides, the content lifecycle, and much more. The following links provide information about often-used features and settings that may enhance your integration with [!INCLUDE[prod_short](includes/prod_short.md)]. 

* [Manage sharing settings](/sharepoint/turn-external-sharing-on-or-off)
* [Use information barriers with SharePoint](/sharepoint/information-barriers)
* [Learn about data loss prevention](/microsoft-365/compliance/dlp-learn-about-dlp)
* [Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)
* [Add and remove admins for a user's OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)
* [Disable OneDrive creation for some users](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users)
* [Multi-Geo Capabilities in OneDrive and SharePoint Online](/microsoft-365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365)

> [!NOTE]
> Some features may be available only for specific plans.

## Managing Privacy

Administrators and end users control the content stored in OneDrive, and this data is owned solely by your organization. For more information, see [How SharePoint and OneDrive safeguard your data in the cloud](/sharepoint/safeguarding-your-data). You can also visit our [Microsoft Privacy Statement](https://privacy.microsoft.com/en-us/privacystatement), which explains the data that Microsoft processes, how Microsoft processes it, and for what purposes.

## Restoring OneDrive and [!INCLUDE[prod_short](includes/prod_short.md)]

As part of a disaster recovery exercise, administrators might need to restore a [!INCLUDE[prod_short](includes/prod_short.md)] environment to a backup from a time in the past, and synchronize OneDrive storage to that same point in time. OneDrive provides various tools for this, such as restoring a user’s OneDrive to a previous time, restore a previous version of an individual file, or restore deleted files. For more information, see the following articles:

* For [!INCLUDE[prod_short](includes/prod_short.md)], see [Restoring an Environment in the Admin Center](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-backup-restore).
* For OneDrive, see [Restore your OneDrive](https://support.microsoft.com/en-us/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15?ui=en-us&rs=en-us&ad=us)

## Configuring Business Central On-Premises

An administrator must set up the connection between [!INCLUDE[prod_short](includes/prod_short.md)] on premises and OneDrive. Unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, the connection isn't automatic. If the connection isn't configured, users can't use the features for OneDrive. 

[!INCLUDE[prod_short](includes/prod_short.md)] on-premises can only be connected to OneDrive hosted by Microsoft in the cloud. Connecting [!INCLUDE[prod_short](includes/prod_short.md)] on premises to the My Sites repository of SharePoint Server isn't supported.

> [!IMPORTANT]
> By configuring this feature, you also enable legacy features that send files to OneDrive.  
>
>* The Open in Excel feature will automatically copy the Excel file to OneDrive, then open it in Excel Online. 
>* Exporting any report to a file will automatically copy the file to OneDrive, then open it in Excel Online, Word Online or OneDrive. 
>* Other features may also automatically open in OneDrive.

### To prepare [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for connecting to OneDrive

<!-- 
1. For the best experience Configure Azure Active Directory (AD) authentication.

   For more information, see [Authenticating Business Central Users with Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-active-directory)-->

Add a registered application for Business Central in your Azure AD tenant of your Microsoft 365 plan. Like other Azure services that work with Business Central, OneDrive requires an app registration in Azure Active Directory (Azure AD). The app registration provides authentication and authorization services between Business Central and SharePoint, which is used by OneDrive.

Configure the registered application with the following delegated permissions to the SharePoint API:

- AllSites.FullControl
- User.ReadWrite.All 

For Business Central 2021 release wave 2 (version 19), set these permissions instead:

- AllSites.Write
- MyFiles.Write
- User.Read.All 

You do this work in the Azure portal. Be sure to copy the Application (client) ID and client secret used by the registered application. You'll need this information in the next task.

For more information about registering an application and configuring permissions, see [Register an application in Azure Active Directory](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory) in the developer and IT pro help.

> [!TIP]
> If you've already registered an application as part of an integration with another Microsoft product, such as Power BI, then you can reuse that app registration. In this case, you'll just have to set the SharePoint permissions.

### To set up the connection in [!INCLUDE[prod_short](includes/prod_short.md)] on-premises

<!--
> [!NOTE]
> This requires the following types of authentication credentials:
>
> * Windows
> * NavUserPassword
> * Azure Active Directory
-->
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Microsoft SharePoint Connection Setup**, and then choose the related link.
2. In the **Description** field, enter a description for the connection, like **OneDrive**.
3. In the **Folder** field, enter **Business Central**.
4. In the **Location** field, enter the URL for your OneDrive.

    The URL for a OneDrive is usually in the following format: `https://<tenant name>-my.sharepoint.com`. For more information, see [OneDrive URLs for users in your organization](/onedrive/list-onedrive-urls) in the OneDrive documentation.
5. In the **Client ID** field, enter the client ID from your application registration.
6. In the **Client Secret** field, enter the secret from your application registration. 
   <!-- 
   For information about how to find the URLs, see the following:
   * [How to find your SharePoint server URL]
   * [How to find your OneDrive URL]-->

> [!IMPORTANT]
> The SharePoint Connection Setup page is used to configure multiple legacy features. The **General** section configures the connection to OneDrive, and the **Shared Documents** section redirects files to SharePoint instead. The legacy SharePoint feature will be deprecated in the near future. We recommend that you do not configure the **Shared Documents** section.

## See Also
[Business Central and OneDrive for Business Integration](across-onedrive-overview.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  
[OneDrive FAQ](admin-onedrive-faq.md)

