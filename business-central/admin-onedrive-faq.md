---
title: OneDrive for Business FAQ
description: Get answers for some typical questions about working with OneDrive for Business and Business Central.
author: brentholtorf
ms.topic: get-started
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: OneDrive, integration, share, browser
ms.date: 09/09/2022
ms.author: bholtorf
---
# OneDrive for Business FAQ

[!INCLUDE [online_only](includes/online_only.md)]

This article answers some of the questions you may have about working with OneDrive and [!INCLUDE [prod_short](includes/prod_short.md)].

## Does this work with all [!INCLUDE[prod_short](includes/prod_short.md)] clients?

Yes. You can open files in OneDrive from the [!INCLUDE[prod_short](includes/prod_short.md)] mobile apps, when viewing card details in Microsoft Teams, or even from the Outlook add-in.  

## Is OneDrive the same as SharePoint for storing files?

As part of your Microsoft 365 subscription, your organization provides you with OneDrive, your file storage in the cloud. OneDrive is private by default, where you organize your content and choose which files or folders to share and with whom. SharePoint on the other hand, provides a file repository in the cloud that is shared with others in your organization.  

## Does [!INCLUDE[prod_short](includes/prod_short.md)] support consumer OneDrive?

No. This integration is exclusively intended for OneDrive for Business and only supports your work account. 

## Are all OneDrive for Business plans supported?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't support standalone plans for OneDrive for Business. OneDrive must be purchased as part of a Microsoft 365 business or enterprise plan. For more information, see [Compare OneDrive cloud storage pricing and plans](https://www.microsoft.com/microsoft-365/onedrive/compare-onedrive-plans?market=af&activetab=tab:primaryr2).  

## Where can I see OneDrive service health?

Administrators can access the Service health dashboard as part of the Microsoft 365 admin center. The dashboard includes OneDrive’s service availability. Go to [https://admin.microsoft.com/Adminportal/Home?#/servicehealth](https://admin.microsoft.com/Adminportal/Home?#/servicehealth).
 
## Is OneDrive integration available to [!INCLUDE[prod_short](includes/prod_short.md)] on premises?

Yes, but unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, it does require more setup. For more information, see [Configuring Business Central On-Premises](admin-onedrive-integration-onpremises.md).  

## Does [!INCLUDE[prod_short](includes/prod_short.md)] on premises connect with SharePoint Server?

No. This deployment combination isn't supported, even if SharePoint Server has enabled My Sites.  

## Does [!INCLUDE[prod_short](includes/prod_short.md)] online connect with SharePoint Server?

No. This deployment combination isn't supported, even if SharePoint Server has enabled My Sites.  

## How does this work in an organization with multiple environments?

The integration assumes that company names are unique across [!INCLUDE[prod_short](includes/prod_short.md)] environments. When company names are unique across the organization, opening a file in OneDrive will copy the file to a folder named after the current company. If company names aren't unique across environments, files may from identical company names will be placed together in the same folder.  

## We’ve changed company name. What happens to my previous files?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't automatically migrate files you opened earlier in OneDrive to the new folder. After renaming your company, the Open in OneDrive action will copy files to a folder that has the new company name.   

## When attaching files to [!INCLUDE[prod_short](includes/prod_short.md)], how do I pick a file from OneDrive?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't provide a cloud file picker. You must download the file from OneDrive to your device, and then upload it to [!INCLUDE[prod_short](includes/prod_short.md)]. 

## I want to open files in SharePoint instead. How do I do this?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't provide features to copy files to SharePoint and open them from a SharePoint library. Contact your Microsoft partner to understand your options, or search for apps on AppSource.  

## How do I turn off integration to OneDrive?

Run the **OneDrive Setup** assisted setup guide and turn off the **Use OneDrive for app features** and **Use OneDrive for system features** switches. 

## Should I use the SharePoint Connection Setup page to connect to SharePoint?

This is a legacy feature where all [!INCLUDE[prod_short](includes/prod_short.md)] files from all users are sent to a single SharePoint folder. We recommend that you don't configure the Shared Documents FastTab on the **SharePoint Connection Setup** page because this page has been [deprecated](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#microsoft-sharepoint-connection-setup) and will be removed in 2023 release wave 2, version 23.0.  We recommend that you use the **OneDrive Setup** instead.  

## Which version of [!INCLUDE[prod_short](includes/prod_short.md)] supports OneDrive?

Integration with OneDrive became available in 2021 release wave 2.  

## <a name="features"></a>Which features are affected by OneDrive integration?

In the **OneDrive Setup** assisted setup guide for setting up OneDrive integration, you can turn on or off features for handling Business Central files in OneDrive. The features are divided between two options:

|Option|Description|
|------|----------|
|**Use OneDrive for app features**|If you turn on this option, the **Open in OneDrive** and **Share** actions are made available on files in Business Central, like files attached to documents or in the report inbox. These actions let users copy, open, and share files in OneDrive. For more information, see [Opening and Sharing Business Central Files in OneDrive](across-share-onedrive.md).
|**Use OneDrive for system features**|Turning on this option activates the following features:<ul><li> The **Open in Excel** and **Edit in Excel** actions on list pages will automatically copy the Excel file to OneDrive, then open it in Excel Online. For more information, see [Viewing and Editing in Excel](across-work-with-excel.md).</li><li> Sending a report to an Excel or Word file will automatically copy the file to OneDrive, then open it in the Excel or Word online. For more information, see [Saving a report to a file](ui-work-report.md#saving-a-report-to-a-file).|

## Will Microsoft continue to improve the integration to OneDrive?

At Microsoft, we're constantly listening to feedback from our diverse user community and acting upon the top suggestions. To learn about what's next for integrations with Microsoft 365 apps, see the [Dynamics 365 release plan](/dynamics365-release-plan/2021wave1).  

If you want to participate in improving OneDrive integration, or have an idea that would improve file sharing and collaboration in [!INCLUDE[prod_short](includes/prod_short.md)], add an idea or vote for existing ideas at [https://aka.ms/BusinessCentralIdeas](https://aka.ms/BusinessCentralIdeas).

## Troubleshooting

This section provides information about how to identify and fix problems you might experience when using OneDrive with [!INCLUDE[prod_short](includes/prod_short.md)].  

### Business Central can't find my OneDrive

When this message displays, “Could not determine the location of your OneDrive for Business, contact your partner to set this up.”, check whether the user has accessed their OneDrive at least one time. If they haven't, ask the person to go to portal.office.com/onedrive to set it up. That can take a while. If the message still displays after 24 hours, contact Support.  
 
### I'm having problems sharing from Outlook

See [Can't share OneDrive files from Outlook.com](https://support.microsoft.com/en-us/office/can-t-share-onedrive-files-from-outlook-com-05d4cb21-40a2-40e3-b111-82cddb82d22f) on Microsoft Support.

### Actions Open in OneDrive and Share are missing

There ara a couple things you can check:

- Check that the application features for OneDrive are turned on in the **OneDrive Setup** assisted setup guide. See [Configure OneDrive using OneDrive Setup](admin-onedrive-integration.md#configure-onedrive-using-onedrive-setup).
- Check that Microsoft OneDrive is set to **Agree** in the **Privacy Notices Status** page. See [Privacy Notices Status](privacy-notices-status.md).

## See Also

[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  
