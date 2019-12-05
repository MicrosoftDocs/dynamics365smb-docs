---
title: FAQ about the Windows Client
description: Learn more about the legacy Dynamics NAV Windows client and why you can no longer use it with Dynamics 365 Business Central
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Frequently asked questions, Windows client
ms.date: 12/05/2019
ms.author: sgroespe

---
# FAQ About the Windows Client and Business Central

The first releases of [!INCLUDE[prodshort](includes/prodshort.md)] on premises included an installed client derived from Dynamics NAV. Starting with 2019 release wave 2, this legacy component, referred to as "the Windows client", will no longer be available for [!INCLUDE[prodshort](includes/prodshort.md)]. Find answers for some of the most common questions here.

## I have heard "modern clients only". What is this about?  
Businesses and users want to be reassured that only the newest, most advanced, and up-to-date tools are being used to access their data. With [!INCLUDE[prodshort](includes/prodshort.md)] 2019 release wave 2, released October 2019, users switch to the **modern experience** in the browser, the Android or iOS mobile apps, or the Windows 10 desktop app, which are available through the respective stores.

Connecting the Windows client to [!INCLUDE[prodshort](includes/prodshort.md)] is **not supported** in [!INCLUDE[prodshort](includes/prodshort.md)] 2019 release wave 2 and onwards.

## Why is Microsoft discontinuing the Windows client?
Our customers must feel comfortable that the tools they use are fit for new hardware, operating systems, and changing environments. We have accelerated our investment in speed and productivity features for the modern browser client, thereby achieving a major milestone in its transformation into a world-class desktop experience for both new and expert users.

Customers can now access [!INCLUDE[prodshort](includes/prodshort.md)] through **a range of modern clients** that support so many productivity features that the Windows client is discontinued from [!INCLUDE[prodshort](includes/prodshort.md)] 2019 release wave 2.  

## Will the Windows client still be supported in older releases of Business Central and Dynamics NAV?
Yes. You can safely continue to use the Windows client on premises and be supported as long as you are covered by the maintenance plan. Please work with you partner to understand the timelines and define the roadmap to move to a newer release at some point.

The Windows client **remains supported** for the Business Central April 2019 release and all earlier releases of [!INCLUDE[prodshort](includes/prodshort.md)] on premises and Dynamics NAV, in accordance with the support lifecycle process.

## When will this take effect?
**In October 2019**, with [!INCLUDE[prodshort](includes/prodshort.md)] 2019 release wave 2, we have now delivered on that promise, especially aimed at partners managing the on-premises upgrade process.

This was first announced last year at various conferences and then with a detailed timeline earlier in 2019. For more information, see [Business Central April 2019 Update and the road ahead](https://community.dynamics.com/business/b/businesscentraldevitpro/posts/business-central-april-2019-release).

## Does this impact me if I use Business Central online?
No. This change **only impacts on-premises** installations because the cloud version of [!INCLUDE[prodshort](includes/prodshort.md)] was already looking forward only and was never enabled to allow connections from the Windows client. For online customers, the modern client continues to be their day-to-day toolset without any change, except for multiple productivity improvements.

For more information, see [Overview of Dynamics 365 Business Central 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-business-central/).

## Does this impact me if I use Business Central on-premises?
Yes. When you **choose to upgrade** to [!INCLUDE[prodshort](includes/prodshort.md)] 2019 release wave 2, you must switch to access [!INCLUDE[prodshort](includes/prodshort.md)] using one of the modern clients. The most popular choice on desktop computers is the web-browser client where your browser is pointing to an on-premises web server using a URL, such as this example (not active): https://myserver.mydomain.com/BC150   

## What if I really want to have an installable component or at least an icon on my desktop?
You can always add a **browser shortcut** on your desktop or pin the web page with [!INCLUDE[prodshort](includes/prodshort.md)] to your Windows task bar. Alternatively, the Business Central **Windows 10 desktop app**, which is available from Microsoft Store, is a great way to access [!INCLUDE[prodshort](includes/prodshort.md)] both on premises and in the cloud. To get the app, go to [Microsoft Dynamics 365 Business Central](https://www.microsoft.com/en-gb/p/microsoft-dynamics-365-business-central/9nblggh4ql79?rtc=1&activetab=pivot:overviewtab) in the store.

## How does this impact mobile?
There is **no impact** on mobile apps for [!INCLUDE[prodshort](includes/prodshort.md)] as they are already part of the modern-client family. For more information about the mobile apps, see [Getting Business Central on Your Mobile Device](install-mobile-app.md).  

## Can I connect to Excel? What happened to the old Excel add-in?
Yes. There are multiple ways to work with [!INCLUDE[prodshort](includes/prodshort.md)] and Excel, including the following:

- The **Open in Excel** feature that downloads any list as an Excel file for your processing or reporting  
- The **Edit in Excel** feature, which is available only in [!INCLUDE[prodshort](includes/prodshort.md)] online, so that you can edit almost any list-based data in Excel and publish it back to [!INCLUDE[prodshort](includes/prodshort.md)]  

For more information, see [Viewing and Editing in Excel From Business Central](across-work-with-excel.md). For instructions on how to configure it for on-premises, see [Setting up the Excel Add-In for Editing Business Central Data](/dynamics365/business-central/dev-itpro/administration/configuring-excel-addin).

Note that the legacy, COM-based Excel plugin that used to be included on the installation media is no longer supported.

## Can we still use the same Outlook add-in?
Yes. This change **does not impact the modern Outlook add-in**. In fact, it enforces its position as one of the modern-client experiences as it is based on the same familiar web experience. It is the only Outlook add-in supported right now for [!INCLUDE[prodshort](includes/prodshort.md)]. For more information, see [Using Business Central as your Business Inbox in Outlook](admin-outlook.md).

## What happened to C/SIDE, the legacy development environment?
In line with the retirement of the Windows client, [!INCLUDE[prodshort](includes/prodshort.md)] 2019 release wave 2 marks a milestone as the first release without the legacy development environment (also known as C/SIDE). The modern developer experience, which is based on Visual Studio Code and the new AL language, supports developing large apps, such as the base application from Microsoft.

Therefore, C/SIDE is discontinued for [!INCLUDE[prodshort](includes/prodshort.md)] going forward. Partners enjoy tremendous productivity and performance gains after moving to thes newest tools. For more information, see [Development in AL](/dynamics365/business-central/dev-itpro/developer/devenv-dev-overview).

## Which features are available in the cloud version, and where will I find more information about the roadmap?
[!INCLUDE[prodshort](includes/prodshort.md)] is a modern business management solution for small and mid-sized organizations that automates and streamlines business processes and helps you manage your business. It is highly adaptable and rich with features already and is being enhanced and enriched on a constant basis.

Note that some features are only available in the cloud version. For more information, see [Features not implemented in on-premises deployments of [!INCLUDE[prodshort](includes/prodshort.md)]](/dynamics365/business-central/dev-itpro/features-not-implemented-on-premises).

The Business Central roadmap is best represented by Release Plans, which are updated every six months. For more linformation, see [Overview of Dynamics 365 Business Central 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-business-central/).

## See Also
[Frequently Asked Questions](across-faq.md)  
[Getting Started](product-get-started.md)  
[Tell Me FAQ](ui-search-faq.md)  
[Searching and Filtering FAQ](ui-search-filter-faq.md)  
[List Views FAQ](ui-views-faq.md)  
[Changing Language and Locale](about-locale-language.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] as Your Business Inbox in Outlook](admin-outlook.md)  
[Using [!INCLUDE[d365fin](includes/d365fin_md.md)] without Outlook](admin-no-outlook.md)  
[Change Basic Settings](ui-change-basic-settings.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Getting answers to questions](product-get-started.md#getting-answers-to-questions)  
[Resources for Help and Support](product-help-and-support.md)  
[Business Central Learning Catalog](readiness/readiness-learning-catalog.md)  
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Country/Regional Availability and Supported Translations](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations?toc=/dynamics365/business-central/toc.json)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
