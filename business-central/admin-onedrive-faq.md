---
title: OneDrive in Business Central FAQ
description: Get answers for some typical questions about working with OneDrive for work or school (formerly known as OneDrive for Business) and Business Central.
author: jswymer
ms.topic: faq
ms.devlang: al
ms.search.keywords: OneDrive, integration, share, browser
ms.date: 11/09/2026
ai-usage: ai-assisted
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# OneDrive in Business Central FAQ

This article answers common questions about using OneDrive for Business with [!INCLUDE [prod_short](includes/prod_short.md)].

## Does this work with all Business Central clients?

Yes. You can open files in OneDrive from the [!INCLUDE[prod_short](includes/prod_short.md)] mobile apps, when viewing card details in Microsoft Teams, or even from the Outlook add-in.  

## Is OneDrive the same as SharePoint for storing files?

No. OneDrive is private by default, allowing you to organize and share content, while SharePoint offers a shared file repository for your organization. Additionally, OneDrive is included in your Microsoft 365 subscription.

## Does Business Central support consumer OneDrive?

No. This integration is exclusively intended for OneDrive for Business and only supports your work account. 

## Are all OneDrive for Business plans supported?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't support standalone OneDrive for Business plans. OneDrive must be part of a Microsoft 365 business or enterprise plan. Learn more at [Compare OneDrive plans](https://www.microsoft.com/microsoft-365/onedrive/compare-onedrive-plans?market=af&activetab=tab:primaryr2).

## Where can I see OneDrive service health?

Administrators can access the Service health dashboard in the Microsoft 365 admin center. The dashboard includes OneDrive's service availability. Visit the [Service health dashboard](https://admin.microsoft.com/Adminportal/Home?#/servicehealth).

## Is OneDrive integration available to Business Central on-premises?

Yes, but unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, it does require more setup. Learn more in [Configuring Business Central on-premises](admin-onedrive-integration-onpremises.md).  

## Does Business Central on-premises connect with SharePoint Server?

No. This deployment combination isn't supported, even if SharePoint Server is enabled with My Sites.  

## Does Business Central online connect with SharePoint Server?

No. This deployment combination isn't supported, even if SharePoint Server is enabled with My Sites.  

## How does this work in an organization with multiple environments?

The integration uses the company's display name for its folder in OneDrive, or the company name if no display name is set. Characters that aren't valid in folder names are removed. If the resulting folder names are identical across environments, files from those companies can be placed together in the same folder.

## We changed the company name. What happens to my previous files?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't automatically migrate files you opened earlier in OneDrive to a new folder. If you change the display name used for the company folder, the **Open in OneDrive** action copies files to a folder based on that new display name. Changing only the company name doesn't change the folder if the display name stays the same.

## When I want to attach a file in Business Central, how do I pick a file from OneDrive?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't provide a cloud file picker. You must download the file from OneDrive to your device, and then upload it to [!INCLUDE[prod_short](includes/prod_short.md)]. 

## I want to open files in SharePoint instead. How do I do this?

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't provide features to copy files to SharePoint and open them from a SharePoint library. Contact your Microsoft partner to understand your options, or search for apps on Marketplace.  

## How do I turn off integration to OneDrive?

Run the **OneDrive Setup** assisted setup guide and turn off the **Use with app features** and **Use with system features** switches.

## Should I use the SharePoint Connection Setup page to connect to SharePoint?

> **APPLIES TO:** Business Central on-premises, version 21 and 22

This page is a legacy feature where all [!INCLUDE[prod_short](includes/prod_short.md)] files from all users are sent to a single SharePoint folder. We recommend that you don't configure the Shared Documents FastTab on the **SharePoint Connection Setup** page because this page is [deprecated](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#microsoft-sharepoint-connection-setup) and removed in 2023 release wave 2, version 23.0. We recommend that you use the **OneDrive Setup** instead.  

## Which version of Business Central supports OneDrive?

Integration with OneDrive became available in 2021 release wave 2.  

## <a name="features"></a>Which features are affected by OneDrive integration?

In the **OneDrive Setup** assisted setup guide for setting up OneDrive integration, you can turn on or off features for handling Business Central files in OneDrive. The features are divided between two options:

|Option|Description|
|------|----------|
|**Use with app features**|If you turn on this option, the **Open in OneDrive** and **Share** actions are made available on files in Business Central, like files attached to documents or in the report inbox. These actions let users copy, open, and share files in OneDrive. Learn more in [Opening and Sharing Business Central Files in OneDrive](across-share-onedrive.md).|
|**Use with system features**|Turning on this option activates the following features:<ul><li> The **Open in Excel** and **Edit in Excel** actions on list pages automatically copy the Excel file to OneDrive, then open it in Excel Online. Learn more in [Viewing and Editing in Excel](across-work-with-excel.md).</li><li> Sending a report to an Excel or Word file automatically copies the file to OneDrive, then opens it in Excel or Word online. Learn more in [Saving a report to a file](ui-work-report.md#save-a-report-to-a-file).</li></ul>|

## Will Microsoft continue to improve the integration to OneDrive?

At Microsoft, we're constantly listening to feedback from our diverse user community and acting upon the top suggestions. To learn about what's next for integrations with Microsoft 365 apps, see the [Dynamics 365 release plans](/dynamics365/release-plans/).

If you want to participate in improving OneDrive integration, or have an idea that would improve file sharing and collaboration in [!INCLUDE[prod_short](includes/prod_short.md)], add an idea or vote for existing ideas at [https://aka.ms/BusinessCentralIdeas](https://aka.ms/BusinessCentralIdeas).

## Does OneDrive work for guest users and delegated admins?

OneDrive features don't work when you're signed in to Business Central as a guest user. For example, if you select **Open in OneDrive** or **Share** on a file, you get the message "Could not connect to your OneDrive for Business."

If you're signed in as a delegated admin, files are downloaded instead of connecting to OneDrive.

These limitations apply to all OneDrive-based features in Business Central, including file sharing, opening, or editing.

## Troubleshoot OneDrive integration

This section provides information about how to identify and fix problems you might experience when using OneDrive with [!INCLUDE[prod_short](includes/prod_short.md)].  

### Business Central can't find my OneDrive

When this message displays, "Could not determine the location of your OneDrive for Business, contact your partner to set this up.", check whether the user accessed their OneDrive at least one time. If they haven't, ask the person to visit [https://portal.office.com/onedrive](https://portal.office.com/onedrive) to set it up. This step can take a while. If the message still displays after 24 hours, contact Support.  

### I'm having problems sharing from Outlook

Learn more at [Can't share OneDrive files from Outlook.com](https://support.microsoft.com/en-us/office/can-t-share-onedrive-files-from-outlook-com-05d4cb21-40a2-40e3-b111-82cddb82d22f) on Microsoft Support.

### Actions Open in OneDrive and Share are missing

There are a couple things you can check:

- Check that the application features for OneDrive are turned on in the **OneDrive Setup** assisted setup guide. Learn more in [Configure OneDrive using OneDrive Setup](admin-onedrive-integration.md#configure-onedrive-using-onedrive-setup).
- Check that the OneDrive privacy notice hasn't been declined on the **Privacy Notices Status** page. A declined notice hides these actions. If the notice hasn't been agreed to, users are prompted when they first use a OneDrive feature. Learn more in [Privacy Notices Status](privacy-notices-status.md).

## Related information

[Business Central and OneDrive Integration](across-onedrive-overview.md)  
[Managing OneDrive Integration with Business Central](admin-onedrive-integration.md)  
[Opening Business Central Files in OneDrive](across-share-onedrive.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
