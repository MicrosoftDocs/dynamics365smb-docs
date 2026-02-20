---
title: Control Access Using Security Groups
description: This article describes how to use security groups to define user permissions.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: access, right, security, permissions
ms.search.form: 1, 119, 8930, 9800, 9807, 9808, 9830, 9831, 9802, 9855, 9862, 9875_Primary, 9874_Primary, 9873_Primary, 9872_Primary, 9877_Primary, 9869_Primary, 9868_Primary, 9871_Primary
ms.date: 02/18/2026
ms.service: dynamics-365-business-central
---

# Control access to Business Central using security groups

Security groups make it easier for administrators to manage user permissions. For example, for [!INCLUDE [prod_short](includes/prod_short.md)] online, they're reusable across Dynamics 365 applications, such as SharePoint Online, CRM Online, and [!INCLUDE [prod_short](includes/prod_short.md)]. Administrators add permissions to their [!INCLUDE [prod_short](includes/prod_short.md)] security groups, and when they add users to the group the permissions apply to all members. For example, an administrator can create a [!INCLUDE [prod_short](includes/prod_short.md)] security group that gives salespeople the ability to create and post sales orders. Or, let purchasers do the same for purchase orders.

> [!NOTE]
> This article describes how to grant certain permissions to users based on their membership of a security group. Learn how to control whether users can access an environment based on their membership of a security group in [Manage Access to Environments](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-access).

## Create security groups in Microsoft Entra or Windows Active Directory

You can use security groups for the online and on-premises versions of [!INCLUDE [prod_short](includes/prod_short.md)]. Depending on your deployment and authentication method, create groups in one of the following ways:

### [Online](#tab/online)

Create Microsoft Entra groups in Microsoft Entra admin center. Learn more in [Create, edit, or delete a security group in the Microsoft 365 admin center](/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

### [On-premises](#tab/onprem)

**With Microsoft Entra ID authentication:**

- Upgrade to Business Central versions 25.11, 26.5, 27.4 or later
- Configure [!INCLUDE [server](includes/server.md)] by setting `EnableEntraGroupsOnPrem` to `true` in CustomSettings.config. Learn more in [Configure Business Central Server](/dynamics365/business-central/dev-itpro/administration/configure-server-instance).
- Create Microsoft Entra groups in Microsoft Entra admin center. Learn more in [Create, edit, or delete a security group in the Microsoft 365 admin center](/microsoft-365/admin/email/create-edit-or-delete-a-security-group).

**With Windows authentication:**

Create Windows Active Directory groups. Learn more in [Create a Group Account in Windows Active Directory](/windows/security/operating-system-security/network-security/windows-firewall/create-a-group-account-in-active-directory).

> [!NOTE]
> If you've set up a special type of user with a Windows Group license type in a version of [!INCLUDE [prod_short](includes/prod_short.md)] on-prem earlier than 2023 release wave 1, when you upgrade [!INCLUDE [prod_short](includes/prod_short.md)] converts the user to a security group. The new security group has the same name as the Windows group name. The security group provides a better overview of the group members and their effective permissions.

---

## Add security groups in Business Central

Once you've created your Microsoft Entra or Windows Active Directory groups, link them to security groups in Business Central.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Security Groups**, and then select the related link.
1. Select **New** to create a group.
1. Create the link to your group, as follows:

   - For [!INCLUDE [prod_short](includes/prod_short.md)] online, select the group in the **Microsoft Entra security group name** field.
   - For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, select the group in the **Windows group name** field.

> [!NOTE]
> The users show in the **Members** card on the FactBox pane or the **Security Group Members** page only if they're added as users in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more about adding users, go to [To add users or update user information and license assignments in Business Central](ui-how-users-permissions.md#adduser).  

## Assign permissions to a security group

1. On the **Security Groups** page, select the group, and then select the **Permissions** action.
1. Assign permissions in the following ways:

   - To assign permission sets individually, in the **Permission Set** field, select the permissions to assign.
   - To assign multiple permission sets, select the **Add multiple** action, and then select the sets to assign.
1. If you want the permission sets to apply only to a specific company, set the **Company** column to that company. If you want the permission set to apply to all companies, leave the **Company** column blank. [Learn more](ui-define-granular-permissions.md#control-access-to-specific-companies).

## Related information

[Create Users According to Licenses](ui-how-users-permissions.md)  
[Set Up Business Central Access in Teams with Microsoft 365 Licenses](admin-access-with-m365-license-setup.md)  
[Learn about groups and access rights in Microsoft Entra ID](/azure/active-directory/fundamentals/concept-learn-about-groups)  
[Microsoft Entra security groups](/windows-server/identity/ad-ds/manage/understand-security-groups)  
