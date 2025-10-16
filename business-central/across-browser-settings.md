---
title: Setting up your browser
description: Describes how to set up browsers to work with Business Central and products that integrate with it.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: Teams, web client, troubleshooting, errors
ms.date: 10/13/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up and troubleshoot your browser to work with Business Central Web Client

This article explains how to set up your browser so that the [!INCLUDE[web_client](includes/web_client.md)] and all its features work properly. Read this article if you're having problems opening the [!INCLUDE[web_client](includes/web_client.md)], your browser's settings can be the cause of some problems.

The article provides details for setting up Microsoft Edge, but the requirements for JavaScript, cookies, and pop-ups are the same for all supported browsers. For other browsers, refer to the instructions provided by the manufacturer.  

## Use a supported browser

Make sure to use a one of the supported browsers. See [Minimum Requirements for Using Business Central](product-requirements.md#browsers).

We recommend that you use a stable channel version of a web browser as it's the most reliable and stable version that has gone through extensive testing and bug fixing. This ensures that you have the best experience and are less likely to encounter any issues while using the web client.  

## Allow JavaScript from Business Central

*Problem:*

If the browser doesn't allow JavaScript, you see **NotSupported/DisabledJavaScript** in the address bar and an **HTTP Error 404.0 - Not Found** message when you try to open [!INCLUDE[prod_short](includes/prod_short.md)], and the 

<!-- http://localhost:8080/NotSupported/DisabledJavaScript HTTP Error 404.0 - Not Found
The resource you are looking for has been removed, had its name changed, or is temporarily unavailable. -->

*Fix:*

1. In Microsoft Edge, go to **Settings** > **Cookies and site permissions** > **JavaScript**.
2. Do one of the following steps. Choose the step that your organization recommends:

    - Move the **Allowed** toggle to the left (Off). Then, select **Add** and type the address (URL) for [!INCLUDE[prod_short](includes/prod_short.md)] in the **Site** box. Select **Add** when done.
    - Move the **Allowed** toggle to the right (On).

## Allow cookies from Business Central

*Problem:*

If the browser doesn't allow cookies, you get the following error:

**Sorry, the page could not be found. Please check the address and try again.** 

*Fix:*

1. In Microsoft Edge, go to **Settings** > **Cookies and site permissions** > **Cookies and site data**.
2. Move the **Allow sites to save and read cookie data** toggle to the right (On).  

## <a name="popup"></a>Allow pop-ups from Business Central

[!INCLUDE[prod_short](includes/prod_short.md)] integrates with several products. In some cases, like with Microsoft Teams, [!INCLUDE[prod_short](includes/prod_short.md)] opens, or "pop-ups," within the product. This capability requires that your browser allows pop-ups from [!INCLUDE[prod_short](includes/prod_short.md)].

*Problem:*

If pop-ups for [!INCLUDE[prod_short](includes/prod_short.md)] are being blocked, you get a message similar to the following message:

**Something went wrong. Your browser may be blocking pop-ups needed by Business Central.**

<!--
Something went wrong
Your browser may be blocking pop-ups needed by Business Central.

Change your browser settings to allow pop-ups or allow this for trusted domains, then try again.
If these settings are managed for your organization, you should contact your administrator for assistance.

Try again
-->
*Fix:*

1. In Microsoft Edge, go to **Settings** > **Cookies and site permissions** > **Pop-ups and redirects**.
2. Move the **Blocked** toggle to the right (On).
3. Select **Add**. In the **Site** box, type `https://businesscentral.dynamics.com`, then select **Add**.

## Related information

[Troubleshooting Teams](admin-teams-troubleshooting.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
