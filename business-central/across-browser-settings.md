---
title: Set Up and Troubleshoot Your Browser for the Business Central Web Client
description: Fix browser problems with the Business Central web client by checking supported browsers and allowing JavaScript, cookies, and required pop-ups.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: Teams, web client, troubleshooting, errors
ms.date: 11/10/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up and troubleshoot your browser for the Business Central web client

This article explains how to set up your browser so that the [!INCLUDE[web_client](includes/web_client.md)] and all its features work properly. Read this article if you're having problems opening the [!INCLUDE[web_client](includes/web_client.md)], your browser's settings can be the cause of some problems.

The article provides details for setting up Microsoft Edge, but the requirements for JavaScript, cookies, and pop-ups are the same for all supported browsers. For other browsers, refer to the instructions provided by the manufacturer.  

## Use a supported browser

Make sure to use a one of the supported browsers. Learn more in [Minimum Requirements for Using Business Central](product-requirements.md#browsers).

We recommend that you use a stable channel version of a web browser as it's the most reliable and stable version that has gone through extensive testing and bug fixing. This ensures that you have the best experience and are less likely to encounter any issues while using the web client.  

## Allow JavaScript from Business Central

*Problem:*

If the browser doesn't allow JavaScript, the web client can't start. You might see `NotSupported/DisabledJavaScript` in the address bar and a message explaining that JavaScript is disabled.

<!-- http://localhost:8080/NotSupported/DisabledJavaScript HTTP Error 404.0 - Not Found
The resource you are looking for has been removed, had its name changed, or is temporarily unavailable. -->

*Fix:*

1. Open your browser's site permission settings for JavaScript.
1. Allow JavaScript for the address that you use to open [!INCLUDE[prod_short](includes/prod_short.md)].

If your organization manages this setting, contact your administrator.

## Allow cookies from Business Central

*Problem:*

If the browser doesn't allow cookies, the web client can't start correctly. You might see a browser requirements message explaining that the browser doesn't accept cookies.

*Fix:*

1. In Microsoft Edge, go to **Settings** > **Privacy, search, and services** > **Cookies**.
1. Turn on **Allow sites to save and read cookie data (recommended)**.

Learn more in [Manage cookies in Microsoft Edge](https://support.microsoft.com/microsoft-edge/delete-cookies-in-microsoft-edge-63947406-40ac-c3b8-57b9-2a946a29ae09).

## <a name="popup"></a>Allow pop-ups from Business Central

[!INCLUDE[prod_short](includes/prod_short.md)] integrates with several products. In some cases, like with Microsoft Teams, [!INCLUDE[prod_short](includes/prod_short.md)] opens, or "pop-ups," within the product. This capability requires that your browser allows pop-ups from [!INCLUDE[prod_short](includes/prod_short.md)].

*Problem:*

If pop-ups for [!INCLUDE[prod_short](includes/prod_short.md)] are being blocked, you get a message similar to the following message:

**Something went wrong. Your browser may be blocking pop-ups needed by Business Central.**

*Fix:*

1. In Microsoft Edge, go to **Settings** > **Privacy, search, and services** > **Site permissions**.
1. Under **Content**, select **Pop-ups and redirects**. Keep **Blocked (recommended)** turned on.
1. Under **Allowed to send pop-ups and use redirects**, select **Add site**. Enter `https://businesscentral.dynamics.com`, then select **Add**.

Learn more in [Manage pop-ups in Microsoft Edge](https://support.microsoft.com/microsoft-edge/block-pop-ups-in-microsoft-edge-1d8ba4f8-f385-9a0b-e944-aa47339b6bb5).

## Related information

[Troubleshoot Teams](admin-teams-troubleshooting.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
