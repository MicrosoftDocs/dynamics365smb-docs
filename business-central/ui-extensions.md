---
title: Installing Extensions to Customize Business Central  | Microsoft Docs
description: Learn about adding functionality and customizing Business Central  by installing extensions.
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize
ms.date: 10/01/2020
ms.author: edupont

---
# Customizing Business Central Using Extensions

You can change [!INCLUDE[d365fin](includes/d365fin_md.md)] by installing extensions that add functionality, changes behavior, or gives you access to new online services, for example.

> [!NOTE]
> To install extensions from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the D365 EXTENSION MGMT user group or you must have the D365 EXTENSION MGMT permission set. If you are an administrator, you can assign user groups and permissions to other users in your company.<br /><br />
To use the functionality that is provided by an extension, such as opening pages, running reports, selecting actions, and so on, you must be assigned the permission sets that are installed as part of the extension.

> [!IMPORTANT]  
> The upload of per-tenant extensions and the installation of AppSource extensions is not supported through the **Extension Management** page for on-premise installations.

When you first launch [!INCLUDE[d365fin](includes/d365fin_md.md)], some extensions are already installed for you. Over time, more extensions will be made available to you, and you can then choose if you want to use the extension or not.

For example, Microsoft provides an extension that provides integration with PayPal Payments Standard. This extension is installed by default.
But if another extension is made available that offers integration with another payment service, you can install the new extension and then choose which of the two services to use.  

You manage the extensions on the **Extension Management** page. You can access this page from Home. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link. For more information, see [Installing and Uninstalling Extensions](ui-extensions-install-uninstall.md).

> [!NOTE]  
> If you think you should have access to an extension but you cannot find its functionality, check the **Extension Management** page - if the extension is not listed there, you can install it as described in the following section.  

> [!NOTE]  
> New extensions are not available in AppSource immediately after we announce an update. You can keep an eye out for the extensions at  [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).

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
