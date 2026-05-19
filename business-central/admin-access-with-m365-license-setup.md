---
title: Set Up Access with Microsoft 365 Licenses
description: A guide to how administrators can configure access to Business Central with Microsoft 365 licenses. 
author: mikebc
ms.author: mikebc 
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central 
ms.topic: how-to
ms.date: 08/12/2024
ms.custom: bap-template
ms.search.keywords: License, access, Microsoft 365, collaborate, collaboration, Teams, Microsoft Teams
ms.search.form: 9061,
---
# Set Up Business Central Access in Teams with Microsoft 365 Licenses

Administrators must complete multiple activities before users can access [!INCLUDE [prod_short](includes/prod_short.md)] with their Microsoft 365 license. The steps below represent the minimum setup required to get started. To learn more about access with Microsoft 365 licenses, go to [Business Central Access with Microsoft 365 Licenses](admin-access-with-m365-license.md).

## Guidelines

Setting up access with Microsoft 365 licenses involves the following tasks:

|Step|Task|Required|
|-|-|-|
|1|[Configure which Business Central data the Microsoft 365 licensed users have permission to view](#configure-permissions)|![check mark](media/check.png "check")|
|2|[Enable access with Microsoft 365 licenses on the Business Central environment](#enable-access-with-microsoft-365-licenses)|![check mark](media/check.png "check")|
|3|[Assign security group to the environment](#choose-who-gets-access-by-using-security-group)|
|4|[Deploy the Business Central app for Teams to users](#deploy-the-business-central-app-for-teams)|![check mark](media/check.png "check")|
|5|[Test the setup](#test-your-setup)||

> [!TIP]
> Except for the last task, you can complete the tasks in any order. You can do tasks separately, as described in the sections that follow or use the **Access with Microsoft 365 licenses** assisted setup guide to walk you through them.
>
> To run the assisted setup, do the following steps:
>
> 1. [!INCLUDE[open-search](includes/open-search.md)], enter **Assisted Setup**, and then choose the related link.
> 2. On the **Assisted Setup** page, go to the **Do more with Business Central** section and select **Access with Microsoft 365 licenses**.
> 3. Follow the instructions.  

## Configure permissions

[!INCLUDE [prod_short](includes/prod_short.md)] is secure by design and minimizes risk by granting no permissions to Microsoft 365 users out of the box. Administrators must configure object permissions that determine which tables, pages and reports can be accessed in Teams with only a Microsoft 365 license. These permissions are the starting permissions assigned when a user signs in for the first time with their Microsoft 365 license. 

To configure starting permissions:

1. In [!INCLUDE [prod_short](includes/prod_short.md)], search for **License Configuration**.
2. Select the Microsoft 365 license.
3. At the top of the **Microsoft 365** license page, select the edit icon ![Edit icon](media/edit-pencil.png), then turn on **Customize permissions**. 
4. In the **Custom Permission Sets** section, add the appropriate permission sets and choose whether they're applicable to a single company or all companies within the environment.

With this configuration, users with only a Microsoft 365 license are added to the **Users** list when they access [!INCLUDE [prod_short](includes/prod_short.md)] for the first time. For more information about users, go to [Creating Users According to Licenses](ui-how-users-permissions.md).

> [!NOTE]
> When synchronizing the users list in [!INCLUDE [prod_short](includes/prod_short.md)] with users in Microsoft 365, only users that have a [!INCLUDE [prod_short](includes/prod_short.md)] license are added to [!INCLUDE [prod_short](includes/prod_short.md)]'s users list. For more administrative control over permissions and profiles, you can assign a security group to the environment. When environments are secured using a security group and enable access with Microsoft 365 licenses, the **Update users from Microsoft 365** action in the **Users** page will also include users that only have a Microsoft 365 license. To learn about securing environments, see [Manage access using Microsoft Entra groups](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-access#manage-access-using-azure-active-directory-groups) in the developer and IT pro help.

> [!TIP]
> Looking for a quicker way to get started when trying out this feature on a sandbox or evaluation company? Assign the **D365 Read** permission set, which grants permission to most objects.  

When working with multiple environments, license configuration must be applied to each environment and can be different on each environment.

Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md) and [Composing Permission Sets](/dynamics365/business-central/dev-itpro/developer/devenv-permissionset-composing).

## Enable access with Microsoft 365 licenses

Access with Microsoft 365 licenses is off by default. Access must be enabled for each environment independently, giving administrators control and allowing for staged rollout across the organization. You turn on access by using the [!INCLUDE [prod_short](includes/prod_short.md)] admin center: 

1. In the upper-right corner, select **Settings** ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role center") > **Admin Center**.  
2. In the admin center, select **Environments**, then select the environment on which you want to change license access. 
3. On the **Environment details** page, select **Modify** for the **Access with Microsoft 365 licenses** setting.
4. In the **Microsoft 365 licenses** pane, turn on the switch. 
5. Select **Save** when done and accept the confirmation. The change comes into effect immediately.

## Choose who gets access by using security group

In the Business Center admin center, an environment can be assigned to one or more security groups to control access. You can assign a Microsoft Entra group to the environment. By assigning a Microsoft Entra group to an environment, only direct and indirect members of the group are granted access to the environment. Indirect members are users in another group, which itself is a member of the group assigned to the environment. Although all licensed users in Microsoft Entra ID will be added to the environment when it's synchronized with Microsoft 365, only group members can sign in. Learn more in [Manage access using Microsoft Entra groups](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-access#manage-access-using-azure-active-directory-groups) in the developer and IT pro help.

People in the security group must also have an applicable Microsoft 365 license to access Business Central from within Microsoft Teams. Get a list of applicable licenses in [Business Central access with Microsoft 365 licenses](admin-access-with-m365-license.md#requirements-for-individual-users-to-access-data-in-teams).

## Deploy the Business Central app for Teams

For [!INCLUDE [prod_short](includes/prod_short.md)] license holders to share data in Teams, and for Microsoft 365 license holders to access that data, each must have the [!INCLUDE [prod_short](includes/prod_short.md)] app for Teams installed. Although users can install the app by themselves, it's recommended that administrators use centralized deployment. Centralized deployment lets you roll out the app to a broader audience across the organization and minimize individual user effort. Laern more in [Installing the Business Central app by using Centralized Deployment](admin-teams-integration.md#installing-the-business-central-app-by-using-centralized-deployment).

> [!NOTE]
> If you have run centralized deployment before and only deployed the app to the security group of licensed [!INCLUDE [prod_short](includes/prod_short.md)] users, you'll need to run it again to deploy to additional groups or the whole organization, depending on how you are configuring access.

> [!TIP]
> Looking for a quicker way to get started when trying out this feature? Test users can install the app at [aka.ms/BCgetTeamsApp](https://aka.ms/BCgetTeamsApp).

## Test your setup

To verify that your setup is ready for production, the following steps will help you build the confidence that everything works as it should.

1. Create or identify two test users (A and B).

   - Test user A must have a [!INCLUDE [prod_short](includes/prod_short.md)] license and Microsoft 365 license with access to Teams.
   - Test user B must have only a Microsoft 365 license with access to Teams.

2. Sign in to the [!INCLUDE [prod_short](includes/prod_short.md)] web client as test user A.

   1. Open a record that test user B should have access to, such as an **Item** card in the appropriate company and environment.
   2. Select **Share** ![!Share to other apps action on pages.](media/share-icon.png) > **Share to Teams** to bring up the Share to Teams window.
   3. In the **Share to** field, add test user B as the recipient.
   4. Wait for the link to expand to a card and select Share.

3. Sign into Microsoft Teams as test user B.

   1. Select Chat and open the conversation with test user A.
   2. In the message sent by test user A, select the Details button on the card. If the [!INCLUDE [prod_short](includes/prod_short.md)] client is displayed and is read-only, your setup was successful.

> [!TIP]
> Something went wrong? Learn more in [Business Central troubleshooting](/troubleshoot/dynamics-365/business-central/welcome-business-central).

## Related information

[Overview of Business Central Access with Microsoft 365 licenses](admin-access-with-m365-license.md#minimum-requirements)  
[Troubleshoot Access with Microsoft 365 Licenses](admin-access-with-m365-license-troubleshooting.md)  
[Business Central and Microsoft Teams Integration](across-teams-overview.md)  
