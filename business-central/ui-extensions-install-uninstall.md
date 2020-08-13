---
title: Installing and Uninstalling Extensions in Business Central  | Microsoft Docs
description: Learn about installing and uninstalling extensions in Business Central.
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize, install, uninstall
ms.date: 07/01/2020
ms.author: solsen
---

# Installing and Uninstalling Extensions in Business Central

You can change [!INCLUDE[d365fin](includes/d365fin_md.md)] by installing extensions that, for example, add functionality, changes behavior, or gives you access to new online services. For more information, see [Customizing Business Central Using Extensions](ui-extensions.md).

> [!NOTE]
> To install extensions from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the D365 EXTENSION MGMT user group or you must have the D365 EXTENSION MGMT permission set. If you are an administrator, you can assign user groups and permissions to other users in your company.<br /><br />
To use the functionality that is provided by an extension, such as opening pages, running reports, selecting actions, and so on, you must be assigned the permission sets that are installed as part of the extension.

## Installing an Extension

You manage extensions on the **Extension Management** page. You can access this page from Home. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link.  

You can get new extensions from the marketplace at [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646). Here, you can see all available extensions for [!INCLUDE[d365fin](includes/d365fin_md.md)], and you can get apps, extensions, and content packs for other Microsoft products. Set the relevant filters, take a look at the information for each extension, and get an extension for your [!INCLUDE[d365fin](includes/d365fin_md.md)].  
> [!NOTE]  
> Sign in to [AppSource.microsoft.com](https://appsource.microsoft.com/) using the email account that you use for [!INCLUDE[d365fin](includes/d365fin_md.md)]. Use the same email account for other services and products for a smooth experience.  

You can also get to the marketplace from inside [!INCLUDE[d365fin](includes/d365fin_md.md)]. On the **Extension Management** page, you can see the extensions that are currently installed, and you can open the **Extension Marketplace** page that shows the [!INCLUDE[d365fin](includes/d365fin_md.md)] extensions that are currently available in AppSource. If you choose the *More apps* link, you are taken to [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).  

If you choose an extension, you can read about what the extension does, and you can access Help for the extension to learn more. When you choose to get an extension, you must agree to the terms of use. If you get the extension from the AppSource website, you will be signed in to [!INCLUDE[d365fin](includes/d365fin_md.md)] to complete the installation.  

When you install an extension, you might have to set it up, such as specifying an account for use with the **PayPal Payments Standard for [!INCLUDE[d365fin](includes/d365fin_md.md)]** extension.
Other extensions simply add fields to an existing page, or they add a new page, for example.

## Uninstalling an Extension

You uninstall an extension using the **Extension Management** page. If you uninstall an extension, and you then change your mind, you can install the extension again. When you uninstall an extension that you have been using, data is by default preserved so that if you install the extension again. You can instead choose to delete the data with the extension. This is controlled by the **Delete Extension Data** checkbox. By default, this checkbox is *not enabled*.

> [!IMPORTANT]  
> If you enable the **Delete Extension Data** checkbox, you will get a confirmation dialog and you must choose **OK**. With the **Delete Extension Data** checkbox enabled, you can now uninstall the extension, and you will be asked to reconfirm that you want to uninstall the extension and delete the data. The action cannot be undone.

Some extensions are required. You are prevented from uninstalling these from the **Extension Management** page. If you try, an error message appears.  


## See Also
[Extending Dynamics 365 Business Central](about-develop-extensions.md)  
[Business Central Extensions by Other Providers](ui-extensions-other.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[Enable Customer Payment Through PayPal](sales-how-enable-payment-service-extensions.md)  
[Migrating Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up the GetAddress.io UK Postal Code extension](LocalFunctionality/UnitedKingdom/uk-setup-postal-code-service.md)  
[[!INCLUDE[d365fin](includes/d365fin_md.md)] Extensions by Other Providers](ui-extensions-other.md)  
[Getting Started](product-get-started.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
