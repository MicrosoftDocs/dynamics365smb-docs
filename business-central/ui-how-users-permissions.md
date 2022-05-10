---
title: Create Users According to Licenses
description: Describes how to add users to Business Central online or on-premises based on licenses.
author: edupont04

ms.topic: conceptual
ms.workload: na
ms.search.keywords: access, right, security
ms.search.form: 119, 6300, 6301, 6302, 8930, 9800, 9807, 9808, 9830, 9831, 9838, 9818, 9062, 9061, 9069, 9173
ms.date: 05/09/2022
ms.author: edupont

---
# Create Users According to Licenses

This article describes how administrators create users and define who can sign in to [!INCLUDE[prod_short](includes/prod_short.md)]. This article also covers how to assign permissions to different types users according to your product licenses.

When you create users in [!INCLUDE[prod_short](includes/prod_short.md)], you can assign permissions to them through permission sets and organize users in user groups. User groups make it easier to manage permissions for multiple users at the same time. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

For more information about the different types of licenses and how licensing works in [!INCLUDE[prod_short](includes/prod_short.md)], [download the Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> The process of managing users and licenses varies depending on whether [!INCLUDE[prod_short](includes/prod_short.md)] is deployed online or on-premises. For [!INCLUDE [prod_short](includes/prod_short.md)] online, you must add users from Microsoft 365. In on-premises deployments, you can create, edit, and delete users directly.  

## Manage users and licenses in online tenants

Your subscription to [!INCLUDE[prod_short](includes/prod_short.md)] online defines the number of users you're allowed. Users are added to your tenant in the Microsoft Partner Center, typically by your Microsoft partner. For more information, see [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration).

You assign product licenses to users according to the work each user will do in [!INCLUDE[prod_short](includes/prod_short.md)]. You can assign licenses in several ways:

- Your company's Microsoft 365 administrator can do it in the [Microsoft 365 Admin Center](https://admin.microsoft.com). For more information, see [Add users individually or in bulk to Microsoft 365](/microsoft-365/admin/add-users/add-users).  
- A Microsoft partner can assign licenses in the Microsoft 365 Admin Center or in the Microsoft Partner Center. For more information, see [User management tasks for customer accounts](/partner-center/assign-licenses-to-users) in the Microsoft Partner Center Help.

For more information, see [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration) in the administration Help.

> [!NOTE]
> After you add users in the Microsoft 365 Admin Center, we recommend that you update the user information in [!INCLUDE[prod_short](includes/prod_short.md)] as soon as possible. Keeping user information current is easy to do, and helps ensure that people can always sign in. For more information, see [To add users or update user information and license assignments in Business Central](#adduser).<br>
>
> Updating user information is especially important if you've customized permission sets for the license. If a new user tries to sign in to [!INCLUDE[prod_short](includes/prod_short.md)] before you've added them, they might not be able to. For more information, see [Configure permissions based on licenses](#licensespermissions).
>
> However, users who experience this problem aren't actually blocked. They can either use the **Go back home** action, or simply sign in again to resolve the issue.

[!INCLUDE [admin-gdap-users](includes/admin-gdap-users.md)]

For more information, see [Delegated administrator access to Business Central Online](/dynamics365/business-central/dev-itpro/administration/delegated-admin).  

### <a name="licensespermissions"></a>Configure permissions based on licenses

[!INCLUDE [2022_releasewave1](includes/2022_releasewave1.md)]

Admins can configure permissions sets and user groups based on the different license types.<!--Note to translators: The names in *italics* or capitalized in this section must not be translated.-->  

For example, the commonly used license, *Dynamics 365 Business Central Team Member*, has  the user groups *D365 Team Member* and *Excel Export Action* plus the following permissions sets by default:

- D365 READ
- D365 TEAM MEMBER
- EDIT IN EXCEL - VIEW
- EXPORT REPORT EXCEL
- LOCAL

If this default configuration isn't the right setup for a particular tenant, the admin can change that configuration. However, customized permissions will affect only new users who are assigned that license. Permissions for existing users who are assigned the license won't be affected.  

1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)] using an administrator account.  
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **License Configuration**, and then choose the related link.  

    Alternatively, if you're already in the **Users** page, you can run the **Update Users from Microsoft 365** guide, and then, on the first page of the guide, choose the **Configure permissions per license** link.  
3. In the **License Configuration** page, choose the license that you want to customize, and then choose the **Configure** action.  
4. Choose the **Customize permissions** field to switch on customization, and then make the relevant changes.  

    In our example, the admin wants to remove the permission to edit in Excel, so they remove the *Excel Export Action* user group from the Team Member license. Going forward, new users that are assigned the Team Member license won't get the option to export data to Excel. If the organization changes their minds on the subject, they can just go back to the **License Configuration** page and switch off the customization for that license type.  

> [!IMPORTANT]
> This customization of permissions only take effect for new users that you assign the relevant license. Existing users are not updated. We recommend that you customize permissions before you start assigning users licenses in the Microsoft 365 admin center.

### <a name="adduser"></a>To add users or update user information and license assignments in Business Central

After you add users or change user information in the Microsoft 365 Admin Center, you can quickly import the user information to [!INCLUDE[prod_short](includes/prod_short.md)]. The import includes license assignments.  

1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)] using an administrator account.
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.  
3. Choose **Update Users from Microsoft 365**.

For new users, the next step is to assign user groups and permissions. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md). If you're updating user information, and the update includes a license change, users are assigned to the appropriate user group and their permission sets are updated. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md).  

> [!NOTE]
> All users in an environment must be assigned to the same license, either Essential or Premium. For more information, see the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/business-central/overview/) website.

For more information about synchronizing user information with Microsoft 365, see the [Synchronization with Microsoft 365](#m365) section.

> [!NOTE]
> If you use an external accountant to manage your books and financial reporting, you can invite them to your Business Central so they can work with you on your fiscal data. For more information, see [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant).

### To remove a user's access to the system

You can remove a user's access to [!INCLUDE[prod_short](includes/prod_short.md)] online. All references to the user are kept. However, the user can't sign in and active sessions for the user are stopped.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Open the **User Card** page for the relevant user, and then, in the **Status** field, select **Disabled**.
3. To give the user access again, set the **Status** field to **Enabled**.

You can also remove the license from a user in the Microsoft 365 Admin Center. The user is then unable to sign in. For more information, see [Remove licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).

### <a name="m365"></a>Synchronization with Microsoft 365

When you assign a license for [!INCLUDE[prod_short](includes/prod_short.md)] to a user in Microsoft 365, there are two ways to create the user in [!INCLUDE[prod_short](includes/prod_short.md)].  

- The administrator can add the user by choosing the **Update Users from Microsoft 365** action on the **Users** page as described in the [To add a user or update user information in Business Central](#adduser) section.
- The license information will update automatically when the user signs in for the first time.

In both cases, several settings are made automatically. These settings are listed in the second and third columns in the table below.

If you change user information in Microsoft 365, you can update [!INCLUDE[prod_short](includes/prod_short.md)] to reflect the change. Depending on what you want to update, use one of the actions on the **Users** page. The actions are described in the last three columns in the table below.

> [!NOTE]
> The actions described in the following table are accurate, however, the only one that you need is **Update Users from Microsoft 365**, which was added to simplify the process. The other actions will be removed in a future version of [!INCLUDE[prod_short](includes/prod_short.md)].

|What happens when:|First user, first sign-in|Get Users from Microsoft 365|Update Users from Microsoft 365|Restore User Default User Groups|Refresh User Groups|Update user information from Microsoft 365|
|-|-|-|-|-|-|-|
|Scope:|Current user|New users in Microsoft 365|Multiple selected users|Single selected user (except current)|Multiple selected users|Multiple selected users|
|Create the new user and assign SUPER permission set.<br /><br /><!--Platform-->|**X**||**X** | | | |
|Update the user based on information in Microsoft 365: Status, Full Name, Contact Email, Authentication Email.<!--<br /><br />Codeunit "Azure AD   Graph User".UpdateUserFromAzureGraph-->|**X**|**X**|**X**|**X**||**X**|
|Synchronize user plans (licenses) with licenses and roles assigned in Microsoft 365.<!--<br /><br />Codeunit "Azure AD   Graph User".UpdateUserPlans-->|**X**|**X**|**X**|**X**|**X**| |
|Add the user to user groups according to the current user plans. Remove the SUPER permission set for all users other than the first user to sign in and [administrators](/dynamics365/business-central/dev-itpro/administration/tenant-administration). At least one SUPER is required.<!--<br /><br />Codeunit "Permission Manager". AddUserToDefaultUserGroups-->|**X**|**X**|**X**|**X**<br /><br />Removes manually assigned user groups and permissions.|**X**<br /><br />Update user group assignments.| |

<!--
## The Device License
This section has been moved to [Licensing in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/deployment/licensing).
-->

## Manage users and licenses in on-premises deployments

For on-premises deployments, the number of user licenses is specified in the license file (.flf). When an administrator or Microsoft partner uploads the license file, they can specify which users can sign in to [!INCLUDE[prod_short](includes/prod_short.md)].

For on-premises deployments, the administrator creates, edits, and deletes users directly from the **Users** page.

### To edit or delete a user in an on-premises deployment

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to edit, and then choose the **Edit** action.
3. On the **User Card** page, change the information as necessary.  
4. To delete a user, select the user that you want to delete, and then choose the **Delete** action.

> [!NOTE]
> For on-premises deployments an administrator can specify how to authenticate user credentials in the [!INCLUDE[server](includes/server.md)] instance. When you create a user, you provide the credential type that you are using.
>
> For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the administration Help for [!INCLUDE[prod_short](includes/prod_short.md)].

## See Also

[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Licensing in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/deployment/licensing)  
[Add Users to Microsoft 365 for business](/microsoft-365/admin/add-users/add-users)  
[Security and Protection in Business Central (administration content)](/dynamics365/business-central/dev-itpro/security/security-and-protection)  
[Assign a telemetry ID to users](/dynamics365/business-central/dev-itpro/administration/telemetry-enable-application-insights#assign-a-telemetry-id-to-users)  


[!INCLUDE[footer-include](includes/footer-banner.md)]