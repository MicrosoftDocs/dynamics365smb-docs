---
title: Install and Uninstall Apps
description: Learn how you can install and uninstall apps and extensions in Business Central.
author: SusanneWindfeldPedersen

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize, install, uninstall
ms.search.form: 2500, 20350
ms.date: 09/22/2022
ms.author: solsen
---

# Install and Uninstall Extensions (Apps) in Business Central

You can change [!INCLUDE[prod_short](includes/prod_short.md)] by installing apps that, for example, add functionality, change behavior, or give you access to new online services. For more information, see [Customizing Business Central Using Extensions](ui-extensions.md).

> [!NOTE]
> To install or uninstall apps from AppSource or add per-tenant apps, you must have the right permissions. You must either be a member of the EXTEND. MGT. - ADMIN user group or you must have the EXTEND. MGT. - ADMIN permission set. If you are an administrator, you can assign user groups and permissions to other users in your company.
>
> To use the functionality that is provided by an extension, such as opening pages, running reports, selecting actions, and so on, you must be assigned the permission sets that are installed as part of the extension.

To use the functionality that is provided by an extension, such as opening pages, running reports, selecting actions, and so on, you must be assigned the permission sets that are installed as part of the extension.

## <a name="install"></a>Install an Extension

You manage apps and extensions on the **Extension Management** page. You can access this page from Home. Alternatively, choose the **Search for Page or Report** icon ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") in the top right corner, enter **Extension**, and then choose the related link.  

You can get new apps from the marketplace at [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646). The marketplace offers all available apps for [!INCLUDE[prod_short](includes/prod_short.md)], plus apps and content packs for other Microsoft products. Set the relevant filters, take a look at the information for each extension, and get an extension for your [!INCLUDE[prod_short](includes/prod_short.md)].  

> [!NOTE]  
> Sign in to [AppSource.microsoft.com](https://appsource.microsoft.com/) using the email account that you use for [!INCLUDE[prod_short](includes/prod_short.md)]. Use the same email account for other services and products for a smooth experience.  

You can also get to AppSource from [!INCLUDE[prod_short](includes/prod_short.md)]. On the **Extension Management** page, you can see the apps that are currently installed, and you can open the **Extension Marketplace** page that shows the [!INCLUDE[prod_short](includes/prod_short.md)] apps that are currently available in AppSource. If you choose the *More apps* link, you're taken to [AppSource.microsoft.com](https://go.microsoft.com/fwlink/?linkid=2081646).  

If you choose an app, you can read about what the app does, and you can access Help for the app to learn more. When you choose to get an app, you must agree to the terms of use. If you get the app from the AppSource website, you'll be signed in to [!INCLUDE[prod_short](includes/prod_short.md)] to complete the installation.  

After you install an app, you might have to set it up. Some apps require that you provide some information before you can use them. For example, after you install the **PayPal Payments Standard** app, you must specify the email or the Merchant account ID for your PayPal account. To set up an app, or to find out what information you'll need, on the **Installed Extensions** page, choose the **Set up** action.  

Other apps simply add fields to an existing page, or they add a new page, for example.

If you uninstall an app, and you then change your mind, you can install it again. When you uninstall an app that you have been using, the data is preserved so that if you install the app again, your data is still available. There are some apps that are required. You're prevented from uninstalling these apps from the **Extension Management** page. If you try, an error message appears.

Some apps are provided by Microsoft, and other apps are provided by [other companies](ui-extensions-other.md). All apps are tested before they're made available to you, but we recommend that you access the links that are provided with each app to learn more about the app before you choose to install it.

Microsoft provides the following apps:

* [AMC Banking 365 Fundamentals Extension](ui-extensions-amc-banking.md)
* [Ceridian Payroll](ui-extensions-ceridian-payroll.md)
* [Company Hub](ui-extensions-company-hub.md)  
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
* [VAT Group](ui-extensions-vat-group.md)
* [WorldPay Payments Standard](ui-extensions-worldpay-payments-standard.md)
* [DK - C5 Data Migration](ui-extensions-c5-data-migration.md)
* [DK - Payments and Reconciliations](ui-extensions-payments-reconciliation-formats-dk.md)
* [DK - Tax File Formats](ui-extensions-tax-file-formats-dk.md)
* [The GetAddress.io UK Postcodes Extension](LocalFunctionality/UnitedKingdom/ui-extensions-getaddressio.md)  
* [US/CA/UK/AU/NZ/ZA - Send Remittance Advice](ui-extensions-send-remittance-advice.md)

## Set Up an Extension
After you install an app, you might have to set it up. For example, for the **PayPal Payments Standard for [!INCLUDE[prod_short](includes/prod_short.md)]** app you must specify the PayPal account to use. If that's the case, when installation completes [!INCLUDE[prod_short](includes/prod_short.md)] will ask whether you want to set up the app right away. Setups can be required for the app to work, or optional. 

If you choose to set up your app right away, and it how a required setup, [!INCLUDE[prod_short](includes/prod_short.md)] will open the required setup. The setup can be either a page where you enter information, or an assisted setup guide that helps you through the steps. If you don't complete the setup in one go, you can use the **Setups for _name of app_** page, which lists all setups for the app. Required setups indicated by **bold letters**.     

## Upload a Per-Tenant Extension (PTE)

You upload a PTE by using the **Extension Management** page. On the **Extension Management** page, go to **Manage**, then choose **Upload Extension**. On the **Upload and Deploy Extension** page, specify the .app file to upload. To proceed, choose the **Accept** button, and then the **Deploy** button, which will start the process of deploying the PTE.

If the PTE contains breaking schema changes, it's possible to *force* an upload of it. To do that, in the **Schema Sync Mode** choose the **Force** option. You'll get a confirmation dialog to accept before proceeding.  

## Uninstall an App

You uninstall an app by using the **Extension Management** page. To uninstall an app, select it on the page, then select the **Uninstall** action. If you uninstall an app, and you then change your mind, you can install the app again.

When you uninstall an app that you've been using, data is by default preserved in case you install the app again. You can instead choose to delete the data with the app. This operation is controlled by the **Delete Extension Data** switch. By default, this switch is **off**. When you try to turn on the **Delete Extension Data** switch for the app, you'll get a confirmation dialog, and you must choose **Yes** to turn it on. After the **Delete Extension Data** switch is turned on, you can uninstall the app, and you'll be asked to reconfirm that you want to uninstall the app and delete the data.

> [!IMPORTANT]  
> - There may be other apps that require or depend on the app that you want to uninstall in order to work. These other apps are referred to as *dependents*. You can't uninstall an app unless its dependents are also uninstalled.
> - When you choose to uninstall an app that has one or more dependents, you'll get a confirmation dialog that lists the dependents and asks whether you want to uninstall the app and all its dependents. You'll have to select **Yes** to continue.
> - If you turn on the **Delete Extension Data** switch, uninstalling the app will delete all data for the app **plus** data for all dependent apps. The action cannot be undone.
> - Some apps are required. You are prevented from uninstalling these from the **Extension Management** page. If you try, an error message appears.  

## See Also

[Customize Business Central](ui-customizing-overview.md)  
[Business Central Extensions by Other Providers](ui-extensions-other.md)  
[Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md)  
[Enable Customer Payment Through PayPal](sales-how-enable-payment-service-extensions.md)  
[Migrating Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up the GetAddress.io UK Postal Code extension](LocalFunctionality/UnitedKingdom/uk-setup-postal-code-service.md)  
[[!INCLUDE[prod_short](includes/prod_short.md)] Extensions by Other Providers](ui-extensions-other.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]