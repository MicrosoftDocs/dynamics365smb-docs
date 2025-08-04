---
title: Create users according to licenses
description: Describes how to add users to Business Central online or on-premises based on licenses.
author: jswymer
ms.topic: how-to
ms.search.keywords: access, right, security
ms.search.form: 119, 774_Primary, 6300, 6301, 6302, 8930, 9061, 9062, 9069, 9173, 9800_Primary, 9807_Primary, 9808, 9830, 9831, 9838, 9816, 9818, 9874
ms.date: 06/10/2025
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Create users according to licenses

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

This article describes how administrators create users and define who can sign in to [!INCLUDE[prod_short](includes/prod_short.md)]. This article also describes how to assign permissions to different users according to your product licenses.

## Basics

- When you create users in [!INCLUDE[prod_short](includes/prod_short.md)], you grant permissions to them through permission sets. 
- You can also organize users in security groups. Security groups make it easier to manage permissions and other settings for multiple users at the same time.
  [!INCLUDE [2023rw1-sec-group-short](includes/2023rw1-sec-group-short.md)]
- There are several license types. Learn about the different types of licenses and how licensing works in the [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544).

- The process of managing users and licenses varies depending on whether [!INCLUDE[prod_short](includes/prod_short.md)] is deployed online or on-premises. For [!INCLUDE [prod_short](includes/prod_short.md)] online, you must add users from Microsoft 365. In on-premises deployments, you can create, edit, and delete users directly.  

## Manage users and licenses in online tenants

User accounts in [!INCLUDE[prod_short](includes/prod_short.md)] online must be first created in the Microsoft 365 admin center. These user accounts aren't exclusive to [!INCLUDE [prod_short](includes/prod_short.md)]. If you subscribe to other plans, they can be used to sign in to other applications, such as Power BI. For information about creating users in the Microsoft 365 admin center, go to [Add users in Microsoft admin center](/microsoft-365/admin/add-users/add-users).

Your subscription to [!INCLUDE[prod_short](includes/prod_short.md)] online defines how many [!INCLUDE[prod_short](includes/prod_short.md)] user licenses you're allowed. Users are added to your tenant in the Microsoft Partner Center, typically by your Microsoft partner. For more information, see [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration).

You assign licenses to users according to the work each user does in [!INCLUDE[prod_short](includes/prod_short.md)]. You can assign licenses in several ways:

- Your company's Microsoft 365 administrator can do it in the [Microsoft 365 Admin Center](https://admin.microsoft.com). For more information, see [Add users individually or in bulk to Microsoft 365](/microsoft-365/admin/add-users/add-users).  
- A Microsoft partner can assign licenses in the Microsoft 365 Admin Center or in the Microsoft Partner Center. For more information, see [User management tasks for customer accounts](/partner-center/assign-licenses-to-users) in the Microsoft Partner Center Help.

For more information, see [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration) in the administration Help.

After user accounts are created in the Microsoft 365 admin center, there are two ways to import them to [!INCLUDE [prod_short](includes/prod_short.md)]:

- A user account is imported automatically when the user signs in to [!INCLUDE [prod_short](includes/prod_short.md)] the first time.

   > [!NOTE]
   > After a user signs in to [!INCLUDE [prod_short](includes/prod_short.md)] online, you can't delete the user.

- The administrator can import users by choosing the **Update Users from Microsoft 365** action on the **Users* page.

Both approaches have their own advantages, and you can use them simultaneously. Each approach allows administrators to proactively configure [!INCLUDE [prod_short](includes/prod_short.md)] to assign the starting permissions, user groups, and user profiles. Using the **Update Users from Microsoft 365** action gives administrators more control to adjust permissions, user groups, and profiles. It's an ideal approach when you're setting up [!INCLUDE [prod_short](includes/prod_short.md)] the first time, before any users sign in, or when adding a new team of users.

> [!NOTE]
> After you add users in the Microsoft 365 Admin Center, we recommend that you update the user information in [!INCLUDE[prod_short](includes/prod_short.md)] as soon as possible. Keeping user information current is easy to do, and helps ensure that people can always sign in. For more information, see [To add users or update user information and license assignments in Business Central](#adduser).<br>
>
> Updating user information is especially important if you've customized permission sets for the license. If a new user tries to sign in to [!INCLUDE[prod_short](includes/prod_short.md)] before you've added them, they might not be able to. For more information, see [Configure permissions based on licenses](#licensespermissions).
>
> However, users who experience this problem aren't actually blocked. They can either use the **Go back home** action, or simply sign in again to resolve the issue.

### Delegated admin users

[!INCLUDE [admin-gdap-users](includes/admin-gdap-users.md)]

### <a name="licensespermissions"></a>Configure permissions based on licenses

[!INCLUDE [2022_releasewave1](includes/2022_releasewave1.md)]

Admins can configure permissions sets and user groups for each license.<!--Note to translators: The names in *italics* or capitalized in this section must not be translated.-->  

For example, the commonly used license, *Dynamics 365 Business Central Team Member*, has the following permissions sets by default:

- D365 READ
- D365 TEAM MEMBER
- EDIT IN EXCEL - VIEW
- EXPORT REPORT EXCEL
- LOCAL

Other permission sets are added automatically based on the user groups assigned to the license. When you create a new user based on this license, [!INCLUDE[prod_short](includes/prod_short.md)] assigns the permission sets originating from the user groups and the permission sets from the license. The same starting permissions are assigned to the user if their user account was created automatically in [!INCLUDE[prod_short](includes/prod_short.md)] or if the administrator used the **Update Users from Microsoft 365** action in the **Users** page.

If this default configuration isn't the right setup for a particular environment, the admin can change that configuration. However, customized permissions affect only new users who are assigned that license. Permissions for existing users who are assigned the license aren't affected.  

1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)] using an administrator account.  
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **License Configuration**, and then choose the related link.  

    <!--Alternatively, if you're already in the **Users** page, you can run the **Update Users from Microsoft 365** guide, and then, on the first page of the guide, choose the **Configure permissions per license** link.-->  
3. In the **License Configuration** page, choose the license that you want to customize, and then choose the **Configure** action.  
4. Choose the **Customize permissions** field to switch on customization, and then make the changes.  

    In our example, the admin wants to remove the permission to edit in Excel, so they remove the *Excel Export Action* user group from the Team Member license. Afterward, new users who are assigned the Team Member license can't export data to Excel. If the organization changes their minds on the subject, they can just go back to the **License Configuration** page and switch off the customization for that license type.  

> [!IMPORTANT]
> This customization of permissions only takes effect for new users that you assign the relevant license. Existing users are not updated. We recommend that you customize permissions before you start assigning users licenses in the Microsoft 365 admin center.

### <a name="adduser"></a>To add users or update user information and license assignments in Business Central

After you add users or change user information in the Microsoft 365 Admin Center, you can quickly import the user information to [!INCLUDE[prod_short](includes/prod_short.md)]. The import includes license assignments.  

> [!TIP]
> If you need to update user information and you have a lot of users, you can use the filter pane to narrow down the list. You can filter on basic information such as the user name, or set more technical filters, such as the user's security ID.

1. Sign in to [!INCLUDE[prod_short](includes/prod_short.md)] using an administrator account.
2. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.  
3. Choose **Update Users from Microsoft 365**.

> [!IMPORTANT]  
> Running the synchronization of users from Microsoft 365 using the **Update Users from Microsoft 365** guide, requires the SUPER permission set.

> [!NOTE]
> The **Update Users from Microsoft 365** guide doesn't update users that are not assigned a license, such as someone who is a [Dynamics 365 administrator](/entra/identity/role-based-access-control/permissions-reference#dynamics-365-administrator). Those users will update the next time they sign in to the environment.

The next step for newly created users is to assign user groups and permissions. Go to [Assign Permissions to Users and Groups](ui-define-granular-permissions.md) for information. If you update a user with a license change, [!INCLUDE [prod_short](includes/prod_short.md)] assigns users to the appropriate user group and updates their permission sets. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md).  

> [!NOTE]
> With 2024 release wave 1, a Premium license user can sign in to a company where the **User Experience** field is set to **Essentials** on the **Company Information** page. However, the Premium user can't use any of the features that the Premium license provides. This doesn't work in the opposite direction. Users who have an Essentials license can't sign in to a company where the **User Experience** is set to **Premium** on the **Company Information** page. For more information about licensing, go to [Business Central](https://dynamics.microsoft.com/business-central/overview/) website.

If you use an external accountant to manage your books and financial reporting, you can invite them to your [!INCLUDE[prod_short](includes/prod_short.md)] so they can work with you on your fiscal data. For more information, see [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant).

For more information about synchronizing user information with Microsoft 365, go to the [Synchronization with Microsoft 365](#m365) section.

> [!NOTE]
> If you use an external accountant to manage your books and financial reporting, you can invite them to your [!INCLUDE[prod_short](includes/prod_short.md)] so they can work with you on your fiscal data. For more information, see [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant).

### To remove a user's access to the system

You can remove a user's access to [!INCLUDE[prod_short](includes/prod_short.md)] online. All references to the user are kept. However, the user can't sign in and active sessions for the user are stopped.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Open the **User Card** page for the relevant user, and then, in the **Status** field, select **Disabled**.
3. To give the user access again, set the **Status** field to **Enabled**.

You can also remove the license from a user in the Microsoft 365 Admin Center. The user is then unable to sign in. For more information, see [Remove licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).

### <a name="m365"></a>Synchronization with Microsoft 365

When you assign a license for [!INCLUDE[prod_short](includes/prod_short.md)] to a user in Microsoft 365, there are two ways to create the user in [!INCLUDE[prod_short](includes/prod_short.md)].  

- The administrator can add the user by choosing the **Update Users from Microsoft 365** action on the **Users** page as described in the [To add a user or update user information in Business Central](#adduser) section.
- The license information updates automatically when the user signs in for the first time.

In both cases, several settings are applied automatically. These settings are listed in the second and third columns in the following table.

If you change user information in Microsoft 365, you can update [!INCLUDE[prod_short](includes/prod_short.md)] to reflect the change. Depending on what you want to update, use one of the actions on the **Users** page. The actions are described in the last two columns in the following table.

|What happens when:|First user, first sign-in|Update Users from Microsoft 365|Restore User Default User Groups|
|-|-|-|-|
|Scope:|Current user|Multiple selected users|Single selected user (except current)|
|Create the new user and assign SUPER permission set.<br /><br /><!--Platform-->|**X**|**X** | | 
|Update the user based on information in Microsoft 365: Status, Full Name, Contact Email, Authentication Email.<!--<br /><br />Codeunit "Azure AD   Graph User".UpdateUserFromAzureGraph-->|**X**|**X**|**X**|
|Synchronize user plans (licenses) with licenses and roles assigned in Microsoft 365.<!--<br /><br />Codeunit "Azure AD   Graph User".UpdateUserPlans-->|**X**|**X**|**X**|
|Add the user to user groups according to the current user plans. Remove the SUPER permission set for all users other than the first user to sign in and [administrators](/dynamics365/business-central/dev-itpro/administration/tenant-administration). At least one SUPER is required.<!--<br /><br />Codeunit "Permission Manager". AddUserToDefaultUserGroups-->|**X**|**X**|**X**<br /><br />Removes manually assigned user groups and permissions.|

Users can access [!INCLUDE[prod_short](includes/prod_short.md)] records in Teams using only their Microsoft 365 license. When access is enabled for an environment, synchronizing using the **Update users from Microsoft 365** action skips users that only have a Microsoft 365 license. To include these users in synchronization, you must first update environment settings by assigning a security group that contains users with a [!INCLUDE[prod_short](includes/prod_short.md)] license and users with only a Microsoft 365 license.

Learn about securing access to environments using security groups at [Manage access using Microsoft Entra groups](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-access#manage-access-using-azure-active-directory-groups).

Get an overview of accessing [!INCLUDE[prod_short](includes/prod_short.md)] in Teams with Microsoft 365 licenses at [admin-access-with-m365-license](admin-access-with-m365-license.md).

## Manage users and licenses in on-premises deployments

For on-premises deployments, the number of user licenses is specified in the license file (.bclicense or .flf). When an administrator or Microsoft partner uploads the license file, they can specify which users can sign in to [!INCLUDE[prod_short](includes/prod_short.md)].

For on-premises deployments, the administrator creates, edits, and deletes users directly from the **Users** page.

> [!NOTE]
> In [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, delegated admin access isn't available like it is in [!INCLUDE[prod_short](includes/prod_short.md)] online. Microsoft partners need standard user licenses to use [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more about licenses in the [Business Central on-premises licensing guide](https://go.microsoft.com/fwlink/?linkid=2009643).

### To edit or delete a user in an on-premises deployment

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to edit, and then choose the **Edit** action.
3. On the **User Card** page, change the information as necessary.  
4. To delete a user, select the user that you want to delete, and then choose the **Delete** action.

> [!NOTE]
> For on-premises deployments an administrator can specify how to authenticate user credentials in the [!INCLUDE[server](includes/server.md)] instance. When you create a user, you provide the credential type that you are using.
>
> For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the administration Help for [!INCLUDE[prod_short](includes/prod_short.md)].

## Analyze user status by license type

You can use the **Data Analysis** feature to analyze data on the [Users](https://businesscentral.dynamics.com/?page=9800&layout=analysis) page. You don't have to run a report or open another application, such as Excel. The feature provides an interactive and versatile way to calculate, summarize, and examine data. Instead of running reports using options and filters, you can add multiple tabs that represent different tasks or views on the data. Some examples are "Users by status" or "Users by license type," or any other view you can imagine. To learn more about how to use the **Data Analysis** feature, go to [Analyze list and query data with analysis mode](analysis-mode.md).

### User analysis scenarios

The following sections provide examples of scenarios where analyzing the user list can help you monitor the status of your users.

| Area | To... | Open this page in analysis mode | Using these fields |
| ---- | ----- | ------------------------------- |------------------- |
| [Users by status](#example-users-by-status) | See a list of users based on their status (enabled/disabled). | [Users](https://businesscentral.dynamics.com/?page=9800&layout=analysis) | **Status**, **User Name**, **Full Name**, **Authorization email**, and **License Type**. |
| [Users by license type](#example-users-by-license-type) | See a list of users based on their license type. | [Users](https://businesscentral.dynamics.com/?page=9800&layout=analysis) | **License Type**, **Status**,  **User Name**, **Full Name**, and **Authorization email**. |

### Example: Users by status

To analyze users by status, follow these steps:

1. Open the [Users](https://businesscentral.dynamics.com/?page=9800&layout=analysis) list, and choose the :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: icon to turn on analysis mode.
1. On the **Columns** menu, remove all columns (select the box next to the **Search** field on the right).
1. Drag the **Status** (user enabled/disabled) and **License Type** fields to the **Row Groups** area.
1. Choose the fields **User Name**, **Full Name**, and **Authorization email**.
1. Rename your analysis tab to **Users by status**, or something that describes this analysis.

The following image shows the result of these steps.

:::image type="content" source=" media/data-analysis-users.png" alt-text="Example of how to do data analysis on the Change Log Entries page (Who changed What data When)." lightbox="media/data-analysis-users.png":::

### Example: Users by license type

To analyze users by license type, follow these steps:

1. Open the [Users](https://businesscentral.dynamics.com/?page=9800&layout=analysis) list, and choose the :::image type="content" source="media/analysis-mode-icon.png" alt-text="Enter analysis mode."::: icon to turn on analysis mode.
1. On the **Columns** menu, remove all columns (select the box next to the **Search** field on the right).
1. Drag the **License Type** and **Status** (user enabled/disabled) fields to the **Row Groups** area.
1. Choose the **User Name**, **Full Name**, and **Authorization email** fields.
1. Rename your analysis tab to **Users by license type**, or something that describes this analysis.

## Related information

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
