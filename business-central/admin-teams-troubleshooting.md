---
title: Troubleshooting Microsoft Teams Integration
description: Learn about what you can do as an administrator to control Microsoft Teams integration and fix problems.
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork, troubleshooting, errors
ms.date: 01/06/2025
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Troubleshoot Microsoft Teams Integration with [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

This article provides information on how to identify and fix problems you might experience when using Microsoft Teams with [!INCLUDE [prod_short](includes/prod_short.md)], as a typical user or administrator.

## The sign-in link doesn't work

If you try to sign in to the [!INCLUDE [prod_short.md](includes/prod_short.md)] app for Teams immediately after installing the app, and the sign-in link doesn't react, the app might not be fully installed. To try to fix the issue, sign out of your Teams client and then sign in again.

## The Settings page is empty

You must first sign in to reach your settings. To sign into the app, either paste a link to a [!INCLUDE [prod_short.md](includes/prod_short.md)] record, or try to search for contacts. Both of these actions will lead you through a sign-up experience, after which you can use the **Settings** page.

## I changed company but it didn't seem to work

After you change the company on the **Settings** page, you might notice that the command box drop-down indicates you're still searching the previous company. This issue happens when you open the **Settings** page directly from the command box. In this case, the company was successfully changed, and you'll in fact search the company you switched to. The problem is that the command box drop-down hasn't updated yet. Close or unpin [!INCLUDE [prod_short.md](includes/prod_short.md)] from the command box, and then open the app again to ensure that the drop-down accurately reflects the company you're searching for. 

## "Something went wrong" error when searching for contacts

You might experience this error when you search in a company that isn't initialized or is in an unresponsive state. For example, you can't search in a new trial company that hasn't yet accepted the terms of use. To resolve this issue, try to sign in to the [!INCLUDE [prod_short.md](includes/prod_short.md)] Web client, and act on or dismiss any initial dialogs that appear.

## "Cannot find the contact/contact summary API" error when searching for contacts

This problem can be caused by customizations or industry solutions that affect or modify [!INCLUDE [prod_short.md](includes/prod_short.md)], or they don't provide a contact or contact summary API. If the problem continues, contact your administrator or supporting partner.

## None of my links expand into a card 

If you're experiencing this problem, here are a few things to try:

1. First, make sure that the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams is installed.

    To check, sign in to the Teams desktop app or Teams in the browser. Then, on the left side, select **Apps**, and search for **[!INCLUDE [prod_short](includes/prod_short.md)]**. When you find the **[!INCLUDE [prod_short](includes/prod_short.md)]** app, select it to open the app details page. If the **Add** button is shown, then the [!INCLUDE [prod_short](includes/prod_short.md)] app isn't installed. Learn more in [Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md).

    > [!NOTE]
    > Guest users can't immediately install apps. Learn more in [FAQ about collaborating with guests](teams-faq.md?tabs=collaborating#language). 

2. Next, check that you've signed in with the correct identity.

    In Teams, go to any chat, and under the message compose box, right-click the [!INCLUDE [prod_short](includes/prod_short.md)] icon, then choose **Settings**. The window that appears states the user account that you’re signed in as. Verify that it’s the correct user account.

3. Make sure codeunit 2718 **Page Summary Provider** is published as a web service.

    Teams connects to [!INCLUDE [prod_short](includes/prod_short.md)] using an endpoint to this codeunit on the [!INCLUDE [prod_short](includes/prod_short.md)] service. Learn more in [Publish a Web Service](across-how-publish-web-service.md).

4. Your organization can also restrict you from pasting links that expand into cards. Contact your administrator to understand the Teams organizational policies that apply to you.

## My link sometimes doesn’t expand into a card 

A link won't expand into a card in the following situations:

- The link targets a page that (at a technical level) isn't connected to a source table in [!INCLUDE [prod_short](includes/prod_short.md)]. You can check whether a page has a source table by using the page inspection pane in the Web client in [!INCLUDE [prod_short](includes/prod_short.md)]. Learn more about page inspection Learn more in [Inspecting Pages](across-inspect-page.md).
- Teams doesn't support link previews in some of its features. For example, when you pop out a chat, or you're a guest to another organization.
- Network issues cause Teams to silently abandon trying to display the card after 15 seconds, for example.
- Teams might not expand the link if you've already pasted a link into the same message compose box and deleted the card.
- When using Teams in some browsers such as Google Chrome or Mozilla Firefox, the link isn't automatically detected as soon as you paste it into the compose box. You might need to add a space after the link or press <kbd>Enter</kbd> for Teams to recognize the link and expand it into a card.

The link must also contain all the necessary information to locate the record and display the corresponding card. This information includes:

- The environment name, by including it in the URL path. If you don't specify the environment name, Teams assumes you're attempting to reach the environment named "Production".
- The company name, by using the *company=* parameter
- The page identifier, by using the *page=* parameter
- The bookmark to the record, by using the *bookmark=* parameter

For example:

`https://businesscentral.dynamics.com/?environmentname=Production&company=CRONUS%20USA%2C%20Inc.&page=21&dc=0&bookmark=21%3bEgAAAAJ7BTEAMAAwADAAMA%3d%3d`

Learn more about [!INCLUDE [prod_short](includes/prod_short.md)] URLs in [Web Client URL](/dynamics365/business-central/dev-itpro/developer/devenv-web-client-urls) in the [!INCLUDE [prod_short](includes/prod_short.md)] Developer and IT Pro Help.

## The details window opens, but shows an error before details are shown

This problem can be caused by a couple of things: lack of permissions in [!INCLUDE [prod_short](includes/prod_short.md)] or browser settings (when using Teams in the browser).

1. Verify your permissions in [!INCLUDE [prod_short](includes/prod_short.md)].

    To view details for a card, [!INCLUDE [prod_short](includes/prod_short.md)] checks your license and permissions to view that specific record and page in the specific company and environment. If you aren't authorized for any of these things, standard [!INCLUDE [prod_short](includes/prod_short.md)] error messages about permissions appear in the details window. 

    Learn more in [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

2. Check your browser settings if using Teams in the browser.

    - Your browser's pop-up blocker must be either turned off or set to allow pop-ups from the *businesscentral.dynamics.com* or *bc.dynamics.com* domains. Learn more in about allowing pop-ups for [!INCLUDE [prod_short](includes/prod_short.md)] in [Setting Up Your Browser](across-browser-settings.md#popup).
    - Your browser must have access to local browser storage for cookies and preferences as you work.
    - Avoid using guest or private browsing unless necessary, because they discard or block certain content in some browsers.

   Learn more about minimum browser requirements in [Minimum Requirements for Using [!INCLUDE [prod_short](includes/prod_short.md)]](product-requirements.md#browsers).

## I'm having problems with the camera or location in Teams

When using [!INCLUDE [prod_short](includes/prod_short.md)] features in the details window that require access to your location or device camera, you must first give your consent for Teams to access these device capabilities.  

- For Teams in the browser, make sure that your browser settings allow access to camera and location for [https://teams.microsoft.com](https://teams.microsoft.com).

- For Teams for iOS or Android, make sure that your device settings allow access to camera and location for the Teams mobile app. 

Learn more about changing these settings at [My camera isn't working in Teams](https://support.microsoft.com/office/my-camera-isn-t-working-in-teams-9581983b-c6f9-40e3-b0d8-122857972ade?ns=msftteams&version=16&ui=en-us&rs=en-us&ad=us) on Microsoft Support.

The [!INCLUDE [prod_short](includes/prod_short.md)] app doesn't support location in the Teams desktop app. Learn more in [Teams FAQ](teams-faq.md#location).

Some browsers, such as the new Microsoft Edge, allow you to choose which device camera to use when your device supports multiple cameras. 

## Teams displays mixed languages for my cards and card details

For cards and card details to display consistently in the same language in Teams, the language of your Teams client and the language you use in [!INCLUDE [prod_short](includes/prod_short.md)] Web client must match.

- Learn more about changing the language in Teams in [Change settings in Teams](https://support.microsoft.com/en-us/office/change-settings-in-teams-b506e8f1-1a96-4cf1-8c6b-b6ed4f424bc7) on Microsoft Support. 

- Learn more about changing the language in [!INCLUDE [prod_short](includes/prod_short.md)] [Change Basic Settings - Language](ui-change-basic-settings.md#language).

Learn more about how languages work between Teams and [!INCLUDE [prod_short](includes/prod_short.md)] in [Teams FAQ](teams-faq.md#language).

## I edited a field in the details window, but my change wasn't saved

Changes you make to a field in the details windows are automatically saved when you leave the field. Before you close the window after changing a field, be sure to select the <kbd>Tab</kbd> key or click/tap outside the field.

## A new tile appeared in the App Launcher. How do I remove it?

When you view your apps on the Office 365 home page (https://home.office.com) or in the app launcher, a new tile named "Business Central Teams Integration Service Connector" will appear after installing the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams. This tile provides no value in itself and can be safely hidden.

As an administrator, who has Microsoft Entra admin permissions, you can hide the tile by doing the following steps:

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).
2. Select **Enterprise apps**, then select **Business Central Teams Integration Service Connector**.
3. Select **Properties**, then set the **Visible To Users** switch to **No**.
4. Select **Save**.

> [!NOTE]
> It will be a while before this change takes effect.

## Duplicate text in the Share to Teams window

When you paste text into the message box in the **Share to Teams** window, the text is duplicated. This problem is known to Microsoft and will be addressed in a later update. 

## Unable to sign in to the Share to Teams window 

This problem can be caused by a various reasons. For example, the identity you are using to sign in must have access to Microsoft Teams, such as through a Microsoft 365 subscription.

## Can't pin a card to tab

Pinning is no longer available in Microsoft Teams.

## Someone added a tab, but the tab doesn’t show up for me

This problem is because you don’t have the BC app for Teams installed. Only those with the app installed will see Business Central tabs.

## Others see a different sorting or column layout than what the tab author sees

This problem is likely because you shared a list view that is a personal view. In this case, work with your administrator to create either role-specific list views that covers the different roles in the channel/chat, or create this view for the whole organization so that everyone can get a consistent view.

## Related information

[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Searching for Customers, Vendors, and Other Contacts from Microsoft Teams](across-search-contacts-teams.md)  
[Share Records in Microsoft Teams](across-working-with-teams.md)  
[Teams FAQ](teams-faq.md)  
[Changing Company and Other Settings in Teams](across-teams-settings.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]
