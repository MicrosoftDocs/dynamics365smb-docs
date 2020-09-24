---
title: Working with Business Central Data in Microsoft Teams| Microsoft Docs
description: Share Business Central records directly in a Teams conversation.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 07/10/2020
ms.author: jswymer
---

# Managing Microsoft Teams Integration with Business Central

[!INCLUDE [prodshort](includes/2020rw_online_only.md)]

As an administrator, there a few things you can do to control who in your organization can use the Teams integration and what

## In Microsoft Teams

### Teams license

This table gives you an overview of the licenses needed for the [!INCLUDE [prodshort](includes/prodshort.md)] app features to work in a Teams conversation.

|What|Teams license|Business Central license|
|----|---|---|
|Send a card|![check](media/check.png "check")|![check](media/check.png "check")|
|View a card|![check](media/check.png "check")||
|View card details|![check](media/check.png "check")|![check](media/check.png "check")|

### Managing the Business Central app

As a Teams administrator, manage all Teams apps for your organization, including the [!INCLUDE [prodshort](includes/prodshort.md)] app. For example, you can approve or upload new Business Central app for your organization,  block or allow user's to install the app, and more. For more information, see the following articles in the Microsoft Teams documentation:

[Manage your apps in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/manage-apps)
[Manage app setup policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)

If you will test with multiple users, you may need to repeat step 3 for each user or use the administrative setup policy to set this up for all users.

## In [!INCLUDE [prodshort](includes/prodshort.md)]

For the most part, the pages and data that users can view and edit in a Teams conversations is controlled by their permissions in [!INCLUDE [prodshort](includes/prodshort.md)] client.

- To paste a [!INCLUDE [prodshort](includes/prodshort.md)] link into a Teams conversation and have it expand into a card, users must have at least read permission on thw page and its data.
- Once a card is submitted into a conversation, any user in that conversation can view that card without permission to Business Central.
- To view more details for a card or open the record in [!INCLUDE [prodshort](includes/prodshort.md)], users must have read permission on the page and its data.
- To change data, user's need modify permissions.

For information about permissions, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).

## See Also

[Getting Started](product-get-started.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
