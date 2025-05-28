---
title: Manage permissions through user groups (legacy)
description: This article describes how to use users groups to define user permissions.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.search.keywords: access, right, security, permissions
ms.search.form: 1, 119, 8930, 9800, 9807, 9808, 9830, 9831, 9802, 9855, 9862, 9875_Primary, 9874_Primary, 9873_Primary, 9872_Primary, 9877_Primary, 9869_Primary, 9868_Primary, 9871_Primary
ms.date: 05/28/2025
ms.service: dynamics-365-business-central
---

# Manage permissions through user groups (legacy)

[!INCLUDE [2023rw1-sec-group-long](includes/2023rw1-sec-group-long.md)]

User groups help you manage permission sets across the company. [!INCLUDE [prod_short](includes/prod_short.md)] online includes default user groups that are assigned to users automatically based on their license. You can add users manually to a user group, and you can create new user groups as copies of existing ones.  

You start by creating a user group. Then you assign permission sets to the group to define which object users of the group can access. When you add user to the group, the permission sets defined for the group applies to the user.

Permission sets assigned to a user through a user group stay synchronized. A change to the user group permissions is automatically propagated to the users. If you remove a user from a user group, the involved permissions are automatically revoked.

## Add users to a user group

The following procedure explains how to create user groups manually. To learn how to create user groups automatically, go to [To copy a user group and all its permission sets](#to-copy-a-user-group-and-all-its-permission-sets).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.

    1. Alternatively, on the **Users** page, choose the **User Groups** action.
2. On the **User Group** page, choose the **User Group Members** action.
3. On the **User Group Members** page, choose the **Add Users** action.

## Copy a user group and all its permission sets

To quickly define a new user group, you can copy all permission sets from an existing user group to your new user group.

> [!NOTE]
> The user group members aren't copied to the new user group. You must add them manually afterwards. To learn more, go to [To add users to a user group](#to-add-users-to-a-user-group).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to copy, and then choose the **Copy User Group** action.
3. In the **New User Group Code** field, enter a name for the group, and then choose the **OK** button.

The new user group is added to the **User Groups** page. Proceed to add users. To learn more, go to [To add users to a user group](#to-add-users-to-a-user-group) section.  

> [!IMPORTANT]
> A validation error displays if you try to assign a user group that refers to a permission set which was defined in an extension that you uninstalled. It's because the App ID of the extension is validated whenever something references it. To assign that user group to a user, either:
>
> - Reinstall the extension.
> - Remove the reference of the uninstalled extension from the permission set.
> - Remove that permission set from the user group.

## Assign permission sets to user groups

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to assign permission to.  

    Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **User Permission Sets** action to open the **User Permission Sets** page.
4. On the **User Permission Sets** page, on a new line, fill in the fields as necessary.

## Assign a permission set on the Permission Set by User Group page

The following procedure explains how to assign permission sets to a user group on the **Permission Set by User Group** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User Group** action.
3. On the **Permission Set by User Group** page, select the **[user group name]** field on a line for the relevant permission set to assign the set to the user group.
4. Select the **All User Groups** checkbox to assign the permission set to all user groups.

You can also assign permissions sets directly to a user.
license configurations on the **License Configuration** page. Choose a license, and then delete all permission sets assigned to it.

## Convert users groups to security groups

> [!NOTE]
> Security groups replace user groups in 2024 release wave 2 (version 25) and later. If you're using on-premises version 22, 23, or 24, use the assisted setup guide to convert user groups to permission sets and transition to security groups.

Security groups are very similar to the user groups that are currently available. However, user groups are only relevant for [!INCLUDE [prod_short](includes/prod_short.md)]. Security groups are based on groups in Microsoft Entra ID or Windows Active Directory, depending on whether you're using [!INCLUDE [prod_short](includes/prod_short.md)] online or on-premises, respectively. Groups benefit administrators because they can use them with other Dynamics 365 apps. For example, if salespeople use [!INCLUDE [prod_short](includes/prod_short.md)] and SharePoint, administrators don't have to recreate the group and its members.

### Convert user groups to permission sets

In 2023 release wave 1 and later, you can convert user groups to permission sets in your tenant. The permission sets provide the same functionality as user groups. Here are some examples:

* You can use the **Users** FactBox to manage permissions for users.
* You can drill down on the permission set name to add other permission sets to the set you're working on. To learn more, go to [To add other permission sets](ui-define-granular-permissions.md#to-add-other-permission-sets).

Use the **User Group Migration** assisted setup guide to convert your groups. To start the guide, on the **Feature Management** page, find **Feature: Convert user group permissions**, and then choose **All Users** in the **Enabled For** field. The assisted setup guide offers the following options for the conversion.

|Option  |Description  |
|---------|---------|
|Assign to user     | Assign the permissions in user groups directly to the users who were assigned to the group, and remove their user group assignments.        |
|Convert to a permission set     | Create a new permission for the permissions in each user group. The new permission set is assigned to all members of each user group.          |

### License configurations still apply

You can configure permissions in [!INCLUDE [prod_short](includes/prod_short.md)] based on licenses. Those permissions are directly assigned to new users. These configurations still apply, even if you start using security groups.

To use security groups exclusively, we recommend that you remove the license configurations. To learn more about license configurations, go to [Create Users According to Licenses](ui-how-users-permissions.md).

You can remove license configurations on the **License Configuration** page. Choose a license, and then delete all permission sets assigned to it.

## Related information

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Set Up Business Central Access in Teams with Microsoft 365 Licenses](admin-access-with-m365-license-setup.md)  
[Learn about groups and access rights in Microsoft Entra ID](/azure/active-directory/fundamentals/concept-learn-about-groups)  
[Microsoft Entra security groups](/windows-server/identity/ad-ds/manage/understand-security-groups)  
