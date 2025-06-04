---
title: Customizing Business Central online using apps
description: Learn all about adding functionality and customizing Business Central by installing apps in this article.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: solsen
ms.topic: concept-article
ms.search.keywords: app, add-in, manifest, customize
ms.search.form: 2500, 2502, 20350, 20353
ms.date: 03/03/2025
ms.service: dynamics-365-business-central
---

# Customizing Business Central online using apps

You can change [!INCLUDE[prod_short](includes/prod_short.md)] online by installing apps that add functionality, changes behavior, or gives you access to new online services, for example. These apps are also called *extensions* because they *extend* [!INCLUDE [prod_short](includes/prod_short.md)].

## Manage apps

When you first launch [!INCLUDE[prod_short](includes/prod_short.md)], some apps are already installed for you. Over time, more apps will be made available to you, and you can then choose if you want to use the app or not.

For example, Microsoft provides an app that lets you integrate with PayPal Payments Standard. This extension is installed by default. But, an extension that offers integration with another payment service might come along. In that case, you can install the new extension and then choose which to use.  

To use an app, you must have the permissions to the installed objects.

To install or uninstall apps from AppSource or add per-tenant extensions, you must have the right permissions. You must either be a member of the **D365 Extension Mgt.** user group, or you must have the **EXTEN. MGT. - ADMIN** permission set explicitly. If you're an administrator, you can assign user groups and permissions to other users in your company. Learn more in [Create Users According to Licenses](ui-how-users-permissions.md).  

> [!IMPORTANT]  
> For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, you cannot upload per-tenant extensions or install AppSource apps through the **Extension Management** page. You cannot install AppSource apps on-premises, including in Docker-based deployments.

You manage the apps on the **Extension Management** page. You can access this page from Home. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link. Learn more in [Install and Uninstall apps](ui-extensions-install-uninstall.md).

> [!NOTE]  
> If you think you should have access to an app but you cannot find its functionality, check the **Extension Management** page - if the app is not listed there, you can install it as described in the following section.  

> [!NOTE]  
> Sign in to [AppSource.microsoft.com](https://appsource.microsoft.com/) using the email account that you use for [!INCLUDE[prod_short](includes/prod_short.md)] online. Use the same email account for other services and products for a smooth experience.  

You can also get to AppSource from [!INCLUDE[prod_short](includes/prod_short.md)]. On the **Extension Management** page, you can see the apps that are currently installed, and you can open the **Microsoft AppSource Apps** page that shows the [!INCLUDE[prod_short](includes/prod_short.md)] apps that are currently available in AppSource. If you choose the **View AppSource** action, you're taken to [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646). Learn more in [Manage AppSource apps](admin-manage-appsource-apps.md).

If you choose an app, you can read about what the app does, and you can access Help for the app to learn more. When you choose to get an app, you must agree to the terms of use. If you get the app from the AppSource website, sign in to [!INCLUDE[prod_short](includes/prod_short.md)] to complete the installation.  

When you install an app, you might have to set it up, such as specifying an account for use with the **PayPal Payments Standard for [!INCLUDE[prod_short](includes/prod_short.md)]** extension. Other apps add fields to an existing page, or they add a new page, for example.

If you uninstall an app, and you then change your mind, you can install it again. When you uninstall an app, your data is preserved. If you install the app again, it's still available. There are some apps that are required, and you can't uninstall them from the **Extension Management** page.

> [!NOTE]  
> You can keep an eye out for new apps from Microsoft and other suppliers at [AppSource.microsoft.com](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365%3Bdynamics-365-business-central&page=1).

## Understanding the risks of installing apps

[!INCLUDE [ui-extensions-risk-install-apps](includes/ui-extensions-risk-install-apps.md)]

## Apps and data transfer

When apps communicate with other services, they might transfer data out of the geography of the [!INCLUDE[prod_short](includes/prod_short.md)] environment. Examples of such apps include banking, payment, payroll, and forecasting services.

The same is true for the base application, such as the following capabilities:

* Cash Flow Forecast
* Document Exchange Service
* Dataverse connections
* OCR Service
* Online Map
* EU VAT Reg. No. Service

## Connect your business

Starting in 2022 release wave 2, [!INCLUDE [prod_short](includes/prod_short.md)] online environments can list one or more apps on the **Connectivity Apps** and **Banking Apps** pages. These apps can connect your business to external services that increase productivity by automating processes. For example, you can connect to your banks and automatically import bank transactions. The apps are easy to install and set up directly from this page. Choose an app to learn more about capabilities and pricing.  

View the list of suggested apps by choosing the **Connectivity Apps** action in the **Extension Management** page.  

> [!NOTE]
> The first person to open the **Connectivity Apps** page must allow the extension to connect to an external service. Allow the connection once or always. If you choose to block the connection, you must find the relevant apps on AppSource. If you allow the connection once or always, be aware that your information might be shared with third parties. Learn more in the section [Understanding the risks of installing apps](#understanding-the-risks-of-installing-apps).

This external service generates a list of relevant apps based on your country or region

## Recommended apps

Microsoft partners and resellers can create an app that they can use to compile lists of apps that they often recommend to their customers. If they do, and they deployed the app to your tenant, the apps are available on the **Recommended Apps** page. There you can read about each app and decide whether to install them.

> [!NOTE]
> If you are a Microsoft partner or reseller, and you're interested in providing a list of recommended apps, see [Recommend Apps from AppSource](/dynamics365/business-central/dev-itpro/administration/recommend-apps) in the administration content.

## Related information

[Install and Uninstall Apps](ui-extensions-install-uninstall.md)  
[Customize Business Central](ui-customizing-overview.md)  
[Business Central Apps by Other Providers](ui-extensions-other.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md)  
[Migrate Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Set Up the GetAddress.io UK Postal Code extension](LocalFunctionality/UnitedKingdom/uk-setup-postal-code-service.md)  
[[!INCLUDE[prod_short](includes/prod_short.md)] apps by Other Providers](ui-extensions-other.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
