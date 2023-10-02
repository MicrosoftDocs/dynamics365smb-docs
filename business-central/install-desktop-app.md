---
title: Get Business Central on Your Desktop
description: This article describes how to get the Business Central app on a Windows or MACiOS desktop.
author: jswymer

ms.topic: get-started
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: phone, tablet
ms.date: 01/11/2022
ms.author: jswymer
---
# Get Business Central Desktop App

If you have a Windows (PC) or macOS computer, you can install a Business Central app on your desktop. The app works with Business Central online and on-premises.

## Why use the app?

The Business Central app resembles the web client, but it provides a few benefits like:

- The app is readily available from the **Start** menu, you can easily pin it to the task bar, or have it launch by default when you start your computer.
- In general, the app also is a faster and smoother to render on screen, with no performance differences, compared to running [!INCLUDE[prod_short](includes/prod_short.md)] in the browser.
- The app opens in its own window, independent of any browser windows. This feature makes it easier to find when running a large number many apps or browser tabs.
- If there's more than one Business Central environment (online only), you can install the app separately for each environment.

     When you open the app for specific environment, the environment name is included in the window title. When working across multiple [!INCLUDE[prod_short](includes/prod_short.md)] environments, each app window is displayed separately. The name makes it easier for you to see which window is associated with each environment.

## Install the app for Business Central online

There are two ways to install the app for Business Central online. You can install it directly from the browser or from Microsoft Store. Whichever approach you use, it's the same app. The difference is that  installing from the browser lets you install the app for each environment when there's more than one.

### From Microsoft Store

1. Go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=2182870).
2. Choose **Get** > **Install**. 
3. When the app has been installed, choose **Open**, then sign in to Business Central.

The next time you want to open the app, look for it in **Start** menu.

### From the browser

1. Open the [!INCLUDE[prod_short](includes/prod_short.md)] web client in either Microsoft Edge or Google Chrome.

2. If the page for selecting the environment appears, you can do one of two things:

   - Select the environment and go to the next step to install the app. In this case, the installed app will open the environment you select.
   - Don't select the environment, and just go to next step to install the app. In this case, the installed app will open the environment selection page, instead of a specific environment.

3. To install the app, depending on your browser, select ![Icon for installing an app in Edge.](media/ui-edge-install-app-icon.png) **App available. Install Business Central** or ![Icon for installing an app in Chrome.](media/ui-chrome-install-app-icon.png) **Install Business Central**, then **Install**.

   | Microsoft Edge | Google Chrome |
   |--|--|
   | :::image type="content" source="media/ui-edge-install-app-v2.png" alt-text="illustration of a button for installing an app in Edge."::: | :::image type="content" source="media/ui-chrome-install-app-v2.png" alt-text="illustration of a button for installing an app in Chrome."::: |

  > [!TIP]
  > With Edge, you can also install the app by going to the **Settings and more** menu in the browser, then selecting **Apps** > **Install this site as an app** > **Install**.

Once installed, the app appears in the **Start** menu. If you've selected a specific environment for the app, the environment name is added to the app name in the **Start** menu.

## Install the app for Business Central on-premises

Installing the desktop app when you're using Business Central on-premises is done directly from the browser as [described above](#from-the-browser). If you only have one tenant, just open the Business Central in your browser, then select either ![Icon for installing an app in Edge.](media/ui-edge-install-app-icon.png) **App available. Install Business Central** or ![Icon for installing an app in Chrome.](media/ui-chrome-install-app-icon.png) **Install Business Central** as shown above.

The difference is when you have multiple tenants. Unlike [!INCLUDE[prod_short](includes/prod_short.md)] online, where you can install the app for different environments, you can only install the app for one tenant. So before you install the app when you have multiple tenants, be sure to switch to the correct tenant. Once installed, when you open the app, it will directly open the tenant.

> [!IMPORTANT]
> If you're using Business Central 2021 release wave 1 (version 18) or earlier, you can't install the app as described in this article. Instead, install the app from [Microsoft Store](https://go.microsoft.com/fwlink/?LinkId=734848). For more information and help about installing this legacy app, see [Preparing For and Installing the Business Central App](/dynamics365/business-central/dev-itpro/deployment/install-business-central-app).

## See Also

[Mobile Apps FAQ](ui-mobile-faq.yml)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
