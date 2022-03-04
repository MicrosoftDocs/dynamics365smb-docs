---
title: OneDrive for Business FAQ
description: Get answers for some typical questions about working with OneDrive for Business and Business Central.
author: brentholtorf

ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: OneDrive, integration, share, browser
ms.date: 05/19/2021
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

[!INCLUDE[prod_short](includes/prod_short.md)] does not support standalone plans for OneDrive for Business. OneDrive must be purchased as part of a Microsoft 365 business or enterprise plan. For more information, see [Compare OneDrive cloud storage pricing and plans](https://www.microsoft.com/microsoft-365/onedrive/compare-onedrive-plans?market=af&activetab=tab:primaryr2).  

## Where can I see OneDrive service health?

Administrators can access the Service health dashboard as part of the Microsoft 365 admin center. The dashboard includes OneDrive’s service availability. 
 
## Is OneDrive integration available to [!INCLUDE[prod_short](includes/prod_short.md)] on premises?

Yes, but unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, it does require additional setup. For more information, see [Configuring Business Central On-Premises](admin-onedrive-integration.md#configuring-business-central-on-premises).  

## Does [!INCLUDE[prod_short](includes/prod_short.md)] on premises connect with SharePoint Server?

No. This deployment combination is not supported, even if SharePoint Server has enabled My Sites.  

## Does [!INCLUDE[prod_short](includes/prod_short.md)] online connect with SharePoint Server?

No. This deployment combination is not supported, even if SharePoint Server has enabled My Sites.  

## How does this work in an organization with multiple environments?

The integration assumes that company names are unique across [!INCLUDE[prod_short](includes/prod_short.md)] environments. When company names are unique across the organization, opening a file in OneDrive will copy the file to a folder named after the current company. If company names are not unique across environments, files may from identical company names will be placed together in the same folder.  

## We’ve changed company name. What happens to my previous files?

[!INCLUDE[prod_short](includes/prod_short.md)] does not automatically migrate files you opened earlier in OneDrive to the new folder. After renaming your company, the Open in OneDrive action will copy files to a folder that has the new company name.   

## When attaching files to [!INCLUDE[prod_short](includes/prod_short.md)], how do I pick a file from OneDrive? 
[!INCLUDE[prod_short](includes/prod_short.md)] does not provide a cloud file picker. You must download the file from OneDrive to your device, and then upload it to [!INCLUDE[prod_short](includes/prod_short.md)]. 

## I want to open files in SharePoint instead. How do I do this?

[!INCLUDE[prod_short](includes/prod_short.md)] does not provide features to copy files to SharePoint and open them from a SharePoint library. Contact your Microsoft partner to understand your options, or search for apps on AppSource.  

## How do I turn off integration to OneDrive?

[!INCLUDE[prod_short](includes/prod_short.md)] online does not provide a way to enable or disable integration to OneDrive.  

## Should I use the SharePoint Connection Setup page to connect to SharePoint?

This is a legacy feature where all [!INCLUDE[prod_short](includes/prod_short.md)] files from all users are sent to a single SharePoint folder. We recommend that you do not configure the Shared Documents FastTab on the SharePoint Connection Setup page because we are working toward deprecating this feature.  

## Which version of [!INCLUDE[prod_short](includes/prod_short.md)] supports OneDrive?

Integration with OneDrive became available in 2021 release wave 2.  

## Will Microsoft continue to improve the integration to OneDrive?

At Microsoft, we're constantly listening to feedback from our diverse user community and acting upon the top suggestions. To learn about what's next for integrations with Microsoft 365 apps, see the [Dynamics 365 release plan](/dynamics365-release-plan/2021wave1).  

If you want to participate in improving OneDrive integration, or have an idea that would improve file sharing and collaboration in [!INCLUDE[prod_short](includes/prod_short.md)], add an idea or vote for existing ideas at [https://aka.ms/BusinessCentralIdeas](https://aka.ms/BusinessCentralIdeas).

## Troubleshooting

This section provides information about how to identify and fix problems you might experience when using OneDrive with [!INCLUDE[prod_short](includes/prod_short.md)].  

### I have to sign in each time I open a file

Sorry, that's a known issue and we're working on it. We expect to provide a smoother experience in an upcoming update.  

### Business Central can't find my OneDrive

When this message displays, “Could not determine the location of your OneDrive for Business, contact your partner to set this up.”, check whether the user has accessed their OneDrive at least one time. If they haven't, ask the person to go to portal.office.com/onedrive to set it up. That can take a while. If the message still displays after 24 hours, contact Support.  
 

## See Also
[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  
