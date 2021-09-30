---
title: Get Business Central on Your Desktop
description: This article describes how to get the Business Central app on a Windows or MACiOS desktop.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: phone, tablet
ms.date: 10/01/2021
ms.author: jswymer
---
# Get Business Central Desktop App

If you have a Windows (PC) or macOS computer, you can install a Business Central app on your desktop. 
> [!NOTE]
> If you're using Business Central 2021 release wave 1 or earlier, get the app from [Windows Store](https://go.microsoft.com/fwlink/?LinkId=734848).

## Why use the app?

The Business Central app resembles the web client, but it provides a few benefits like:

- The app is readily available from the **Start** menu, you can easily pin it to the task bar, or have it launch by default when you start your computer.
- In general, the app also is a faster and smoother to render on screen, with no performance differences, compared to running [!INCLUDE[prod_short](includes/prod_short.md)] in the browser.
- The app opens in its own window, independent of any browser windows. This feature makes it easier to find when running a large number of apps or browser tabs.
- If you have more than one Business Central environment (or tenants for on-premises), you can install the app separately for each environment or tenant.

     When you open the app for specific environment, the environment name is included in the window title. When working across multiple [!INCLUDE[prod_short](includes/prod_short.md)] environments, each window is displayed separately. The name makes it easier for you to see which window is associated with each environment.

## Install the app

1. Open the [!INCLUDE[prod_short](includes/prod_short.md)] web client in either Microsoft Edge or Google Chrome.

    Safari and Firefox don't support installing the app.

2. If the page for selecting the environment appears, you can do one of two things:

   - Select the environment and go to the next step to install the app. In this case, the installed app will open the environment you select.
   - Don't select the environment, and just go to next step to install the app. In this case, the installed app will open the environment selection page, instead of a specific environment.

3. To install the app, depending on your browser, select ![Icon for installing an app in Edge.](media/ui-edge-install-app-icon.png) **App available. Install Business Central** or ![Icon for installing an app in Chrome.](media/ui-chrome-install-app-icon.png) **Install Business Central**, then **Install**.

   | Microsoft Edge | Google Chrome |
   |--|--|
   | :::image type="content" source="media/ui-edge-install-app-v2.png" alt-text="illustration of a button for installing an app in Edge."::: | :::image type="content" source="media/ui-chrome-install-app-v2.png" alt-text="illustration of a button for installing an app in Chrome."::: |

Once installed, the app appears in the **Start** menu. If you've selected a specific environment for the app, the environment name is added to the app name in **Start** menu.

### For Business Central on-premises

Installing the app when you're using Business Central on-premises is basically the same as described above. The difference is when you have multiple tenants. Unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, where you can choose the environment, with on-premises, you switch tenants by adding `?tenant=tenant_name` to the URL in the browser address. Also, you can only install the app for one tenant. So before you install the app, make sure that you've opened the correct tenant. Once installed, the app will open the tenant directly.
<!--
   > [!NOTE]
   > You can only install the app on a macOS computer if your using Microsoft Edge or Google Chrome.

-->

## See Related Training at [Microsoft Learn](/learn/modules/alternative-interfaces-dynamics-365-business-central/index)

## See Also

[Mobile Apps FAQ](ui-mobile-faq.yml)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]