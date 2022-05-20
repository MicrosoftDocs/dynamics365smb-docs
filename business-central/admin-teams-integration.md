---
title: Managing Microsoft Teams Integration with Business Central| Microsoft Docs
description: Manage Business Central integration with Microsoft Teams.
author: jswymer

ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork
ms.date: 04/12/2021
ms.author: jswymer
---

# Managing Microsoft Teams Integration with [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE [online_only](includes/online_only.md)]

This article provides an overview of what you can do as an administrator to control Microsoft Teams integration with [!INCLUDE [prod_short](includes/prod_short.md)].

## In Microsoft Teams

### Minimum requirements

This section describes the minimum requirements for the [!INCLUDE [prod_short](includes/prod_short.md)] app features to work in Teams.

- Required licenses

    The [!INCLUDE[prod_short](includes/prod_short.md)] app requires a Teams license through a Microsoft 365 Business or Enterprise subscription. Standalone Teams subscriptions such as Microsoft Teams (free) or Microsoft Teams Essentials aren't supported.

    Most features of the [!INCLUDE[prod_short](includes/prod_short.md)] app for Teams also require a [!INCLUDE [prod_short](includes/prod_short.md)] license, as shown in the following table.

    |What|[!INCLUDE [prod_short](includes/prod_short.md)] license|
    |----|---|
    |Search for [!INCLUDE [prod_short](includes/prod_short.md)] contacts.|![check mark](media/check.png "check")|
    |Paste a link to a [!INCLUDE [prod_short](includes/prod_short.md)] record into a conversation, and send it as a card.|![check mark](media/check.png "check")|
    |Share a link from a page in [!INCLUDE [prod_short](includes/prod_short.md)] to Teams conversation.|![check mark](media/check.png "check")|
    |View a card of a [!INCLUDE [prod_short](includes/prod_short.md)] record in a conversation.||
    |View more details of card for a [!INCLUDE [prod_short](includes/prod_short.md)] record in a conversation.|![check mark](media/check.png "check")|
    |Open a page link in [!INCLUDE [prod_short](includes/prod_short.md)] from a conversation.|![check mark](media/check.png "check")|

- Allow URL previews

    **Allow URL previews** policy setting must be turned on. Otherwise, a card can't be generated for [!INCLUDE [prod_short](includes/prod_short.md)] links pasted into a Teams conversation. For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### Managing the [!INCLUDE [prod_short](includes/prod_short.md)] app (optional)

As a Teams administrator, you can manage all apps for your organization, including the [!INCLUDE [prod_short](includes/prod_short.md)] app. You can approve or install the [!INCLUDE [prod_short](includes/prod_short.md)] app for your organization, block user's from installing the app, and more.

For more information, see the following articles in the Microsoft Teams documentation:

- [Manage your apps in the Microsoft Teams admin center](/MicrosoftTeams/manage-apps)
- [Manage app setup policies in Microsoft Teams](/microsoftteams/teams-app-setup-policies)

## In [!INCLUDE [prod_short](includes/prod_short.md)]

### Minimum requirements

- [!INCLUDE [prod_short](includes/prod_short.md)] version:

    [!INCLUDE [prod_short](includes/prod_short.md)] 2021 release wave 1 or later. Teams integration is only supported for [!INCLUDE [prod_short](includes/prod_short.md)] online; not on-premises.

- Codeunit **2718 Page Summary Provider** is published as a web service:

    This codeunit is published as a web service by default. The codeunit is part of the [!INCLUDE [prod_short](includes/prod_short.md)] system application. It's used to get the field data for a [!INCLUDE [prod_short](includes/prod_short.md)] page added to a Teams conversation. For information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

- <a name="permissions"></a>User permissions:

    For the most part, the contact search, pages, and data that users can view and edit in a Teams conversation is controlled by their permissions in [!INCLUDE [prod_short](includes/prod_short.md)].

    - To search for contacts, users must have at least read permission to the **Contacts** table. 
    - To paste a [!INCLUDE [prod_short](includes/prod_short.md)] link into a Teams conversation and have it expand into a card, users must have at least read permission on the page and its data.
    - Once a card is submitted into a conversation, any user in that conversation can view that card without permission to [!INCLUDE [prod_short](includes/prod_short.md)].
    - To view more details for a card or open the record in [!INCLUDE [prod_short](includes/prod_short.md)], users must have read permission on the page and its data.
    - To change data, user's need modify permissions.
    
    For information about permissions, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

## Installing the Business Central app by using Centralized Deployment

The Microsoft Teams admin center is where you configure Teams app setup policies for the organization. In the Teams admin center, you can use the Centralized Deployment feature to automatically install the Business Central app in Teams for all users in your organization, specific groups, or individual users.

> [!NOTE]
> To set up Centralized Deployment, your Teams account must have the **Teams Service admin**  role or the **Global admin** role.

1. In Business Central, choose the ![Magnifying glass that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Teams App Centralized Deployment**, and then choose the related link. Or, select [here](https://businesscentral.dynamics.com/?page=1833) to open the page directly.
2. Read the information on the **Set up the Business Central app for Teams**, then choose **Next** when ready.
3. Open the [Teams admin center](https://go.microsoft.com/fwlink/?linkid=2163970), and complete the following steps.
    1. Go to **Teams apps** > **Setup policies**.
    2. Create a new policy or select the policy that you want to use to install the Business Central app, then select **Add apps**.
    3. In the **Add installed apps** page, search for and select **Business Central**.
    4. Choose **Add**.

       Business Central should now appear under **Installed apps** for the policy.
    5. Configure any additional settings, then choose **Save**.

    For more information about setup policies in Teams, see [Manage app setup policies in Microsoft Teams](/MicrosoftTeams/teams-app-setup-policies) in the Teams documentation.
4. Go back to **Teams App Centralized Deployment** in Business Central, and select **Done**.

> [!IMPORTANT]
> It can take up to 24 hours for the app set up policy to be applied and the app deployed to users.

## Managing privacy and compliance 

Microsoft Teams provides extensive controls for compliance and management of sensitive or personally identifiable data&mdash;including data added to chats and channels by the [!INCLUDE [prod_short](includes/prod_short.md)] app.

### Understanding where [!INCLUDE [prod_short](includes/prod_short.md)] cards are stored

After a card is sent to a chat, the card and the fields shown on the card are copied to Teams. This information is subject to the Teams policies for your organization, such as data retention policies. When displaying card details, none of the data in the details window is stored in Teams. The data remains stored in [!INCLUDE [prod_short](includes/prod_short.md)] and will only be retrieved by Teams when the user chooses to view the details. 

- To learn more about where Teams stores that data, see [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams).
- To learn more about retention policies in Teams, see [Retention policies in Microsoft Teams](/microsoftteams/retention-policies).

### Restricting sharing of cards 

You prevent specific users or groups from sending cards to chats or channels by setting up messaging policies that turn off the **URL Previews** setting. For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams). 

You can also use information barriers to prevent individuals or groups from communicating with each other. To learn more, see [Information barriers in Microsoft Teams](/microsoftteams/information-barriers-in-teams).

Data loss prevention features in the Microsoft 365 Security & Compliance Center can't be applied specifically to cards. But they can be applied to the chat messages that contain the cards. <!-- To track upcoming advanced features that include enabling DLP for cards, see [https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=67093).-->

### Responding to data requests

You allow team members and team owners to delete messages that contain sensitive cards by setting up messaging policies, like: **Owners can delete sent messages** and **Users can delete sent messages**. For more information, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

Content search and eDiscovery compliance features in the Microsoft 365 Security & Compliance Center can also be applied to cards.

Because card data in Teams is a copy of data in [!INCLUDE [prod_short](includes/prod_short.md)], you can also use [!INCLUDE [prod_short](includes/prod_short.md)] features to export a customer’s data if requested. For more information about privacy in [!INCLUDE [prod_short](includes/prod_short.md)], see [Privacy FAQ for Business Central Customers](/dynamics365/business-central/dev-itpro/security/privacyfaq).

## See Also
[[!INCLUDE [prod_short](includes/prod_short.md)] and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prod_short](includes/prod_short.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Teams FAQ](teams-faq.md)  
[Troubleshooting Teams](admin-teams-troubleshooting.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]