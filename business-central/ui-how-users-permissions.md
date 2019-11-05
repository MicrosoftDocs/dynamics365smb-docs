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
ms.date: 11/06/2019
ms.author: sgroespe

---
# Manage Users and Licenses - Define who can sign in to Business Central
The process of managing licenses and users depends on deployment option. 

## Users and license in online deployments
In [!INCLUDE[d365fin](includes/d365fin_md.md)] online number of users is defined in subscription added by partner to your tenant in Microsoft Partner Center. For more information, see [add a customer](https://docs.microsoft.com/partner-center/add-a-new-customer) and create [new subscriptions](https://docs.microsoft.com/partner-center/create-a-new-subscription)

To define who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)] the product licenses should be assigned to users accordingly to roles they should perform in [!INCLUDE[d365fin](includes/d365fin_md.md)]:
- Your company's Office 365 administrator can do it in [Microsoft 365 Admin center](https://admin.microsoft.com). For more information, see [Add Users to Office 365](https://aka.ms/CreateOffice365Users).  
- Partner can assign licenses in Microsoft 365 Admin center or in Microsoft Partner Center. For more information, see [assign licenses to users](https://docs.microsoft.com/partner-center/assign-licenses-to-users).
For more information, see: [Administration of Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-administration) in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].

Once users with [!INCLUDE[d365fin](includes/d365fin_md.md)] license are created in Office 365, they can be imported into the **Users** page in [!INCLUDE[d365fin](includes/d365fin_md.md)] by using the **Get Users from Office 365** action. 

### To add a user in Business Central
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Choose the **Get Users from Office 365** action.

Any new user that has been created for your Office 365 subscription will be added on the **Users** page. Users are assigned permission sets depending on the license assigned to the user in Office 365. You can then proceed to assign granular permissions to users and to organize them in user groups. For more information, see [To assign permission sets to users](ui-how-users-permissions.md#to-assign-permission-sets-to-users).
 
### To remove a user's access to the system
As an administrator, you can remove a user's access to the system by setting the **State** field to **Disabled**. All references to the user will be retained, but the user can no longer sign in to the system, and active sessions for the user will be terminated. To give the user access again, set the **State** field to **Enabled**.

You can remove, or unassign, licenses from users in Office 365 Admin Center. Users without license can no longer sign in to the system, see [Unassign licenses from users](https://docs.microsoft.com/office365/admin/manage/remove-licenses-from-users).

### Changing assigned license for user
Sometimes you may need to change license assigned to users. For example, you decided to use Service Management module and therefore you upgrade all Essential licenses to Premium. Another case is when user’s responsibility has changed and you need to replace Team Member license with Essential.
1. Change license in Office 365 Admin Center. For more information, see [Add Users to Office 365](https://aka.ms/CreateOffice365Users).
2. Sign is as an administrator in to [!INCLUDE[d365fin](includes/d365fin_md.md)].
3. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
4. On the **Users** page, choose the **Refresh all User Groups** action.
The users will be moved to a proper user group and the permission sets will be updated. For more information, see [To manage permissions through user groups](ui-how-users-permissions.md#to-manage-permissions-through-user-groups).

> [!NOTE] 
> All regular users in a solution must be assigned the same license, Essential or Premium.
> For information about licensing, see [Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing).

## Users and license in on-premises deployments
For on-premises deployments number of licensed users is specified in license file (*.flf). Once administrator or partner uploads the licensing file, administrator can specify users who can sign in to [!INCLUDE[d365fin](includes/d365fin_md.md)].
For on-premises deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], the administrator creates, edits, deletes users directly from **Users** page. 

### To edit or delete a user On-Premises
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to edit, and then choose the **Edit** action.
3. On the **User Card** page, change the information as necessary.    
4. To delete a user, select the user that you want to delete, and then choose the **delete** action.

> [!NOTE]
> For on-premises deployments of [!INCLUDE[d365fin](includes/d365fin_md.md)], the administrator can choose between different credential authorization mechanisms for users. Then, when you create a user, you provide different information depending on the credential type that you are using in the specific [!INCLUDE[server](includes/server.md)] instance.<br /><br />
> For more information, see the [Authentication and Credential Types](/dynamics365/business-central/dev-itpro/administration/users-credential-types) in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)].

Once users created you can then proceed to assign granular permissions to users and to organize them in user groups. For more information, see [To assign permission sets to users](ui-how-users-permissions.md#to-assign-permission-sets-to-users).

# Define Granular Permissions

The [!INCLUDE[d365fin](includes/d365fin_md.md)] security system allows you to control which objects or tables a user can access within each database or environment. You can specify the type of access that each user has to these objects and tables, whether they are able to read, modify, or enter data. You can learn more about [Data Security](/dynamics365/business-central/dev-itpro/security/data-security?tabs=object-level) in in the Administration section of the developer and ITPro content for [!INCLUDE[d365fin](includes/d365fin_md.md)]. 

In [!INCLUDE[d365fin](includes/d365fin_md.md)], there are two levels of permissions for the application objects:
- Permissions that describe which objects a user is entitled to use according to the license they purchased 
- Permissions that describe which objects an administrator or a partner gave the user access to inside [!INCLUDE[d365fin](includes/d365fin_md.md)] 

Once users are created in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can then proceed to assign permission sets to the users to define which database objects, and thereby which UI elements, they have access to, and in which companies. To make it easier to manage users in [!INCLUDE[d365fin](includes/d365fin_md.md)], including to assign permissions to them, you can organize them in user groups. For more information, see [To manage permissions through user groups](ui-how-users-permissions.md#to-manage-permissions-through-user-groups).

> [!NOTE]
> An additional method of defining which features a user has access to is by setting the **Experience** field on the **Company Information** page. For more information, see [Change Which Features are Displayed](ui-experiences.md).

> You can also define what users see in the user interface and how they interact with their permitted functionality through pages. You do this through profiles that you assign to different types of users according to their job role or department. For more information, see [Manage Profiles](admin-users-profiles-roles.md) and [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md).

## To assign permission sets to users
A permission set is a collection of permissions for specific objects in the database. All users must be assigned one or more permission sets before they can access [!INCLUDE[d365fin](includes/d365fin_md.md)].
A [!INCLUDE[d365fin](includes/d365fin_md.md)] solution contains a number of predefined permission sets that are added by Microsoft or by your software provider. You can also add new permission sets tailored to meet the needs of your organization. For more information, see [To create or edit a permission set](ui-how-users-permissions.md#to-create-or-modify-a-permission-set).

>[!NOTE] If you as administrator don’t want to restrict user access more than it is already defined in license you can assign to user special permission set, called SUPER. That permission set ensures user can access all objects specified in the license. 
>The user with Essential license and SUPER permission set has access to more functionality than user with Team member license and SUPER permission set.

You can assign permissions sets to users in two ways:
- Define permission sets on a user's user card.
- Select the check box for a user, on a column, for a related permission set, on a row, on the **Permission Set by User** page.

### To assign a permission set on a user card
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Select the user that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **Edit** action to open the **User Card** page.
4. On the **User Permission Sets** FastTab, on a new line, fill in the fields as necessary. For more information, see [To create or edit a permission set](ui-how-users-permissions.md#to-create-or-modify-a-permission-set).

### To assign a permission set on the **Permission Set by User** page  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User** action.
3. On the **Permission Set by User** page, select the **[user name]** check box on a line for the relevant permission set to assign the set to the user.
4. Select the **All Users** check box to assign the permission set to all users.

## To get an overview of a user's permissions
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. Open the card of the relevant user.
3. Choose the **Effective Permissions** action.

    The **Permissions** part lists all the database objects that the user has access to. You cannot edit this section.

    The **By Permission Set** part shows the assigned permission sets through which the permissions are granted to the user, the source and type of the permission set, and to which extend the different access types are permitted.

    For each row that you select in the **Permissions** section, the **By Permission Set** section shows which permission set or sets that the permission is granted through. In this section, you can edit the value in each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, **Execute Permission**.

    > [!NOTE]  
    > Only permission sets of type **User-Defined** can be edited.<br /><br />
    > Rows of source Entitlement originate from the subscription plan. The permission values of the entitlement overrule values in other permission sets if they have a higher ranking. A value in a non-entitlement permission set that has a higher ranking than the related value in the entitlement will be surrounded by brackets to indicate that it is not effective as it is overruled by the entitlement. For an explanation of ranking, see [To create or edit permissions manually](ui-how-users-permissions.md#to-create-or-modify-permissions-manually).  

4. To edit a permission set, in the **By Permission Set** part, on the line for a relevant permission set of type **User-Defined**, choose one of the five access type fields and select a different value.

5. To edit individual permissions within the permission set, choose the value in the **Permission Set** field to open the **Permissions** page. Follow the steps described in [To create or edit permissions](ui-how-users-permissions.md#to-create-or-modify-permissions-manually).  

> [!NOTE]  
> When you edit a permission set, the changes will also apply to other users that have the permission set assigned.

## To create or modify a permission set
Permission sets function as containers of permissions, so that you can easily manage multiple permissions in one record. 

> [!NOTE]  
> A [!INCLUDE[d365fin](includes/d365fin_md.md)] solution typically contains a number of predefined permission sets that are added by Microsoft or by your software provider. These permission sets are of type **System** or **Extension**. You cannot create or edit these types of permission sets or the permissions within them. However, you can copy them to define your own permission sets and permissions. <br /><br />
Permission sets that users create, from new or as copies, are of type **User-Defined** and can be edited.

### To create new permission set from scratch
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2. To create a new permission set, choose the **New** action.
3. On the new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
When you have created a permission set, you must add the actual permissions. For more information, see [To create or modify permissions manually](ui-how-users-permissions.md#to-create-or-modify-permissions-manually).

### To copy a permission set
You can also use a copy function to quickly carry all the permissions of another permission set to a new permission set.

> [!NOTE]  
> If a System permission set that you have copied is changed, you will be notified (depending on your selection), so that you can consider if the changes are relevant to copy or write into your user-defined permission set.

1. On the **Permission Sets** page, select the line for a permission set that you want to copy, and then choose the **Copy Permission Set** action.
2. On the **Copy Permission Set** page, specify the name of the new permission set, and then choose the **OK** button.
3. Select the **Notify on Changed Permission Set** check box if you want to maintain a link between the original and the copied permission sets. The link is then used to notify you if the name or content of the original permission set changes in a future version that the solution is upgraded to later.

The new permission set, containing all the permissions of the copied permission set, is added as a new line on the **Permission Sets** page. Now you can modify permission in the new permission set. Note that the lines are sorted alphabetically within each type. 

## To create or modify permissions manually
This procedure explains how to add or edit permissions manually. You can also have a permissions generated automatically from your actions in the UI. For more information, see [To create or modify permission sets by recording your actions](ui-how-users-permissions.md#to-create-or-modify-permission-sets-by-recording-your-actions).

> [!NOTE]
> When you edit a permission and thereby the related permission set, the changes will also apply to other users that have the permission set assigned.

1. On the **Permission Sets** page, select the line for a permission set, and then choose the **Permissions** action.
2. On the **Permissions** page, create a new line or edit the fields on an existing line.

In each of the five access type fields, **Read Permission**, **Insert Permission**, **Modify Permission**, **Delete Permission**, and **Execute Permission**, you can select one of the following three permission options:

|Option|Description|Ranking|
|------|-----------|
|**Yes**|The user can perform the action on the object in question.|Highest|
|**Indirect**|The user can perform the action on the object in question but only through another related object that the user has full access to.|Second highest|
|**Blank**|The user cannot perform the action on the object in question.|Lowest|

### Example - Indirect Permission
You can assign an indirect permission to use an object only through another object.
For example, a user can have permission to run codeunit 80, Sales-Post. The Sales-Post codeunit performs many tasks, including modifying table 37, Sales Line. When the user posts a sales document, the Sales-Post codeunit, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks if the user has permission to modify theSales Line table. If not, the codeunit cannot complete its tasks, and the user receives an error message. If so, the codeunit runs successfully.

However, the user does not need to have full access to the Sales Line table to run the codeunit. If the user has indirect permission for the Sales Line table, then the Sales-Post codeunit runs successfully. When a user has indirect permission, that user can only modify the Sales Line table by running the Sales-Post codeunit or another object that has permission to modify the Sales Line table. The user can only modify the Sales Line table when doing so from supported application areas. The user cannot run the feature inadvertently or maliciously by other methods.

## To create or modify permission sets by recording your actions
1.	Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Permission Sets**, and then choose the related link.
2.	Alternatively, on the **Users** page, choose the **Permission Sets** action.
3.	On the **Permission Sets** page, choose the **New** Action.
4.	On a new line, fill in the fields as necessary.
5.	Choose the **Permissions** action.
6.	On the **Permissions** page, choose the **Record Permissions** action, and then choose the **Start** action.

    This starts a recording process that captures all your action in the user interface.
7.	Go to the various pages and activities in [!INCLUDE[d365fin](includes/d365fin_md.md)] that you want users with this permission set to access. You must carry out the tasks that you want to record permissions for.
8.	When you want to finish the recording, return to the **Permissions** page, and then choose the **Stop** action.
9.	Choose the **Yes** button to add the recorded permissions to the new permission set.
10.	For each object in the recorded list, specify if users are able to insert, modify, or delete records in the recorded tables.

## Security Filters - To limit a user's access to specific records in a table
For record-level security in [!INCLUDE[d365fin](includes/d365fin_md.md)], you use security filters to limit a user's access to data in a table. You create security filters on table data. A security filter describes a set of records in a table that a user has permission to access. You can specify, for example, that a user can only read the records that contain information about a particular customer. This means that the user cannot access the records that contain information about other customers. For more information, see [Using Security Filters](/dynamics365/business-central/dev-itpro/security/security-filters) in Developer and IT-Pro help.

## To manage permissions through user groups
You can set up user groups to help you manage permission sets for groups of users in your company.

You start by creating a user group. Then you assign permission sets to the group to define which object users of the group can access. When you add user to the group, the permission sets defined for the group will apply to the user.

Permission sets assigned to a user through a user group stay synchronized so that a change to the user group permissions are automatically propagated to the user. If you remove a user from a user group, the involved permissions are automatically revoked.

### To group users in user groups
The following procedure explains how to create user groups manually. To create user groups automatically, see [To copy a user group and all its permission sets](ui-how-users-permissions.md#to-copy-a-user-group-and-all-its-permission-sets).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Alternatively, on the **Users** page, choose the **User Groups** action.
3. On the **User Group** page, choose the **User Group Members** action.
4. On the **User Group Members** page, choose the **Add Users** action.

### To copy a user group and all its permission sets
To quickly define a new user group, you can copy all permission sets from an existing user group to your new user group.

> [!NOTE]
> The user group members are not copied to the new user group. You must add them manually afterwards. For more information, see [To group users in user groups](ui-how-users-permissions.md#to-group-users-in-user-groups).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to copy, and then choose the **Copy User Group** action.
3. In the **New User Group Code** field, enter a name for the group, and then choose the **OK** button.

The new user group is added to the **User Groups** page. Proceed to add users. For more information, see [To group users in user groups](ui-how-users-permissions.md#to-group-users-in-user-groups).  

### To assign permission sets to user groups
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Groups**, and then choose the related link.
2. Select the user group that you want to assign permission to.
Any permission sets that are already assigned to the user are displayed in the **Permission Sets** FactBox.
3. Choose the **User Permission Sets** action to open the **User Permission Sets** page.
4. On the **User Permission Sets** page, on a new line, fill in the fields as necessary.

### To assign a permission set on the Permission Set by User Group page  
The following procedure explains how to assign permission sets to a user group on the **Permission Set by User Group** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Users**, and then choose the related link.
2. On the **Users** page, select the relevant user, and then choose the **Permission Set by User Group** action.
3. On the **Permission Set by User Group** page, select the **[user group name]** check box on a line for the relevant permission set to assign the set to the user group.
4. Select the **All User Groups** check box to assign the permission set to all user groups.

## To set up user time constraints
Administrators can define periods of time during which specified users are able to post, and also specify if the system logs the amount of time users are logged on. Administrators can also assign responsibility centers to users. For more information, see [Work with Responsibility Centers](inventory-responsibility-centers.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **User Setup**, and then choose the related link.
2. On the **User Setup** page opens, choose the **New** action.
3. In the **User ID** field, enter the ID of a user, or choose the field to see all current Windows users in the system.
4. Fill in the fields as necessary.

## See Also
[Manage Profiles](admin-users-profiles-roles.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-customizing-overview.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Add Users to Office 365 for business](https://aka.ms/CreateOffice365Users)  
[Microsoft Dynamics 365 Business Central Licensing Guide](https://aka.ms/BusinessCentralLicensing)  
[Security and Protection in Business Central](/dynamics365/business-central/dev-itpro/security/security-and-protection) in Developer and IT-pro Help
