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
ms.date: 08/12/2020
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
> If you think you should have access to an extension but you cannot find its functionality, check the **Extension Management** page - if the extension is not listed there, you can install it as described in [Installing and Uninstalling an Extension](ui-extensions-install-uninstall.md).

Some extensions are provided by Microsoft, and other extensions are provided by [other companies](ui-extensions-other.md). All extensions are tested before they are made available to you, but we recommend that you access the links that are provided with each extension to learn more about the extension before you choose to install it.  

Microsoft provides the following extensions:  

* [Accountant Portal for Business Central](ui-extensions-accountant-portal.md)
* [Ceridian Payroll](ui-extensions-ceridian-payroll.md)
* [Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md)
* [Envestnet Yodlee Bank Feeds](ui-extensions-yodlee-bank-feeds.md)
* [Essential Business Insights](ui-extensions-essential-business-insights.md)
* [Image Analyzer](ui-extensions-image-analyzer.md)
* [Intelligent Cloud](ui-extensions-data-replication.md)
* [Intelligent Cloud Base](ui-extensions-intelligent-cloud.md)
* [Late Payment Predictions](ui-extensions-late-payment-prediction.md)
* [Microsoft Pay](ui-extensions-microsoft-pay-payments.md)
* [PayPal Payments Standard](ui-extensions-paypal-payments-standard.md)
* [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)
* [QuickBooks Online Data Migration](ui-extensions-quickbooks-online-data-migration.md)
* [Quickbooks Payroll File Import](ui-extensions-quickbooks-payroll.md)
* [Sales and Inventory Forecast](ui-extensions-sales-forecast.md)
* [WorldPay Payments Standard](ui-extensions-worldpay-payments-standard.md)
* [AMC Banking 365 Fundamentals Extension](ui-extensions-amc-banking.md)
* [DK - C5 Data Migration](ui-extensions-c5-data-migration.md)
* [DK - Payments and Reconciliations](ui-extensions-payments-reconciliation-formats-dk.md)
* [DK - Tax File Formats](ui-extensions-tax-file-formats-dk.md)
* [UK - GetAddress.io UK Postcodes](ui-extensions-getaddressio.md)
* [US/CA/UK/AU/NZ/ZA - Send Remittance Advice](ui-extensions-send-remittance-advice.md)
* [Business Central Extensions by Other Providers](ui-extensions-other.md)

> [!NOTE]  
> New extensions are not available in AppSource immediately after we announce an update. You can keep an eye out for the extensions at [AppSource.microsoft.com](https://appsource.microsoft.com/marketplace/apps?product=dynamics-365%3Bdynamics-365-business-central&page=1).

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
