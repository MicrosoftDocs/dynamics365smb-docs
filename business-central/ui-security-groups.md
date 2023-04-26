---
title: Control Access Using Security Groups
description: This article describes how to use security groups to define user permissions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: access, right, security, permissions
ms.search.form: 1, 119, 8930, 9800, 9807, 9808, 9830, 9831, 9802, 9855, 9862
ms.date: 02/08/2023
---

# Control Access to Business Central Using Security Groups

[!INCLUDE [2023rw1-sec-group-long](includes/2023rw1-sec-group-long.md)]

Security groups make it easier for administrators to manage user permissions in their Dynamics 365 applications, such as SharePoint Online, CRM Online, and the online version of [!INCLUDE [prod_short](includes/prod_short.md)]. Administrators add permissions to their security groups, and when they add users to the group the permissions apply to all members. For example, an administrator can create a security group that gives salespeople the ability to create and post sales orders. Or, let purchasers do the same for purchase orders.

Create your security groups in your Microsoft 365 admin center or Azure Active Directory. This article describes the steps in Microsoft 365 admin center, but the steps are similar in both.

## Add a security group in the Microsoft 365 admin center

1. In Microsoft 365 admin center, go to the **Active teams & groups** page.
2. Choose **Add a group**.
3. Choose the **Security** type of group, and then choose **Next**.
4. Specify the basics for your group.
5. Optional: Make the members of the group available for role assignment. To learn more about the assignments, go to [Use Azure AD groups to manage role assignments](/azure/active-directory/roles/groups-concept).
6. Open the group, and then use the **Add members** tab to include people in the group.

## Add a security group in Business Central

In [!INCLUDE [prod_short](includes/prod_short.md)], create a security group and then link it to the security group in the Microsoft 365 admin center. Your new group contains the members you added in Microsoft 365 admin center.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Security Groups**, and then choose the related link.
2. Choose **New** to create a group.
3. In the **Name** field, enter a name for the group.
4. In the **AAD security group name** field, enter the name of the security group exactly as it appears in Microsoft 365 admin center. [!INCLUDE [prod_short](includes/prod_short.md)] will find that group and link it to this group.

> [!NOTE]
> The users that show in the **Members** card on the FactBox pane or the **Security Group Members** page only if they've been added as users in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more about adding users, go to [To add users or update user information and license assignments in Business Central](ui-how-users-permissions.md#adduser).  

### Assign permissions to the group

1. On the **Security Groups** page, choose the group, and then choose the **Permissions** action.
1. Assign permissions in the following ways:
    * To assign permission sets individually, in the **Permission Set** field, choose the permissions to assign.
    * To assign multiple permission sets, choose the **Select Permission Sets** action, and then choose the sets to assign.

## Review the permissions in a security group

On the **Security Groups** page, the FactBox pane shows the **Permission Sets** that are assigned to the group. Each user listed in the **Members** card has those permissions. The **Permission Set by Security Group** action provides a more detailed view. There you can also explore the individual permissions in each security group.

Permissions are also available on the **Users** page. The FactBox pane shows the **Permission Sets from Security Group** and **Security Group Memberships** cards for the selected user.

## Security groups and user groups

If you have user groups, you can convert the groups to permission sets in your tenant by using the **User Group Migration** assisted setup guide. To start the guide, on the **Feature Management** page, find **Feature: Convert user group permissions**, and then choose **All Users** in the **Enabled For** field. The assisted setup guide offers the following options for the conversion.

|Option  |Description  |
|---------|---------|
|Assign to user     | Assign the permissions in user groups directly to the users who were assigned to the group, and remove their user group assignments.        |
|Convert to a permission set     | Create a new permission for the permissions in each user group. The new permission set is assigned to all members of each user group.          |

## See Also

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Set Up Business Central Access in Teams with Microsoft 365 Licenses](admin-access-with-m365-license-setup.md)  
[Learn about groups and access rights in Azure Active Directory](/azure/active-directory/fundamentals/concept-learn-about-groups)  
[Active Directory security groups](/windows-server/identity/ad-ds/manage/understand-security-groups)  