---
title: Manage Microsoft Teams Integration with Business Central
description: Manage Business Central integration with Microsoft Teams, configure access and deployment, and control whether shared cards display record data.
author: jswymer
ms.topic: overview
ai-usage: ai-assisted
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork
ms.date: 11/09/2026
ms.author: jswymer
ms.reviewer: jswymer
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.search.form: 2718_Primary
---

# Manage Microsoft Teams integration with Business Central

[!INCLUDE [online_only](includes/online_only.md)]

This article provides an overview of what you can do as an administrator to control Microsoft Teams integration with [!INCLUDE [prod_short](includes/prod_short.md)].

## In Microsoft Teams

### Minimum requirements

This section describes the minimum requirements for the [!INCLUDE [prod_short](includes/prod_short.md)] app features to work in Teams.

- Required licenses

    The [!INCLUDE[prod_short](includes/prod_short.md)] app requires a Teams license through a Microsoft 365 Business or Enterprise plan, Microsoft Teams EEA, or a similar plan that includes Microsoft Teams. Standalone Teams plans like Microsoft Teams (free) or Microsoft Teams Essentials aren't supported.

    Most features of the [!INCLUDE[prod_short](includes/prod_short.md)] app for Teams also require a [!INCLUDE [prod_short](includes/prod_short.md)] license, as shown in the following table.

    |What|[!INCLUDE [prod_short](includes/prod_short.md)] license|
    |----|---|
    |Search for [!INCLUDE [prod_short](includes/prod_short.md)] contacts.|:::image type="icon" source="media/check.png"::: Yes|
    |Paste a link to a [!INCLUDE [prod_short](includes/prod_short.md)] record into a conversation, and send it as a card.|:::image type="icon" source="media/check.png"::: Yes|
    |Share a link from a page in [!INCLUDE [prod_short](includes/prod_short.md)] to Teams conversation.|:::image type="icon" source="media/check.png"::: Yes|
    |View a card of a [!INCLUDE [prod_short](includes/prod_short.md)] record in a conversation.||
    |View more details of a card for a [!INCLUDE [prod_short](includes/prod_short.md)] record in a conversation.|A Business Central license or configured access with a Microsoft 365 license.|
    |Open a page link in [!INCLUDE [prod_short](includes/prod_short.md)] from a conversation.|:::image type="icon" source="media/check.png"::: Yes|

- URL previews

    The **URL previews** policy setting must be turned on. Otherwise, a card can't be generated for [!INCLUDE [prod_short](includes/prod_short.md)] links pasted into a Teams conversation. Learn more about this setting in [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### Manage the Business Central app (optional)

As a Teams administrator, you can manage all apps for your organization, including the [!INCLUDE [prod_short](includes/prod_short.md)] app. You can approve or install the [!INCLUDE [prod_short](includes/prod_short.md)] app for your organization, block user's from installing the app, and more.

Learn more in the Microsoft Teams documentation at:

- [Manage your apps in the Microsoft Teams admin center](/MicrosoftTeams/manage-apps)
- [Manage app setup policies in Microsoft Teams](/microsoftteams/teams-app-setup-policies)

## In Business Central

### Minimum requirements

- [!INCLUDE [prod_short](includes/prod_short.md)] version:

  Teams integration is only supported for [!INCLUDE [prod_short](includes/prod_short.md)] online, not on-premises.

- Codeunit **2718 Page Summary Provider** is published as a web service:

  This codeunit is published as a web service by default. The codeunit is part of the [!INCLUDE [prod_short](includes/prod_short.md)] system application. It's used to get the field data for a [!INCLUDE [prod_short](includes/prod_short.md)] page added to a Teams conversation. Learn more about publishing web services in [Publish a Web Service](across-how-publish-web-service.md).

- <a name="permissions"></a>User permissions:

  For the most part, the contact search, pages, and data that users can view and edit in a Teams conversation is controlled by their permissions in [!INCLUDE [prod_short](includes/prod_short.md)].

  - To search for contacts, users must have at least read permission to the `Contact` table.
  - To paste a [!INCLUDE [prod_short](includes/prod_short.md)] link into a Teams conversation and have it expand into a card, users must have execute permission on the page and read permission on its data.
  - Once a card is submitted into a conversation, any user in that conversation can view that card without permission to [!INCLUDE [prod_short](includes/prod_short.md)].
  - To view a card's details or open its record in [!INCLUDE [prod_short](includes/prod_short.md)], users need execute permission on the target page and read permission to the table data that the page displays.
  - To create, modify, or delete records, users need the corresponding insert, modify, or delete permissions on the table data and a [!INCLUDE [prod_short](includes/prod_short.md)] license that allows the operation. Access with only a Microsoft 365 license is read-only. Assigning write permissions doesn't override this license restriction. Learn more in [Business Central access with Microsoft 365 licenses](admin-access-with-m365-license.md#data-access).

  Learn more in [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

<a name="installing-the-business-central-app-by-using-centralized-deployment"></a>

## Install the Business Central app centrally

Use the Microsoft Teams admin center to install the Business Central app for all users, specific groups, or individual users. If your organization has migrated to app-centric management, manage installation from **Manage apps**. Otherwise, use an app setup policy. Installing the app and pinning it are separate tasks.

> [!NOTE]
> To set up Centralized Deployment, your Teams account must have at least the [Teams Administrator](/entra/identity/role-based-access-control/permissions-reference#teams-administrator) role.

1. In Business Central, [!INCLUDE[open-search-lowercase](includes/open-search-lowercase.md)], enter **Teams App Centralized Deployment**, and then choose the related link. Or open [Teams App Centralized Deployment](https://businesscentral.dynamics.com/?page=1833) directly.
1. Read the information on the **Set up the Business Central app for Teams**, then choose **Next** when ready.
1. Open the [Teams admin center](https://go.microsoft.com/fwlink/?linkid=2163970), and use the method that applies to your organization.

    - **App-centric management:** Go to **Teams apps** > **Manage apps**. Find and select **Business Central**, and then select **Edit installs**. Choose the users or groups to install the app for, or choose everyone, and then select **Apply**.
    - **App setup policy:** Complete the following steps only if your organization hasn't migrated app installation to app-centric management.
        1. Go to **Teams apps** > **Setup policies**.
        1. Create a new policy or select the policy that you want to use, then select **Add apps** under **Installed apps**.
        1. In the **Add installed apps** pane, search for and select **Business Central**.
        1. Choose **Add**.

           Business Central should now appear under **Installed apps** for the policy.
        1. Configure more settings as needed, then choose **Save**.

    Learn more in [Preinstall Teams apps for your organization](/microsoftteams/install-teams-apps).
1. Go back to **Teams App Centralized Deployment** in Business Central, select **Next**, and then select **Done**.

> [!IMPORTANT]
> It can take up to 24 hours for the app setup policy to be applied and the app deployed to users.

With app-centric management, installation makes the app available to the selected users and groups, so you don't need a separate availability assignment. Existing installation settings from app setup policies aren't automatically migrated.

To pin the app for users, use **Pinned apps** in an app setup policy. Pinning remains managed through setup policies even when installation uses app-centric management. Learn more in [Pin apps in Teams](/microsoftteams/teams-app-setup-policies#pin-apps).

## Manage privacy and compliance

Microsoft Teams provides extensive controls for compliance and management of sensitive or personally identifiable data&mdash;including data added to chats and channels by the [!INCLUDE [prod_short](includes/prod_short.md)] app.

### Understand where Business Central cards are stored

After a card is sent to a chat, the card and the fields shown on the card are copied to Teams. This information is subject to the Teams policies for your organization, such as data retention policies. When displaying card details, none of the data in the details window is stored in Teams. The data remains stored in [!INCLUDE [prod_short](includes/prod_short.md)] and will only be retrieved by Teams when the user chooses to view the details. 

- Learn more about where Teams stores that data at [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams).
- Learn more about retention policies in Teams at [Retention policies in Microsoft Teams](/microsoftteams/retention-policies).

### Restrict sharing of cards

You prevent specific users or groups from sending cards to chats or channels by setting up messaging policies that turn off the **URL previews** setting. For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

You can also use information barriers to prevent individuals or groups from communicating with each other. To learn more, see [Information barriers in Microsoft Teams](/microsoftteams/information-barriers-in-teams).

Data loss prevention features in the Microsoft Purview can't be applied specifically to cards. But they can be applied to the chat messages that contain the cards.

### Respond to data requests

Use **Delete sent messages** to let users delete their own messages that contain sensitive cards. Use **Owners can delete sent messages** to let owners delete messages sent by other users. Learn more at [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

Content search and eDiscovery compliance features in the Microsoft Purview can also be applied to cards.

Because card data in Teams is a copy of data in [!INCLUDE [prod_short](includes/prod_short.md)], you can also use [!INCLUDE [prod_short](includes/prod_short.md)] features to export a customer’s data if requested. Learn more  about privacy in [!INCLUDE [prod_short](includes/prod_short.md)] in [Privacy FAQ for Business Central Customers](/dynamics365/business-central/dev-itpro/security/privacyfaq).

## Show or hide record data on cards

When a record is shared with others in a Teams chat or channel, a card with fields that contain data about the record is shown. All recipients can view this data (or record summary) by default, regardless of their license or permissions in Business Central. If you're an admin, you can use the **Card Settings** assisted setup guide to hide the record summary from appearing on cards in Teams. Hiding the record summary removes all fields and images but continues to show the **Details** button and other non-record information on the card.

|Record summary on|Record summary off|
|-|-|
|:::image type="content" source="media/card-settings-example-on.png" alt-text="Image that shows a card in Teams when the record summary is turned on.":::|:::image type="content" source="media/card-settings-example-off.png" alt-text="Image that shows a card in Teams when the record summary is turned off.":::|

You configure the setting per environment. So when you turn the record summary on or off, it affects all companies in the environment.

The setting applies only to newly created cards. Cards that were shared previously aren't changed. Hiding the summary doesn't change access to card details, which still depends on the recipient's license and Business Central permissions.

To run the guide, you need permission to read and change the **Page Summary Settings** table. The **Page Summary - Admin** permission set provides these permissions.

1. In Business Central, open the environment that you want to change.

   > [!TIP]
   > To switch the environment, select <kbd>Ctrl</kbd>+<kbd>O</kbd>.
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Card Settings**, and then choose the related link.
1. Read the information on the **Card Settings**, then choose **Next** when ready.
1. On the **Data visibility** page, turn on the **Show record summary** switch to display data on the cards or off to hide the data.
1. Select **Next** and follow the instructions to complete the setup guide.

## Related information

[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Troubleshooting Teams](admin-teams-troubleshooting.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## Try Business Central

[!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]
