---
title: Optimize Outlook for Your Business Inbox
description: Learn how Outlook updates, Microsoft Edge WebView2, and supported browsers can help improve your Business Central add-in experience in Outlook.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Outlook, Microsoft 365, inbox, business inbox, WebView2, Edge, addin, add-in
ms.date: 11/09/2026
ai-usage: ai-assisted
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Optimize Outlook for your business inbox

This article discusses things you can do to get the best possible experience with the Business Inbox in Microsoft Outlook. 

## Update Outlook

Use a supported version of Outlook and install its current updates. The older version 1905 and 2012 recommendations aren't a substitute for keeping Office supported and up to date. On Windows, supported Office add-ins use Microsoft Edge WebView2, not Internet Explorer. Learn more in [Browsers and webview controls used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins).

### How to check your version of Outlook

Follow this Microsoft Support guide to check which version of Outlook you have:

[About Office: What version of Office am I using?](https://support.microsoft.com/office/about-office-what-version-of-office-am-i-using-932788b8-a3ce-44bf-bb09-e334518b8b19)

> [!IMPORTANT]
> Office 2019 reached the end of support on October 14, 2025. If you still use it, plan an upgrade to a supported version. Learn more in [Overview of Office 2019](/office/2019/overview).

### How to update Outlook

To update Outlook to the latest version, follow this Microsoft Support guide or contact your administrator:

[Install Office updates](https://support.microsoft.com/office/install-office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5)

## Install Microsoft Edge WebView2

For Outlook on Windows, make sure that Microsoft Edge WebView2 Runtime is installed. Supported versions of Office install it by default. If it's missing or its installation is blocked, ask your administrator for help. Installing the Microsoft Edge browser alone isn't a substitute for the runtime. Learn more in [Microsoft Edge WebView2 and Microsoft 365 Apps](/microsoft-365-apps/deploy/webview2-install).

### How to check if Microsoft Edge WebView2 is installed 

To check if you have Microsoft Edge WebView2 installed on a computer, do the following steps:

From Start menu:

1. Choose **Start** :::image type="icon" source="media/windows-start-icon.png"::: > **Settings** :::image type="icon" source="media/windows-settings-icon.png"::: > **Apps** > **Installed apps**. On Windows 10, use **Apps & features** instead.
1. In the search box, type **WebView2**. If Microsoft Edge WebView2 is installed, you see an entry called **Microsoft Edge WebView2 Runtime**.

From Control Panel:

1. In the search box next to **Start** :::image type="icon" source="media/windows-start-icon.png":::, type **Control Panel**, and then select the result.
1. Choose **Programs** > **Programs and Features**.
1. In the search box, type **WebView2**. If Microsoft Edge WebView2 is installed, you see an entry called **Microsoft Edge WebView2 Runtime**.

### How to install Microsoft Edge WebView2 

1. Go to [Download the WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2#download-the-webview2-runtime).
1. Download the **Evergreen Bootstrapper** for an internet-connected device, or the **Evergreen Standalone Installer** for an offline installation.
1. Run the downloaded installer, and then restart Outlook.

> [!NOTE]
> Your organization might restrict which components can be installed on your device. Contact your administrator for assistance. Learn more about the installation options in [Distribute your app and the WebView2 Runtime](/microsoft-edge/webview2/concepts/distribution).

## Use a supported browser

Consider using Outlook for the Web in one of the browsers supported by Business Central. For a list of supported browsers, see [Minimum Requirements for Using Business Central](product-requirements.md#browsers).

## Related information

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Getting Business Central on my Mobile Device](install-mobile-app.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Minimum Requirements for Outlook](product-requirements.md#outlook)  
[Use add-ins in Outlook on the web](https://support.office.com/article/Using-Add-ins-in-Outlook-on-the-web-8f2ce816-5df4-44a5-958c-f7f9d6dabdce?appver=OWB150)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
