---
title: Managing Microsoft Teams Integration with Business Central| Microsoft Docs
description: Manage Business Central integration with Microsoft Teams.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork
ms.date: 10/08/2020
ms.author: jswymer
---

# Managing Microsoft Teams Integration with Business Central

[!INCLUDE [teams_preview.md](includes/teams_preview.md)]

This article provides an overview of what you can do as an administrator to control Microsoft Teams integration with [!INCLUDE [prodshort](includes/prodshort.md)].

## In Microsoft Teams

### Minimum requirements

This section describes the minimum requirements for the [!INCLUDE [prodshort](includes/prodshort.md)] app features to work in Teams.

- Required licenses

    This table gives you an overview of the licenses needed for the [!INCLUDE [prodshort](includes/prodshort.md)] app features to work in Teams.

    |What|Teams license|Business Central license|
    |----|---|---|
    |Paste a link to a [!INCLUDE [prodshort](includes/prodshort.md)] record into a conversation, and send it as a card.|![check mark](media/check.png "check")|![check mark](media/check.png "check")|
    |View a card of a [!INCLUDE [prodshort](includes/prodshort.md)] record in a conversation.|![check mark](media/check.png "check")||
    |View more details of card for a [!INCLUDE [prodshort](includes/prodshort.md)] record in a conversation.|![check mark](media/check.png "check")|![check mark](media/check.png "check")|

- Allow URL previews

    **Allow URL previews** policy setting must be turned on. Otherwise, a card can't be generated for Business Central links pasted into a Teams conversation. For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).

### Managing the Business Central app (optional)

As a Teams administrator, you can manage all apps for your organization, including the [!INCLUDE [prodshort](includes/prodshort.md)] app. You can approve or install the [!INCLUDE [prodshort](includes/prodshort.md)] app for your organization, block user's from installing the app, and more.

For more information, see the following articles in the Microsoft Teams documentation:

- [Manage your apps in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/manage-apps)
- [Manage app setup policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)

## In [!INCLUDE [prodshort](includes/prodshort.md)]

### Minimum requirements

- [!INCLUDE [prodshort](includes/prodshort.md)] version:

    [!INCLUDE [prodshort](includes/prodshort.md)] 2020 release wave 2 (version 17) or later. Teams integration is only supported for [!INCLUDE [prodshort](includes/prodshort.md)] online; not on-premises.

- Codeunit **2718 Page Summary Provider** is published as a web service:

    This codeunit is published as a web service by default. The codeunit is part of the [!INCLUDE [prodshort](includes/prodshort.md)] system application. It's used to get the field data for a [!INCLUDE [prodshort](includes/prodshort.md)] page added to a Teams conversation. 

- User permissions:

    For the most part, the pages and data that users can view and edit in a Teams conversation is controlled by their permissions in [!INCLUDE [prodshort](includes/prodshort.md)].
    
    - To paste a [!INCLUDE [prodshort](includes/prodshort.md)] link into a Teams conversation and have it expand into a card, users must have at least read permission on the page and its data.
    - Once a card is submitted into a conversation, any user in that conversation can view that card without permission to Business Central.
    - To view more details for a card or open the record in [!INCLUDE [prodshort](includes/prodshort.md)], users must have read permission on the page and its data.
    - To change data, user's need modify permissions.
    
    For information about permissions, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

## See Also
[Business Central and Microsoft Teams Integration Overview](across-teams-overview.md)  
[Install the [!INCLUDE [prodshort](includes/prodshort.md)] App for Microsoft Teams](across-install-app-for-teams.md)  
[Developing for Teams Integration](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  
[Getting Started](product-get-started.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
