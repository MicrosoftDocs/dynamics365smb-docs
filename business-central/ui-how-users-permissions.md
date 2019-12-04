---
title: Assign or Edit User Permissions  | Microsoft Docs
description: Describes how to add Office 365 users to Business Central, and then assign permissions, access rights, and security settings.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: access, right, security
ms.date: 12/03/2019
ms.author: sgroespe

---
# Create Users According to Licenses
The following describes how you as an administrator create users and define who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)], and which fundamental rights different user types have according to the licenses.

When users are created in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can proceed to assign specific permissions to users through permission sets and to organize users in user groups for easy permission management. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

> [!NOTE]
> The process of managing users and licenses varies depending on whether your solution is deployed online or on-premises. For example, in online deployments, you can only disable and enable a user once added to [!INCLUDE[d365fin](includes/d365fin_md.md)]. In on-premises deployments, you can create, edit, and delete users.  

## Managing Users and Licenses in Online Deployments
In [!INCLUDE[d365fin](includes/d365fin_md.md)] online, the number of users is defined by the subscription and added to your tenant in the Microsoft Partner Center, typically by your Microsoft partner. For more information, see [Add a new customer](https://docs.microsoft.com/partner-center/add-a-new-customer) and [Create, suspend, or cancel customer subscriptions](https://docs.microsoft.com/partner-center/create-a-new-subscription) in the Microsoft Partner Center help.

To define who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)], the product licenses must be assigned to users according to the roles that they will perform in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This can be done in the following ways:
- Your company's Office 365 administrator can do it in the [Microsoft 365 Admin Center](https://admin.microsoft.com). For more information, see [Add users individually or in bulk to Office 365](https://aka.ms/CreateOffice365Users).  
- A Microsoft partner can assign licenses in the Microsoft 365 Admin Center or in the Microsoft Partner Center. For more information, see [User management tasks for customer accounts](https://docs.microsoft.com/partner-center/assign-licenses-to-users) in the Microsoft Partner Center help.

For more information, see [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration) in the Developer and ITPro help.

When users with a [!INCLUDE[d365fin](includes/d365fin_md.md)] license are created in Office 365, they can be imported into the **Users** page in [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Get New Users from Office 365** action.

### To add a user in Business Central
To add users from the Microsoft 365 Admin Center to [!INCLUDE[d365fin](includes/d365fin_md.md)] online, you use a dedicated import function.  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Choose the **Get New Users from Office 365** action.

Any new user that has been created for your Office 365 subscription will be added on the **Users** page. Users are assigned permission sets according to the license assigned to the user in Office 365. You can then proceed to assign more detailed permissions to users and to organize them in user groups for easy permission management. For more information, see [To assign permission sets to users](ui-define-granular-permissions.md#to-assign-permission-sets-to-users).

> [!NOTE]
> If you use an external accountant to manage your books and financial reporting, you can invite them to your Business Central so they can work with you on your fiscal data. For more information, see [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant)

### To remove a user's access to the system
In online deployments, you can remove a user's access to the system by setting the **State** field to **Disabled**. All references to the user will be retained, but the user can no longer sign in to the system and active sessions for the user will be terminated.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Open the **User Card** page for the relevant user, and then, in the **State** field, select **Disabled**.
3. To give the user access again, set the **State** field to **Enabled**.

In addition to disabling a user, you can unassign the license from a user in the Microsoft 365 Admin Center. The user is then unable to sign in. For more information, see [Unassign licenses from users](https://docs.microsoft.com/office365/admin/manage/remove-licenses-from-users).

### To change the assigned license for a user
Sometimes you may need to change the license that is assigned to a user. For example, if you decide to use the Service Management module and therefore need to upgrade all Essential licenses to Premium. Or if a user’s responsibility has changed and you need to replace a Team Member license to Essential.

1. Change the license in the Microsoft 365 Admin Center. For more information, see [Add users individually or in bulk to Office 365](https://aka.ms/CreateOffice365Users).
2. Sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] as an administrator.
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
4. On the **Users** page, choose the **Refresh all User Groups** action.

The users will be moved to a proper user group and the permission sets will be updated. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md#to-manage-permissions-through-user-groups).

> [!NOTE]
> All regular users in a solution must be assigned the same license, Essential or Premium.
> For information about licensing, see [Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing).

### Synchronization with Office 365
When a license is assigned to a user in Office 365, there are two ways to create the user in [!INCLUDE[d365fin](includes/d365fin_md.md)]. The system will do it automatically when the user signs in for the first time, or the administrator can add the user by choosing the **Get Users from Office 365** action on the **Users** page.

In both cases, a number of additional settings are made automatically. These are listed in the second and third columns
in the table below.

If you change the user in Office 365 afterwards, and you need to synchronize the changes to [!INCLUDE[d365fin](includes/d365fin_md.md)], you can use different actions on the **Users** page depending on what exactly you want to synchronize. These are listed in the last three columns in the table below.

|What happens when:|First sign-in|Get Users from Office 365|Update Users from Office 365|Restore User Default User Groups|Refresh User Groups|
|-|-|-|-|-|-|
|Scope:|Current user|New users in Office 365|Multiple selected users|Single selected user (except current)|Multiple selected users|
|Create the new user and assign SUPER permission set.<br /><br />Platform|**X**|**X**| | | |
|Update the user record based on actual information in Office 365: State, Full Name, Contact Email, Authentication Email.<br /><br />Codeunit "Azure AD   Graph User".UpdateUserFromAzureGraph|**X**|**X**|**X**|**X**| |
|Synchronize user plans (licenses) with licenses and roles assigned in Office 365.<br /><br />Codeunit "Azure AD   Graph User".UpdateUserPlans|**X**|**X**| |**X**|**X**|
|Add the user to user groups according to the current user plans. Revoke SUPER permission set. (At least one SUPER is needed. Do not revoke from [administrators](/dynamics365/business-central/dev-itpro/administration/tenant-administration).)<br /><br />Codeunit "Permission Manager". AddUserToDefaultUserGroups|**X**|**X**| |**X**<br /><br />Overwrite: Remove the user from other groups. Remove manually assigned permission sets.|**X**<br /><br />Additive: Keep the current membership in  the user group and assigned permission sets intact. Only add user to groups if needed.|

## Managing Users and Licenses in On-premises Deployments
For on-premises deployments, a number of licensed users is specified in the license file (.flf). When the administrator or Microsoft partner uploads the license file, the administrator can specify which users can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)].

For on-premises deployments, the administrator creates, edits, and deletes users directly from the **Users** page.

### To edit or delete a user on-premises
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to edit, and then choose the **Edit** action.
3. On the **User Card** page, change the information as necessary.    
4. To delete a user, select the user that you want to delete, and then choose the **delete** action.

> [!NOTE]
> For on-premises deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], the administrator can choose between different credential authorization mechanisms for users. Then, when you create a user, you provide different information depending on the credential type that you are using in the specific [!INCLUDE[server](includes/server.md)] instance.<br /><br />
> For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].

## See Also
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users)  
[Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help
