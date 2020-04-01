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
ms.date: 04/01/2020
ms.author: sgroespe

---
# Create Users According to Licenses
This topic describes how administrators create users and define who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)], and which permissions are given to different user types according to the licenses.

When you create users in [!INCLUDE[d365fin](includes/d365fin_md.md)] you can assign specific permissions to them through permission sets and organize users in user groups. User groups make it easier to manage permissions for multiple users at the same time. For more information, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).  

> [!NOTE]
> The process of managing users and licenses varies depending on whether [!INCLUDE[d365fin](includes/d365fin_md.md)] is deployed online or on-premises. For example, in online deployments, you can manage users only after they are added to [!INCLUDE[d365fin](includes/d365fin_md.md)] from Office 365. In on-premises deployments, you can create, edit, and delete users directly.  

## Managing Users and Licenses in Online Deployments
In the online version of [!INCLUDE[d365fin](includes/d365fin_md.md)], the number of users is defined by the subscription and added to your tenant in the Microsoft Partner Center, typically by your Microsoft partner. For more information, see [Add a new customer](https://docs.microsoft.com/partner-center/add-a-new-customer) and [Create, suspend, or cancel customer subscriptions](https://docs.microsoft.com/partner-center/create-a-new-subscription) in the Microsoft Partner Center help.

To define who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)], you must assign product licenses to users according to the roles that they will perform in [!INCLUDE[d365fin](includes/d365fin_md.md)]. This can be done in the following ways:
- Your company's Office 365 administrator can do it in the [Microsoft 365 Admin Center](https://admin.microsoft.com). For more information, see [Add users individually or in bulk to Office 365](https://aka.ms/CreateOffice365Users).  
- A Microsoft partner can assign licenses in the Microsoft 365 Admin Center or in the Microsoft Partner Center. For more information, see [User management tasks for customer accounts](https://docs.microsoft.com/partner-center/assign-licenses-to-users) in the Microsoft Partner Center help.

For more information, see [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration) in the Developer and IT-Pro help.

When users are assigned a [!INCLUDE[d365fin](includes/d365fin_md.md)] license in Office 365 you can import them to the **Users** page in [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Get New Users from Office 365** action.

### <a name="adduser"></a>To add a user or update user information in Business Central
Use dedicated import functions to add new users or update user information in [!INCLUDE[d365fin](includes/d365fin_md.md)] from the Microsoft 365 Admin Center.  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Depending on what you want to do, choose either the **Get New Users from Office 365** or **Update Users from Office 365** action.

The new users and user information in your Office 365 subscription will be added on the **Users** page in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information about synchronizing user information with Office 365, see [Synchronization with Office 365](ui-how-users-permissions.md#synchronization-with-office-365).

> [!NOTE]
> If you use an external accountant to manage your books and financial reporting, you can invite them to your Business Central so they can work with you on your fiscal data. For more information, see [Inviting Your External Accountant to Your Business Central](finance-accounting.md#inviteaccountant)

### To remove a user's access to the system
In online deployments, you can remove a user's access to [!INCLUDE[d365fin](includes/d365fin_md.md)]. All references to the user are kept, but the user cannot sign in and active sessions for the user are stopped.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Open the **User Card** page for the relevant user, and then, in the **State** field, select **Disabled**.
3. To give the user access again, set the **State** field to **Enabled**.

You can also remove the license from a user in the Microsoft 365 Admin Center. The user is then unable to sign in. For more information, see [Remove licenses from users](https://docs.microsoft.com/office365/admin/manage/remove-licenses-from-users).

### To change the assigned license for a user
Sometimes you may need to change the license that is assigned to a user. For example, if you decide to use the Service Management module and therefore need to upgrade all Essential licenses to Premium. Or if a user's responsibility has changed and you need to replace a Team Member license to Essential.

1. Change the license in the Microsoft 365 Admin Center. For more information, see [Add users individually or in bulk to Office 365](https://aka.ms/CreateOffice365Users).
2. Sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] as an administrator.
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
4. On the **Users** page, choose the **Restore User Default User Groups** action.

The users will be moved to a proper user group and the permission sets will be updated. For more information, see [To manage permissions through user groups](ui-define-granular-permissions.md).

> [!NOTE]
> All users must be assigned to the same license, either Essential or Premium. For more information, see the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/en-us/business-central/overview/) website.

### Synchronization with Office 365
When you assign a license for [!INCLUDE[d365fin](includes/d365fin_md.md)] to a user in Office 365, there are two ways to create the user in [!INCLUDE[d365fin](includes/d365fin_md.md)]. 

* The administrator can add the user by choosing the **Update Users from Office 365** action on the **Users** page.
* The license information will update automatically when the user signs in for the first time.

In both cases, a number of settings are made automatically. These are listed in the second and third columns in the table below.

If you change user information in Office 365 you can update [!INCLUDE[d365fin](includes/d365fin_md.md)] to reflect the change. Depending on what you want to update, use one of the actions on the **Users** page. The actions are described in the last three columns in the table below.

|What happens when:|First user, first sign-in|Get Users from Office 365|Update Users from Office 365|Restore User Default User Groups|Refresh User Groups|
|-|-|-|-|-|-|
|Scope:|Current user|New users in Office 365|Multiple selected users|Single selected user (except current)|Multiple selected users|
|Create the new user and assign SUPER permission set.<br /><br /><!--Platform-->|**X**|| | | |
|Update the user record based on actual information in Office 365: State, Full Name, Contact Email, Authentication Email.<!--<br /><br />Codeunit "Azure AD   Graph User".UpdateUserFromAzureGraph-->|**X**|**X**|**X**|**X**| |
|Synchronize user plans (licenses) with licenses and roles assigned in Office 365.<!--<br /><br />Codeunit "Azure AD   Graph User".UpdateUserPlans-->|**X**|**X**| |**X**|**X**|
|Add the user to user groups according to the current user plans. Remove the SUPER permission set for all users other than the first user to sign in and [administrators](/dynamics365/business-central/dev-itpro/administration/tenant-administration). At least one SUPER is required.<!--<br /><br />Codeunit "Permission Manager". AddUserToDefaultUserGroups-->|**X**|**X**| |**X**<br /><br />Removes manually assigned user groups and permissions.|**X**<br /><br />Update user group assignments.|

## The Device License
The Dynamics 365 Business Central Device license allows multiple users to simultaneously use a device that is covered by the license. For example, this might be a point of sales, shop floor, or warehouse device. When you have purchased a number of device licenses, up to that number of users assigned to the Dynamics 365 Business Central Device Users group can sign in at the same time. For more information, see the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/en-us/business-central/overview/) website.

Your company's Office 365 administrator or Microsoft partner can create the Dynamics 365 Business Central Device Users group and add device users as members in the [Microsoft 365 Admin Center](https://admin.microsoft.com/) or on the [Azure Portal](https://portal.azure.com/).

### Device User Limitations
Users with the Device license cannot perform the following tasks in [!INCLUDE[d365fin](includes/d365fin_md.md)]:

- Set up jobs to run as scheduled tasks in the job queue. Device users are concurrent users and, therefore, we cannot ensure that the involved user is present in the system when a task is executed, which is required.

- A device user cannot be the first user to sign in. A user of type Administrator, Full User, or External Accountant must be the first to sign in so they can set up [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Administrators](/dynamics365/business-central/dev-itpro/administration/tenant-administration).

### To create a Dynamics 365 Business Central Device Users group
1. In the Microsoft 365 Admin Center, go to the **Groups** page.
2. Choose the **Add a group** action.
3. On the **Choose a group type** page, choose the **Security** action, and then choose the **Add** action.
4. On the **Basics** page, enter **Dynamics 365 Business Central Device Users** as the name of the group.
  
   >[!Note]
   >The name of the group must be spelled in English exactly as shown in step 4, even if you are using another language.
5. Choose the **Close** button.

> [!NOTE]
> You can also create a group of type Office 365. For more information, see [Compare Groups](https://docs.microsoft.com/office365/admin/create-groups/compare-groups)

### To add members to the group
1. In the Microsoft 365 Admin Center, refresh the **Groups** page so your new group appears.
2. Select the **Dynamics 365 Business Central Device Users** group, and then choose the **View all and manage members** action.
3. Choose the **Add members** action.
4. Select the users that you want to add, and then choose the **Save** button.
5. Choose the **Close** button three times.

You can add as many users to the Dynamics 365 Business Central Device Users group as you need. However, the number of devices that users can sign in to simultaneously is defined by the number of purchased device licenses.

> [!NOTE]
> You do not need to assign a [!INCLUDE[d365fin](includes/d365fin_md.md)] license to users that are members of the Dynamics 365 Business Central Device Users group.

## Managing Users and Licenses in On-premises Deployments
For on-premises deployments, the number of user licenses is specified in the license file (.flf). When an administrator or Microsoft partner uploads the license file, the administrator can specify which users can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)].

For on-premises deployments, the administrator creates, edits, and deletes users directly from the **Users** page.

### To edit or delete a user in an on-premises deployment
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to edit, and then choose the **Edit** action.
3. On the **User Card** page, change the information as necessary.    
4. To delete a user, select the user that you want to delete, and then choose the **Delete** action.

> [!NOTE]
> For on-premises deployments an administrator can specify how to authenticate user credentials in the [!INCLUDE[server](includes/server.md)] instance. When you create a user, you provide the credential type that you are using.<br /><br />
> For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the Administration section of the Developer and IT-Pro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].

## See Also
[Assign Permissions to Users and Groups](ui-define-granular-permissions.md)  
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help
